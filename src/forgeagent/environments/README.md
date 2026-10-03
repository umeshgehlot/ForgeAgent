# Execution environments

An environment executes the shell actions produced by an agent and returns their output. Choose an environment based on the isolation and infrastructure required by the task.

## Core implementations

- `local.py` — runs commands on the local machine; convenient for trusted tasks, but not an isolation boundary.
- `docker.py` — executes commands in Docker or Podman containers.
- `singularity.py` — executes commands using Singularity or Apptainer.

## Optional backends

Additional integrations, including Swerex Docker/Modal, Bubblewrap, and ConTree, are available in the package's extra environment modules. They may require optional dependencies or external services. Consult the [environment guide](https://forgeagent.com/latest/advanced/environments/) for installation and configuration details.
