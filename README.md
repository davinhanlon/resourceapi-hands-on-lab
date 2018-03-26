# resourceapi-hands-on-lab
> Create a Puppet module.

Puppet provides a number of built-in resource types, such as package, service, file, user etc. - all listed online. It is possible to add custom resources to Puppet using Types and Providers, so that users can extend Puppet to manage extra stuff.

This is generally considered a difficult process, with many people avoiding using types and providers in their modules.

The Resource API has been designed and developed with the intention of goal of making it easier to write custom types and providers.

This tutorial will help you write a module that creates a custom type and provider using the Resource API.

Some random notes:

1. Why use types and providers?
⋅⋅⋅Idempotent - only change a certain property.
⋅⋅⋅Prefetch information that is on a system.
2. Type
⋅⋅⋅What properties are available for the configuration.
⋅⋅⋅Make it obvious what it manages.
⋅⋅⋅These have properties and parameters
⋅⋅⋅Properties are modifiable - e.g. user name
⋅⋅⋅Parameter - changes behaviour - e.g. manage home
3. Provider
⋅⋅⋅Know about application, commands, options, parameters. Maybe use a Ruby library.
⋅⋅⋅Methods of the provider are provided to the type.
⋅⋅⋅Mk resource methods - what are they - omit them?
⋅⋅⋅For properties - there should be getters and setters - core concept of puppet - using idempotency. Need to explain this using Resource API specific functions in the lab.
4. Don’t reuse reserved words in types and providers
5. It is possible to extend existing types. Can be many providers to one type. Providers per platforms is possible. Same Puppet code can interact with providers.
6. Types and Providers are best when a CLI or API is required to configure an application (e.g. config files can’t be manipulated directly).

[Install Ruby](./1-install-ruby)
