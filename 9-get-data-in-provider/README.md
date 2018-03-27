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

As you can see there are 4 functions listed.

## get
This gets information from the target. It is called when the ```puppet resource <type>``` call is made. It is also called when data is to be written to the target. Before writing information to a target Puppet will check if the data is already set on the target and if not by executing the get. Only then will Puppet take the decision to write the data to the target.

## create
TODO when is this executed by Puppet?

## update
This is the set operation. It is called when ```puppet apply <manifest.pp>``` is called and the data is not already set on the target. This is the code that writes information to the target.

## delete
TODO is this just when ensure = absent is set?

Not all 4 functions must be implemented for a provider to be valuable. For example, on some remote targets it may not be possible to delete resource data.

