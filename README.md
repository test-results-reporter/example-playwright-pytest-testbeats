# Example Playwright Pytest Project with TestBeats Integration

This is an example project demonstrating how to run Playwright tests with Pytest and report results, presumably to TestBeats.

## Setup

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd <repository-directory>
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv .venv
    source .venv/bin/activate
    ```

3.  **Install dependencies:**
    This project uses `uv` for dependency management.
    ```bash
    uv sync pyproject.toml
    ```

4.  **Install Playwright browsers:**
    ```bash
    playwright install
    ```

## Running Tests

To run the tests, use Pytest:

```bash
pytest --output=reports --screenshot=only-on-failure --junitxml=reports/junit.xml
```

This will execute the tests found in files like `test_example.py`.

## Reporting Results to TestBeats

This project is configured to generate a JUnit XML report, which is a common format for test reporting tools like TestBeats.

1.  **Generate JUnit XML report:**
    Pytest can generate a JUnit XML report using the `--junitxml` flag.
    ```bash
    pytest --junitxml=reports/junit.xml
    ```

    Make sure the `reports` directory exists, or create it:
    ```bash
    mkdir -p reports
    ```

2.  **Upload to TestBeats:**
    The method for uploading `reports/junit.xml` to TestBeats depends on your specific TestBeats setup. This typically involves:
    *   Using a TestBeats CLI tool.
    *   A CI/CD integration that automatically picks up the report.

    Please refer to the TestBeats documentation for the specific command or procedure to upload the JUnit XML file.

    **Example (conceptual - replace with actual TestBeats command):**
    ```bash
    npx testbeats@latest publish --slack <slack-webhook-url> --junit reports/junit.xml
    ```

## Contributing

Please feel free to submit issues and pull requests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details, which mentions TestBeats.
