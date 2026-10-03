<div align="center">
<a href="https://forgeagent.com/latest/"><img src="https://github.com/SWE-agent/ForgeAgent/raw/main/docs/assets/forgeagent-banner.svg" alt="ForgeAgent banner" style="height: 7em"/></a>
</div>

# ForgeAgent — Autonomous AI Software Engineering Agent

ForgeAgent is a compact, extensible AI software-engineering agent. It gives a language model a task, lets it run shell commands through an execution environment, and feeds command output back into a simple agent loop. The project is designed to make the control flow easy to inspect and adapt.

This checkout is **v2**. Users upgrading from v1 should read the [migration guide](https://forgeagent.com/latest/advanced/v2_migration/).

- Documentation: <https://forgeagent.com/latest/>
- PyPI: <https://pypi.org/project/forgeagent/>
- Issues: <https://github.com/SWE-agent/forgeagent/issues>

## Install and run

Install the command-line tool in an isolated environment with `uv`:

```bash
pip install uv
uvx forgeagent
```

Or install it in the active Python environment:

```bash
pip install forgeagent
mini
```

To install this checkout in editable mode for development:

```bash
python -m pip install -e '.[dev]'
mini
```

The project requires Python 3.10 or later. Configure model credentials and defaults using the [quick start](https://forgeagent.com/latest/quickstart/) and [global configuration guide](https://forgeagent.com/latest/advanced/global_configuration/). Model providers and supported environment backends may require optional credentials, packages, or runtimes.

## Use from Python

The core pieces can be assembled directly in Python:

```python
from forgeagent.agents.default import DefaultAgent
from forgeagent.environments.local import LocalEnvironment
from forgeagent.models.litellm_model import LitellmModel

agent = DefaultAgent(model=LitellmModel(model_name="openai/gpt-4o-mini"), env=LocalEnvironment())
result = agent.run("Describe the files in the current repository")
```

Review the [Python bindings cookbook](https://forgeagent.com/latest/advanced/cookbook/) before running an agent on a repository. The local environment executes commands on the host; use an appropriate sandbox for untrusted tasks.

## Design and package layout

- `src/forgeagent/agents/` — default and interactive agent loops
- `src/forgeagent/environments/` — local, Docker, and Singularity command execution; additional backends are optional
- `src/forgeagent/models/` — LiteLLM, OpenRouter, Portkey, Requesty, and response/text-based model integrations
- `src/forgeagent/run/` — CLI, hello-world example, utilities, and benchmark runners
- `src/forgeagent/config/` — packaged agent and benchmark configuration files
- `tests/` — unit and integration tests
- `docs/` — user and API documentation (built with MkDocs)

The package defines protocols for agents, models, and environments. Run scripts combine implementations of those interfaces for the CLI, examples, and benchmarks.

## Development

Install the development extras and run the test suite:

```bash
python -m pip install -e '.[dev]'
pytest -n auto
```

Some tests require optional backends or external services. Fire tests are opt-in with `--run-fire` and can make paid model API calls; do not enable them unless that is intended.

Lint and check formatting with:

```bash
ruff check .
ruff format --check .
```

Build the documentation with the development dependencies using MkDocs. See [contributing](https://forgeagent.com/latest/contributing/) for the full contributor workflow.

## Related resources

- [CLI usage](https://forgeagent.com/latest/usage/mini/)
- [SWE-bench runner](https://forgeagent.com/latest/usage/swebench/)
- [ProgramBench runner](https://forgeagent.com/latest/usage/programbench/)
- [Configuration files](https://forgeagent.com/latest/advanced/yaml_configuration/)
- [FAQ](https://forgeagent.com/latest/faq/)

## License and attribution

See [LICENSE.md](LICENSE.md). For the project's research background and citation guidance, refer to the [SWE-agent paper](https://arxiv.org/abs/2405.15793).
