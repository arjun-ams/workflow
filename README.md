# Sample GitHub Workflow

This repository contains a simple GitHub Actions workflow that outputs test metadata.

## Workflow File

The workflow is defined in `.github/workflows/sample-workflow.yml`.

It uploads two artifacts:

1. `README.md` — the repository README file
2. `sample-workflow.yml` — the workflow definition file

## Sample Output Values

| Output Key             | Sample Value              | Description                          |
|------------------------|---------------------------|--------------------------------------|
| `test_case_id`         | `TC-001`                  | Unique identifier for the test case  |
| `test_artifact_name`   | `Login Test Report`       | Human-readable name of the artifact  |
| `test_artifact_filename` | `README.md`               | File name of the generated artifact  |
