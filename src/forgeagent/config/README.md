# Packaged configuration

This package ships YAML configuration files used by the run scripts. The top-level configs include `default.yaml`, `mini.yaml`, and the text-based mini configuration. The `benchmarks/` directory contains SWE-bench variants and ProgramBench settings.

Configuration selects the agent, model, environment, prompts, and run limits. Users can override settings on the command line or with their own YAML file. See the [configuration guide](https://forgeagent.com/latest/advanced/yaml_configuration/) and [global configuration documentation](https://forgeagent.com/latest/advanced/global_configuration/) for supported fields and precedence.
