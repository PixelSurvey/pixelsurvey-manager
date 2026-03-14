# Core Usage

Repository containing `pixelsurvey-core` as a submodule and specific recipes.

## Structure

```
core-usage/
├── pixelsurvey-core/    (Git submodule)
├── recipes/             (Your recipe files)
└── run.py              (Script to run surveys)
```

## Initial Setup

1. **Clone the repo with submodules:**
```bash
git clone --recursive https://github.com/your-org/core-usage.git
cd core-usage
```

2. **Create a Python venv with the rquirements**
```bash
python -m venv .psenv
source .psenv/bin/activate
pip install -r requirements.txt
```

## Usage

```bash
# Run from the core-usage folder
cd core-usage
python -m pixelsurvey_core.survey_gen <survey_id>

# Example:
python -m pixelsurvey_core.survey_gen homes-example
```

## Running the created survey (debug mode)

```bash
# Run it with the psenv
cd surveys/<survey_id>
python app.py

# Example:
cd surveys/survey-homes-example
python app.py
```

