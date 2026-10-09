# Study Assistant — Starter

A starter repository for the CSC10014 Smart Virtual Assistant project.

## Prerequisites

Before setting up the project, make sure you have:

- Python 3.10 or newer
- Git
- A GitHub account
- SSH configured for GitHub

You can check your installed versions with:

python --version
git --version

## Setup

Clone the repository:

git clone git@github.com:phkhoiit-1508/lab01-phkhoiit-1508.git
cd lab01-phkhoiit-1508

Create a Python virtual environment:

### macOS / Linux

python -m venv .venv
source .venv/bin/activate

### Windows PowerShell

python -m venv .venv
.venv\Scripts\Activate.ps1

When the virtual environment is active, you should see (.venv) at the beginning of your terminal prompt.

Upgrade pip:

python -m pip install --upgrade pip

Install the required dependencies:

pip install -r requirements.txt

Install the project in editable mode:

pip install -e .

## Run

Run the assistant with a question:

python -m assistant "where is the IT helpdesk?"

Expected output:

text
IT Helpdesk: room E.005, open Mon-Fri 08:00-17:00.

You can also run the assistant in interactive mode:

python -m assistant

Example:

text
Study assistant (starter). Type 'quit' to exit.

> hi
> Hello! Ask me where an office is, or when it opens.
> quit

## Test

Run the automated tests:

pytest -q

Expected result:

text
4 passed

## Check the Environment

Run the environment checker:

python scripts/check_env.py

The goal is for every check to show:

text
[ OK ]

## Project Structure

text
lab01-phkhoiit-1508/
├── README.md
├── pyproject.toml
├── requirements.txt
├── src/
│ └── assistant/
├── data/
│ └── offices.csv
├── tests/
│ └── test_smoke.py
├── docs/
├── ui/
├── scripts/
│ └── check_env.py
└── .gitignore

- src/assistant/ — application source code
- tests/ — automated tests
- data/ — small, non-sensitive sample data
- docs/ — project documentation
- ui/ — user interface files and plans
- scripts/ — helper scripts
- requirements.txt — pinned Python dependencies
- pyproject.toml — Python project configuration and metadata
- .gitignore — files and folders that Git should not track

## Troubleshooting

### No module named assistant

Make sure the virtual environment is active:

source .venv/bin/activate

Then reinstall the project:

pip install -e .

### Packages are installed into the wrong virtual environment

Leave the current virtual environment:

deactivate

Then activate the virtual environment inside this repository:

source .venv/bin/activate

You can verify the active environment with:

python -c "import sys; print(sys.prefix)"

The path should end with:

text
lab01-phkhoiit-1508/.venv

### VS Code uses the wrong Python interpreter

Open the Command Palette:

text
Cmd + Shift + P

Then select:

text
Python: Select Interpreter

and choose the interpreter inside .venv.

### PowerShell blocks Activate.ps1

Run:

Set-ExecutionPolicy -Scope CurrentUser RemoteSigned

Then activate the environment again:

.venv\Scripts\Activate.ps1
