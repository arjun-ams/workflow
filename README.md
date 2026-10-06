# Sample GitHub Workflow

This repository contains a simple GitHub Actions workflow that outputs test metadata.

## Workflow File

Create `.github/workflows/sample-workflow.yml` with the following content:

```yaml
name: Sample Workflow

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]
  workflow_dispatch:

jobs:
  run-tests:
    runs-on: ubuntu-latest

    outputs:
      test_case_id: ${{ steps.test-step.outputs.test_case_id }}
      test_artifact_name: ${{ steps.test-step.outputs.test_artifact_name }}
      test_artifact_filename: ${{ steps.test-step.outputs.test_artifact_filename }}

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Run sample test and set outputs
        id: test-step
        run: |
          echo "test_case_id=TC-001" >> $GITHUB_OUTPUT
          echo "test_artifact_name=Login Test Report" >> $GITHUB_OUTPUT
          echo "test_artifact_filename=login-test-report.html" >> $GITHUB_OUTPUT

      - name: Print outputs
        run: |
          echo "Test Case ID: ${{ steps.test-step.outputs.test_case_id }}"
          echo "Test Artifact Name: ${{ steps.test-step.outputs.test_artifact_name }}"
          echo "Test Artifact Filename: ${{ steps.test-step.outputs.test_artifact_filename }}"
```

## Sample Output Values

| Output Key             | Sample Value              | Description                          |
|------------------------|---------------------------|--------------------------------------|
| `test_case_id`         | `TC-001`                  | Unique identifier for the test case  |
| `test_artifact_name`   | `Login Test Report`       | Human-readable name of the artifact  |
| `test_artifact_filename` | `login-test-report.html` | File name of the generated artifact  |
