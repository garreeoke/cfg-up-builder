# Upbound Builder Configuration

This repository contains the Upbound Builder configuration to use with [Crossplane](https://crossplane.io/).
 
## APIs

There is one CompositeResourceDefinition (XRD) definition in this configuration. 
- **Builder**: Front-end to all the builders that can be built.

## Builders

Builders are sets of Crossplane compositions to standardize and consolidate the way cloud services are built. Using builders will reduce
the amount of configuration code needed by up to 50% or more.

Think of builders like a helper function in a programming language. Instead of writing the same code hundreds of times in multiple places
a function is used instead. It is the same with builders. 

## Compositions

For general info on creating compositions, see [Crossplane documentation](https://crossplane.io/docs/v1.10/reference/composition.html).

For a builder, a composition is selected based off of the selector. The selector has four items.
- builder: The builder type to use (i.e - iam).
- cloud: The cloud for the composition (currently only aws is available).
- service: The service within the cloud (i.e- s3)
- config: The configuration used.

We are building more compositions to cover as many basic configurations as possible.
See below for links to README's on specific clouds.

* [aws](./builders/iam/aws)

## Usage

### Pre-Requisites
To install `up` run this install script:
```console
curl -sL https://cli.upbound.io | sh
```

See [up docs](https://docs.upbound.io/cli/) for more install options.

### Install the configuration
Find latest version of [IamBuilder](https://marketplace.upbound.io/configurations/garreeoke-org/builder/) on the marketplace
```console
up ctp configuration install xpkg.upbound.io/garreeoke-org/builder:v0.0.1
```

### Using the API
See the examples directory for some examples of how to make a claim for
different configurations.

#### Notes
- Composition name is composed of config.cloudService.cloud.builder.upbound.io