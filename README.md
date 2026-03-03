<p align="center">
  <!-- <img src="docs/source/assets/logos/persona-bench-logo.png" alt="PERSONA-Bench" width="400"> -->
  <h1 align="center">PERSONA-Bench</h1>
</p>

<h3 align="center">
Personal Environment for Reasoning over Synthesized Observations, Narratives & Activities
</h3>

<p align="center">
  <a href="https://github.com/zhadyz/PERSONA-Bench/blob/main/LICENSE">
    <img alt="License" src="https://img.shields.io/badge/License-Apache%202.0-blue.svg">
  </a>
</p>

---

PERSONA-Bench is an AI safety benchmark that evaluates how well large language models reason about **individual people** — their preferences, constraints, routines, and social relationships — when making everyday decisions on their behalf (shopping, scheduling, medication reminders, etc.).

The benchmark provides a **statistically representative synthetic population** of 100 personas whose demographics align with U.S. Census distributions. Each persona includes:

- **Demographics** — age, gender, race/ethnicity, education, income, location
- **Personality** — Big Five (OCEAN) traits drawn from a normal distribution
- **Social network** — relationships organized by Dunbar's layers (intimate / close / social / active)
- **Taboos & constraints** — food allergies, health conditions, religious/political sensitivities, personal conflicts — all matching U.S. prevalence rates
- **Activity logs** — daily routines correlated with personality traits and ATUS time-use data
- **App logs** — simulated data from messenger, calendar, review, and social apps

## Getting Started

### Requirements

- Python 3.10+

### Quick Start

```bash
# Clone the repository
git clone https://github.com/zhadyz/PERSONA-Bench.git
cd PERSONA-Bench

# Load the dataset
python -c "import json; data = json.load(open('data/social_world.json')); print(f'{len(data[\"personas\"])} personas loaded')"
```

### Regenerating the Dataset

```bash
python generate_personas.py
```

This produces `social_world.json` with 100 personas, ~130 groups, ~770 facts, ~600 activities, and ~1700 app log entries.

## Dataset Structure

```
data/social_world.json
├── personas[]          # 100 synthetic individuals
│   ├── demographics    # Census-aligned attributes
│   ├── personality     # Big Five (OCEAN) scores
│   ├── social_network  # Dunbar-layered relationships
│   ├── taboos          # Allergies, health, religion, politics, conflicts
│   ├── activities      # Daily routines & hobbies
│   └── app_logs        # Simulated app interactions
└── groups[]            # ~130 social groups (local + online)
```

## Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details on how to get started.

All contributors must sign off their commits in accordance with the [Developer Certificate of Origin (DCO)](DCO).

## Citation

If you use PERSONA-Bench in your research, please cite:

```bibtex
@misc{persona-bench,
  title   = {PERSONA-Bench: Personal Environment for Reasoning over Synthesized Observations, Narratives \& Activities},
  author  = {Bari, Abdul},
  year    = {2026},
  url     = {https://github.com/zhadyz/PERSONA-Bench}
}
```

## Contact

- Abdul Bari — [abari@sfsu.edu](mailto:abari@sfsu.edu)

## License

PERSONA-Bench is released under the [Apache 2.0 License](LICENSE).
