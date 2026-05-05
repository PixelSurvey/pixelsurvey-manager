# 🚀 PixelSurvey Usage Environment

Welcome to the **PixelSurvey Usage Environment**. This repository serves as your workspace to create, manage, and run surveys using the `pixelsurvey-core` engine. 

By keeping the core engine as a Git submodule, this structure ensures a clean separation between the survey generation engine and your specific research data (recipes and generated surveys).

---

## 📁 Repository Structure

```text
core-usage/
├── pixelsurvey-core/    # The main survey generation engine (Git submodule)
├── recipes/             # Directory for your YAML survey configurations
├── surveys/             # (Generated) Output directory for created Dash surveys
├── requirements.txt     # Python dependencies needed for the core engine
└── run.py               # Helper script to manage your surveys
```

---

## 🛠️ Initial Setup
Follow these steps to set up your environment for the first time:

### 1. Clone the repository
Make sure to include the `--recursive` flag to pull the `pixelsurvey-core` submodule along with this repository.

```bash
git clone --recursive https://github.com/PixelSurvey/core-usage.git
cd core-usage
```

### 2. Set up the Python Environment
We highly recommend using a virtual environment to avoid dependency conflicts.

```bash
# Create a virtual environment named .psenv
python -m venv .psenv

# Activate the virtual environment (macOS/Linux)
source .psenv/bin/activate

# Install the required dependencies
pip install -r requirements.txt
```

---

## 🏗️ Generating a Survey
To generate a new Dash survey application from a YAML recipe, use the core generator. Make sure your YAML recipe is placed in the `recipes/` folder.

```bash
# Ensure your virtual environment is active
source .psenv/bin/activate

# Generate the survey
python -m pixelsurvey_core.survey_gen <survey_id>
```

**Example:**
```bash
python -m pixelsurvey_core.survey_gen homes-example
```
*This will read your recipe and generate a new Dash app inside the `surveys/` directory.*

---

## ▶️ Running a Generated Survey (Debug Mode)

Once your survey is generated, you can run it locally to test the flow and verify the design before deployment.

```bash
# Navigate to the newly generated survey directory
cd surveys/<survey_id>

# Run the Dash application
python app.py
```

**Example:**
```bash
cd surveys/survey-homes-example
python app.py
```

Then, open your web browser and navigate to `http://127.0.0.1:8050/` (or the port specified in the terminal) to preview your survey!

---
*Built for research with [PixelSurvey](https://github.com/PixelSurvey/pixelsurvey-core).*

