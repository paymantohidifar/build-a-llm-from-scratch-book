## Project Initialization and Environment Configuration

The project structure was initialized using the `uv init` command, establishing a modern Python standards-compliant foundation. The default `pyproject.toml` file was subsequently customized to manage three distinct dependency tiers: **Main**, **Development**, and **Bonus**.

To maintain a lean and performant project state, dependencies were strategically partitioned into these groups, ensuring the core environment remains uncluttered. The local virtual environment was then synchronized and populated specifically for advanced features using:

```bash
uv sync --group bonus

```

This approach ensures that only the necessary overhead is introduced while maintaining a reproducible and version-locked environment.