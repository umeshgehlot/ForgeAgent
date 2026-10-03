# Agent implementations

Agents coordinate the model and execution environment. They send the task and history to the model, execute the resulting action, add observations to the history, and stop when the task is complete or a configured limit is reached.

- `default.py` — the standard agent loop.
- `interactive.py` — extends the default workflow with human-in-the-loop interaction.

The [control-flow guide](https://forgeagent.com/latest/advanced/control_flow/) explains the message/action loop and how to customize it.
