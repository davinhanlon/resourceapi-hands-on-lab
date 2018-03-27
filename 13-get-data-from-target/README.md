# Get Data from Target

All that needs to be done is run the ```puppet resource``` command for a speific type. This will invoke the get method of the associated provider. run ```puppet resource <type_name>``` and output will be displayed similar to that below.

```
Notice: Puppet::ResourceApi::PuppetContext::PuppetLogger: temp: Getting something from the nest
Notice: Puppet::ResourceApi::PuppetContext::PuppetLogger: temp: 22.5
Notice: Puppet::ResourceApi::PuppetContext::PuppetLogger: temp: done with getter
```

TODO: Update to be an accurate reflection of what we're trying to do.

TODO: udpate: As we can see the temperature of the stat is 22.5.

Now that we can retrieve data from the target we will move on to explain how to set data on the target.

[14. Set Data in Provider](../14-set-data-in-provider)
