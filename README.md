[![Open in GitHub Codespaces](
  https://img.shields.io/badge/Open%20in%20GitHub%20Codespaces-333?logo=github)](
  https://codespaces.new/dwave-examples/anneal-schedule-notebook?quickstart=1)
[![Linux/Mac/Windows build status](
  https://circleci.com/gh/dwave-examples/anneal-schedule-notebook.svg?style=shield)](
  https://circleci.com/gh/dwave-examples/anneal-schedule-notebook)

# Anneal Schedule

This notebook explains and demonstrates the global anneal scheduling features.
These features can improve solutions to a problem and provide insight into the
behaviour and dynamics of problems undergoing quantum annealing.

*anneal schedule* refers to the global annealing trajectory. It specifies the
normalized anneal fraction, ``s``, an abstract parameter ranging from 0 to 1.
``s(t)`` is a continuous function starting at ``s=0`` for time ``t=0``
and ending with ``s=1`` at ``t=t_f``, the total time of the anneal.

There are two ways to specify the anneal schedule, using two
*mutually exclusive* parameters:

1.  ``annealing_time``: Set to a number in microseconds to specify linear growth
    from ``s=0`` to ``s=1`` over that time.
2.  ``annealing_schedule``: Specify a list of ``(t, s)`` pairs specifying
    points, which are then linearly interpolated. This feature supports two
    modes&mdash;mid-anneal pause and mid-anneal quench&mdash;which this tutorial
    explores.

The notebook has the following sections:

1.  **Understanding the Anneal Schedule** explains the feature.
2.  **Using Anneal Schedule Features** shows how to use the feature with an
    interactive example problem.
3.  **Mapping Various Anneal Schedules** provides code that sweeps through
    various anneal schedules to explore the effect on results.

![pause](images/pause_success_fraction.png)

## Installation

You can run this example without installation in cloud-based IDEs that support
the [Development Containers specification](https://containers.dev/supporting)
(aka "devcontainers").

For development environments that do not support ``devcontainers``, install
requirements:

    pip install -r requirements.txt

If you are cloning the repo to your local system, working in a
[virtual environment](https://docs.python.org/3/library/venv.html) is
recommended.

## Usage

Your development environment should be configured to
[access Leap’s Solvers](https://docs.dwavequantum.com/en/latest/ocean/sapi_access_basic.html).
You can see information about supported IDEs and authorizing access to your Leap
account [here](https://docs.dwavequantum.com/en/latest/leap_sapi/dev_env.html).

The notebook can be opened by clicking on the ``01-anneal-schedule.ipynb`` file
in VS Code-based IDEs.

To run a locally installed notebook:

```bash
jupyter notebook
```

## License

See [LICENSE](LICENSE.md) file.
