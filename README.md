# RBAnalytics
Place holder for Runbook Automation Analytics job
Clealy overkill for one job, but this will serve as a placeholder for any future Runbook Projects.

Import the .json file to a Runbook Automation/Rundeck/Process Automation server.

# Automation Job Execution Report

This repository contains a Python script that interacts with the Rundeck API to collect job execution data and calculate metrics such as time saved and cost saved. The script is configurable, allowing you to fetch executions over a specified date range, filter jobs by name, and generate summaries in text or HTML format.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Output](#output)
- [License](#license)

## Prerequisites

To run this script, you need the following:

- **Python 3.x** installed.
- The following Python libraries:
  - `requests`
  - `pandas`
  - `tabulate`
  - `re`
  - `datetime`

You can install the required dependencies using pip:

```bash
pip install requests pandas tabulate
```

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/automation-job-execution-report.git
   cd automation-job-execution-report
   ```

2. Install the required Python packages:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Configure the script** by adjusting the variables at the top of the script:
   - `DAYS_RANGE`: Number of days to fetch executions from.
   - `API_TOKEN`: Your Rundeck API token.
   - `BASE_URL`: The Rundeck API base URL.
   - `ROI_BASE_URL`: The ROI data API base URL.
   - `TEST_PROJECTS`: List of project names to process. Leave `None` to process all projects.
   - `JOB_NAME_FILTER`: Regular expression pattern to filter job names. Set `None` to include all jobs.
   - `AVERAGE_SALARY_PER_HOUR`: Average salary per hour to calculate cost savings.

2. **Run the script**:
   ```bash
   python job_execution_report.py
   ```

3. The script will fetch job executions from Rundeck, calculate ROI metrics, and generate a report in the specified output format (`html` or `text`).

## Configuration

You can modify the following key configuration variables in the script:

- **API Configuration**:
  - `BASE_URL`: The Rundeck API base URL.
  - `API_TOKEN`: Your Rundeck API token.

- **Execution Range**:
  - `DAYS_RANGE`: Number of days to fetch job executions for.

- **Output Options**:
  - `OUTPUT_FORMAT`: Can be set to `'text'` or `'html'` for different output formats.

- **Job Filtering**:
  - `JOB_NAME_FILTER`: A regular expression to filter job names by pattern. Leave it as `None` to include all jobs.

## Output

The script will produce a summary table of job executions, including:

- Project name
- Job name
- Execution status (success or failure)
- Total execution time
- ROI metrics such as time saved and cost saved

### Example Output (Text)

```text
🚀 Automation Job Digest 🚀
===============================
📅 Date Range: Last 7 Days
Average Salary per Hour: $50.0

📊 Total Projects: 3
📋 Total Jobs: 12
✅ Successful Executions: 25
❌ Failed Executions: 5

⏱️ Total Timesaved (minutes): 1500
💵 Total Cost Associated with Time Saved ($): 1250.00
```

### Example Output (HTML)

In HTML format, the summary is displayed in a table format with full details, including total time saved and cost saved for each job.

## License

This project is licensed under the [MIT License](LICENSE).
