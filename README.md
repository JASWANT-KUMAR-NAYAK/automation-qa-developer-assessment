# GitHub Morning Brief Automation

## Overview

An n8n workflow that automatically discovers popular AI-related GitHub
repositories, enriches them with README information, and records the
results in Google Sheets.

## Workflow

1.  **Schedule Trigger:** Starts the workflow hourly.
2.  **GitHub API:** Searches repositories under the
    `artificial-intelligence` topic, sorted by stars.
3.  **Code Node:** Sorts the results and selects the top five
    repositories.
4.  **IF Node:** Checks whether repository stars exceed 1,000.
5.  **README API:** Retrieves README metadata for qualifying
    repositories.
6.  **Merge Node:** Combines repository details with README information.
7.  **Code Node:** Formats the final records, including repository URLs,
    README status, priority, and timestamp.
8.  **Google Sheets:** Appends the five records to the
    `GitHub Morning Brief` spreadsheet.

## Error Handling

The README request uses the **Continue (using regular output)**
error-handling option. This allows the workflow to continue when README
retrieval fails, rather than stopping the entire execution.

## Output

The Google Sheet stores: - Repository name and description - Stars and
programming language - Repository and README URLs - README size and
availability status - Priority and generation timestamp

## Configuration

-   Platform: n8n
-   Data source: GitHub REST API
-   Output: Google Sheets
-   Authentication: Google Sheets OAuth2 credentials configured in n8n
-   Schedule: Hourly

## Testing

The workflow was executed successfully. The latest recorded execution
completed in approximately 6.07 seconds and appended five repository
records to Google Sheets.

## Files

-   `GitHub_Morning_Brief_Automation.json` --- Workflow export
-   `Task2_Workflow_Canvas.png` --- Workflow canvas screenshot
-   `Task2_Successful_Execution.png` --- Successful execution screenshot
