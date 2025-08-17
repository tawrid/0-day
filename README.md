Daily Vulnerability Report 🛡️
This repository hosts a daily, automated vulnerability report. A GitHub Actions workflow runs a Python script every day at 6 AM NZST to fetch the latest 0-day vulnerabilities from the National Vulnerability Database (NVD) and publishes them as a clean, navigable GitHub Page.

The goal is to provide a simple, self-updating site that keeps a historical record of recent vulnerabilities, allowing for easy browsing by date.

Features
Daily Automation: The report is automatically generated every day using a scheduled GitHub Actions workflow.

0-Day Vulnerability Tracking: Fetches up-to-date vulnerability data from the NVD API.

Historical Archive: All daily reports are saved and organized by year, month, and day, creating a browsable archive.

GitHub Pages: The generated reports are automatically synced and published to a user-friendly website.

Simple Navigation: The website includes a dynamic sidebar that allows for easy navigation through the historical reports.

How It Works
Scheduled Trigger: A GitHub Actions workflow is scheduled to run daily at 6 AM NZST (which is 18:00 UTC).

API Call: The vulnerability_reporter.py script makes an API request to the NVD to find all Common Vulnerabilities and Exposures (CVEs) published in the last 24 hours.

HTML Generation: The script dynamically generates an HTML file for the daily report, including basic styling and a simple layout. It then injects a navigation sidebar with links to all existing reports.

Commit & Push: The workflow commits the newly generated HTML files to the repository. The GitHub Actions bot handles the commit and push, ensuring the repository stays synchronized.

GitHub Pages: With each new commit, GitHub Pages automatically rebuilds and deploys the site, making the new daily report available online.

Getting Started
Prerequisites
A GitHub account.

A new or existing GitHub repository to host the project.

Setup
Fork this repository (or create a new one).

Add the Python Script: Create a file named vulnerability_reporter.py in the root of your repository and paste the Python code into it.

Add the GitHub Workflow: Create the necessary directory structure .github/workflows/ and add the daily-job.yml file. Paste the workflow code into this file.

Enable GitHub Pages: Go to your repository's Settings -> Pages. Select Deploy from a branch and choose the main branch. The site will be published from the root directory (/).

The workflow will run automatically at the scheduled time. You can also trigger a manual run at any time from the Actions tab of your repository.

Project Structure
/
├── .github/
│   └── workflows/
│       └── daily-job.yml      # The GitHub Actions workflow file
├── _data/                     # Directory for generated reports
│   └── reports/
│       └── <year>/
│           └── <month>/
│               └── <day>/
│                   └── index.html # The daily report
├── vulnerability_reporter.py  # The Python script
└── README.md                  # This file

Contributing
We welcome contributions! Feel free to open an issue or submit a pull request if you have ideas for improvements, bug fixes, or new features.
