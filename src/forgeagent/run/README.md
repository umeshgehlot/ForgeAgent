# Run scripts

The `forgeagent.run` package contains executable entry points that assemble an agent, model, and environment for interactive use, examples, or benchmarks.

## Local examples and CLI

- `hello_world.py` — minimal example using the default agent.
- `mini.py` — interactive command-line application. Installed as `mini` and `forgeagent`.
- `utilities/` — supporting CLI tools, including the extra command and trajectory inspector.

## Benchmarks

Benchmark runners live in `benchmarks/`:

- `swebench.py` — batch SWE-bench runs.
- `swebench_single.py` — run a single SWE-bench instance.
- `programbench.py` — run ProgramBench tasks.

Runner-specific YAML settings are packaged under `forgeagent/config/benchmarks/`. Consult the [usage documentation](https://forgeagent.com/latest/) for required datasets, model credentials, and environment backends before running benchmarks.
