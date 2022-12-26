# Beeper UI Client (generator)

Used to generate the client-side TypeScript types and service functions from the OpenAPI specification.

**DO NOT** modify any generated files!
Treat the generated package as a build artifact.
If you need to change the way the models or API functions work, _change the OpenAPI spec and regenerate_.

Ideally, this generator is paired with generating the implementation structure in the API service itself.
When done correctly, this allows type safety and versioning around an otherwise-unchecked boundary in AJAX: the lack of cross-HTTP schemas in JSON.

## Usage

Run the `generate_api.sh` script to generate the UI client package.
This script uses the OAS file `../beeper-oas.yaml` and the `generator-config.yaml` to create a new NPM package named `beeper-ui-client`.

## Consuming the API Client

The generated NPM package contains two important directorys: `src/apis/` and `src/models/`.

The `models` directory contains TypeScript interfaces that represent the types defined in the OpenAPI spec.
Ideally, these should be used within the UI to pass API-oriented data around.
They _must_ be used with the API functions.

The `apis` directory contains the generated functions for calling the API.
The models and available methods are all based on the OpenAPI spec.
