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

2. **If you already cloned without submodules:**
```bash
git submodule update --init --recursive
```

## Usage

```bash
# Run from the core-usage folder
cd core-usage
python -m pixelsurvey_core.survey_gen <survey_id>

# Example:
python -m pixelsurvey_core.survey_gen safe-seoul-pilot-en-v1_3
```

## How it Works

- Recipe files go in `core-usage/recipes/`
- Generated surveys are created in `core-usage/surveys/`
- Both paths are configured automatically via `vars.py` in `pixelsurvey-core`
- The submodule ensures you always have the correct version of the generator

## Update pixelsurvey-core

```bash
cd pixelsurvey-core
git pull origin main  # or the branch you use
cd ..
git add pixelsurvey-core
git commit -m "Update pixelsurvey-core submodule"
```
