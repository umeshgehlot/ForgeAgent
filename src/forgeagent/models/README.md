# Model integrations

Model implementations provide the interface used by an agent to send conversation messages to a language model and format its responses.

The package includes integrations for LiteLLM, OpenRouter, Portkey, and Requesty, along with response-based and text-based variants and deterministic test models. Provider-specific models may require extra packages and credentials; see the individual implementation and the [model documentation](https://forgeagent.com/latest/reference/models/overview/) for configuration details.

Most users only need the default LiteLLM integration, configured through a model name and the provider settings described in the [quick start](https://forgeagent.com/latest/quickstart/).
