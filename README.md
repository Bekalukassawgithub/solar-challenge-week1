1. Environment Setup
To reproduce the development environment:

Clone the Repository
git clone <repository-url>
cd solar-challenge-week1
Create a Virtual Environment
Using venv
python -m venv .venv
 HEAD
source .venv/Scripts/activate  # (Git Bash/Windows)
source .venv/bin/activate      # (Mac/Linux)

source .venv/Scripts/activate  # (Git Bash/Windows)
source .venv/bin/activate      # (Mac/Linux)
setup-task
Using Conda (Alternative)

conda create --name my_env python=3.9
conda activate my_env
Install Dependencies
pip install -r requirements.txt
2. Git Workflow
Branching & Commits
Create a new branch for setup tasks

git checkout -b setup-task
Make at least 3 commits

git add .gitignore
git commit -m "init: add .gitignore"

git add requirements.txt
git commit -m "chore: venv setup"

git add .github/workflows/ci.yml
git commit -m "ci: add GitHub Actions workflow"
Push Changes

git push origin setup-task
Merge the Branch
Create a Pull Request in GitHub.

Title: "Setup task"

Description: "This PR adds the.gitignore,requirements.txt, and GitHub Actions workflow configuration."

Merge setup-task into main.

3. Continuous Integration (CI)
GitHub Actions Workflow (.github/workflows/ci.yml)
This workflow ensures dependencies are installed and Python version is verified.

yaml
name: Basic CI

on:
 HEAD
  push:
    branches:
      - main
      - setup-task
  pull_request:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v3

      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.9'

      - name: Verify Python version
        run: python --version

      - name: Install dependencies
        run: pip install -r requirements.txt

  push:
    branches:
      - main
      - setup-task
  pull_request:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v3

      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.12'

      - name: Verify Python version
        run: python --version

      - name: Install dependencies
        run: pip install -r requirements.txt
setup-task

4. Key Performance Indicators (KPIs)
Development Environment Setup: Ensures smooth installation and execution of dependencies.

 HEAD
Version Control & CI/CD: Maintains structured commits and automated testing with GitHub Actions.


Version Control & CI/CD: Maintains structured commits and automated testing with GitHub Actions.
setup-task
