# Deploy Module

The module has been written to include a type and associated provider. The code has been validated and unit tests have been run. Now we're going to deploy and test it against a real device.

TODO: need to have puppet installed for this to work. check if all this works with just the agent...! Add details for installing the agent at the start of the tutorial

TODO: add operating system specific folders.
Check the module path by running ```puppet config print modulepath```. This will return a directory such as: ```/home/davinhanlon/.puppetlabs/etc/code/modules/```.

Now copy the module to that directory. Run ```cp -R <module_directory>  /home/davinhanlon/.puppetlabs/etc/code/modules/```.

The module is now deployed and Puppet will recognise the type. To check this type ```puppet resource --types``` to list all types on the puppet server. To display fewer types type the following command to check that your type is on the Puppet server: ```puppet resource --types | grep temp```

Now let's use the module.

[13. Get Data from the Target](13-get-data-from-target)
