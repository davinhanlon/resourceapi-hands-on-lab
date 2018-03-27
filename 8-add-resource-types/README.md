# Add Resource Types

Navigate to your newly created type. The type represents the data attributes that are to be managed by Puppet.

```cd lib/puppet/type/```

The type will be named <resource_name>. Open it, check that the code matches the below.

```
require 'puppet/resource_api'

Puppet::ResourceApi.register_type(
  name: '<resource_name>',
  docs: <<-EOS,
      This type provides Puppet with the capabilities to manage ...
    EOS
  features: [],
  attributes:   {
    ensure:      {
      type:    'Enum[present, absent]',
      desc:    'Whether this resource should be present or absent on the target system.',
      default: 'present',
    },
    name:        {
      type:      'String',
      desc:      'The name of the resource you want to manage.',
      behaviour: :namevar,
    },
  },
)
```

This is a skeleton of the type. Now, we need to make it useful so that the type represents the actual data to be managed by Puppet.

TODO: explain the contents of the type, what data can be represented. Some basic rules on what not to do.

TODO: this needs to change, can't be the NEST. For this tutorial we will create a data type to respresent the temperature of a Nest thermostat. The temperature is an Integer, so we'll represent that as below.

```
require 'puppet/resource_api'

Puppet::ResourceApi.register_type(
  name: 'temp',
  docs: <<-EOS,
      This type allows the temperature of a Nest thermostat's temperature to be controlled by Puppet
    EOS
  features: [],
  attributes:   {
    ensure:      {
      type:    'Enum[present, absent]',
      desc:    'Whether this resource should be present or absent on the target system.',
      default: 'present',
    },
    name:        {
      type:      'Integer',
      desc:      'The temperature of the thermostat.',
      behaviour: :namevar,
    },
  },
)
```

Now that we've done the type, we need to add the Provider. The provider is the piece of code that will interact with the thermostat to get and set data. This is broken into two sections: a get and a set.

[9. Implement Get Data in Provider](../9-get-data-in-provider)
