# Implement Get Function in Provider.

Now that we have the resource type defined, we need to write some code that will interact with the target to manipulate the type. This code is called the provider. It contains code that is executed by Puppet depending on the operating being performed. The first piece of code we will create will implement a function to get information from the target.

Navigate to the directory containing the provider. This is located in ```<module_name>/lib/puppet/provider/<provider_name>/```. In that directory you will find a file with the name of the type and the extension ```.rb``` indicating that it's a Ruby file.

TODO: update 

The provider should contain code as below

```
require 'puppet/resource_api'
require 'puppet/resource_api/simple_provider'

# Implementation for the meh type using the Resource API.
class Puppet::Provider::Meh::Meh < Puppet::ResourceApi::SimpleProvider
  def get(_context)
    [
      {
        name: 'foo',
        ensure: :present,
      },
      {
        name: 'bar',
        ensure: :present,
      },
    ]
  end

  def create(context, name, should)
    context.notice("Creating '#{name}' with #{should.inspect}")
  end

  def update(context, name, should)
    context.notice("Updating '#{name}' with #{should.inspect}")
  end

  def delete(context, name)
    context.notice("Deleting '#{name}'")
  end
end
```

As you can see there are 4 functions listed. TODO: thoughts: perhaps this needs its own page, or should go on the previous page?

## get
This gets information from the target. It is called when the ```puppet resource <type>``` call is made. It is also called when data is to be written to the target. Before writing information to a target Puppet will check if the data is already set on the target and if not by executing the get. Only then will Puppet take the decision to write the data to the target.

## create
TODO when is this executed by Puppet?

## update
This is the set operation. It is called when ```puppet apply <manifest.pp>``` is called and the data is not already set on the target. This is the code that writes information to the target.

## delete
TODO is this just when ensure = absent is set?

Not all 4 functions must be implemented for a provider to be valuable. For example, on some remote targets it may not be possible to delete resource data.

# Implement get code
For this tutorial, we will get information from the thermostat. Add the following code block to the get function:

TODO: this needs to change

```
    _context.notice("Getting something from the Nest")

    url = URI('https://firebase-apiserver20-tah01-iad01.dapi.production.nest.com:9553')

    http = Net::HTTP.new(url.host, url.port)
    http.use_ssl = true
    http.verify_mode = OpenSSL::SSL::VERIFY_NONE

    request = Net::HTTP::Get.new(url)
    request["content"] = 'application/json'
    request["authorization"] = '<your unique id>'

    response = http.request(request)

    parsed = JSON.parse(response.body)

    _context.notice(response.code)
    _context.notice(parsed["devices"]["thermostats"]["<your stat id>"]["target_temperature_c"])
    _context.notice('done with getter')
    
    parsed["devices"]["thermostats"]["<your stat id>"]["target_temperature_c"]
```

The code above references some libraries that are required in order to work. Please include the following at the top of the provider file:

```
require 'uri'
require 'net/http'
require 'openssl'
require 'json'
```

Now the 'getter' is written. This means that Puppet should be able to connect to the thermostat and retrieve the temperature. Let's give it a go.

[10 Validate Code](../10-validate-code)
