# Validate Code

The PDK makes it easy to validate code and ensure that it is formatted correctly before committing the code.

TODO: List the functions that pdk validate does. Rubocop, puppet lint

From the root directory of your provider, run the following command: ```pdk validate```. It will return output similar to the below.

TODO: update the following mess.

```
pdk (INFO): Running all available validators...
[✔] Checking metadata syntax (metadata.json tasks/*.json).
[✔] Checking module metadata style (metadata.json).
[✔] Checking Puppet manifest syntax (**/**.pp).
[✔] Checking Puppet manifest style (**/*.pp).
[✖] Checking Ruby code style (**/**.rb).
info: task-metadata-lint: ./: Target does not contain any files to validate (tasks/*.json).
warning: puppet-lint: manifests/temp.pp:2:14: indentation of => is not properly aligned (expected in column 10, but found it in column 14)
warning: puppet-lint: manifests/temp.pp:3:14: indentation of => is not properly aligned (expected in column 10, but found it in column 14)
warning: rubocop: lib/puppet/provider/temp/temp.rb:10:11: Lint/UnderscorePrefixedVariableName: Do not use prefix `_` for a variable that is used.
```

The PDK can automatically fix some warnings, such as Rubocop warnings. Run ```pdk validate -a``` to have warnings auto fixed. After executing that command you will get output such as the below:

TODO: update the following mess.

```
pdk (INFO): Running all available validators...
[✔] Checking metadata syntax (metadata.json tasks/*.json).
[✔] Checking module metadata style (metadata.json).
[✔] Checking Puppet manifest syntax (**/**.pp).
[✔] Checking Puppet manifest style (**/*.pp).
[✖] Checking Ruby code style (**/**.rb).
info: task-metadata-lint: ./: Target does not contain any files to validate (tasks/*.json).
corrected: puppet-lint: manifests/temp.pp:2:14: indentation of => is not properly aligned (expected in column 10, but found it in column 14)
corrected: puppet-lint: manifests/temp.pp:3:14: indentation of => is not properly aligned (expected in column 10, but found it in column 14)
warning: rubocop: lib/puppet/provider/temp/temp.rb:10:11: Lint/UnderscorePrefixedVariableName: Do not use prefix `_` for a variable that is used.
corrected: rubocop: lib/puppet/provider/temp/temp.rb:11:21: Style/StringLiterals: Prefer single-quoted strings when you don't need string interpolation or special symbols.
```

