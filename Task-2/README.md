# Task 2 — GitHub Morning Brief Automation

An n8n workflow that discovers popular AI-related GitHub repositories, retrieves README metadata, and stores the results in Google Sheets.

## Workflow components

- Schedule Trigger — hourly execution
- GitHub REST API — repository search
- Code node — selects top five repositories
- IF node — checks stars greater than 1,000
- HTTP Request — retrieves README metadata
- Merge and Code nodes — combine and format data
- Google Sheets — stores the final results

## Error Handling

The README request continues using regular output when an API request fails.

## Deliverables

See the workflow JSON and screenshots in this folder.
