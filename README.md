# Puppet Resource API Hands on Lab

In this lab we'll go through how to create a Puppet module that uses the Resource API. Puppet modules are components that are used to manage resources, for example configuring a web server. Puppet provides a number of built-in resource types, such as package, service, file, user - full list available [here](https://puppet.com/docs/puppet/5.3/type.html). Puppet provides the ability for developers to add their own resource types so that additional resources can be managed.

This requires the developer to create types and providers. Traditionally this was considered difficult and the code required was considered cumbersome. The Resource aims to make this an easier process.

## What you'll learn
* How to create a Puppet module using the [Puppet Development Kit](https://puppet.com/download-puppet-development-kit)
* How to write types and providers that extend Puppet's ability to manage resources
* How to manage remote resources that have no Puppet agent installed

## What you'll need
* A computer on which you have access to install software.

## Audience
The intended audience for this tutorial is Puppet module developers. There is no need to write code as part of the tutorial - code samples are provided throughout.

## Types and Providers
Before we start let's start by explaining types and providers.
* Types define data that is being managed. Types are most easily thought of as properties of a resource that is being managed. Types have attributes. For example, ```user``` is a built-in Puppet type that has attributes of name, password, user id etc.
* Providers are functions that allow types to be manipulated. An example of a provider is a ```get``` function. It enables data to be retrieved from a resource and populates the type with that data.

Using types and providers mean that your modules will benefit from the power of Puppet, so native Puppet capability such as idempotency will be inherited automatically.

> Let's get started [01 Install Prerequisites](./01-install-prerequisites)
