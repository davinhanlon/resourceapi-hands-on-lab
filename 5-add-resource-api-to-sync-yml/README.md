# Add Resource API Reference to .sync.yml

By default the PDK does not create a sync.yml. It needs to be added.

Change directory into the root directory of the module. ```cd <module_name>```

Then create a new file called ```.sync.yml``` with the following contents

```
# .sync.yml
---
Gemfile:
  optional:
    ':development':
      - gem: 'puppet-resource_api'
spec/spec_helper.rb:
  mock_with: ':rspec'
```

TODO add some explanation as to why this is necessary - and will it always be necessary.

[6. Run PDK Update](6-run-pdk-update)
