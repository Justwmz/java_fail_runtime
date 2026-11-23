# Failing Java Build Demo

This intentionally broken Maven project is a small input repository for the agent-runtime POC.

## Expected failure

Run:

```bash
mvn verify
```

Both calculator tests fail because `Calculator.add` subtracts the right operand instead of adding it. The intended repair is a one-line change in `Calculator.java`.

## Push to GitHub

Create an empty public GitHub repository, then run:

```bash
git add .
git commit -m "Add intentionally failing Java build"
git remote add origin https://github.com/YOUR_ACCOUNT/YOUR_REPOSITORY.git
git push -u origin main
```

The `Build` GitHub Actions workflow will run automatically and produce a failed workflow run that can be submitted to the agent-runtime UI.

This repository contains no credentials and its workflow only requests read access to repository contents.
