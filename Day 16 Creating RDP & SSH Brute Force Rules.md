# Day 16: Creating RDP & SSH Brute Force Rules
## 1. Introduction

**Goal**: Review authentication logs from the Windows server and create a Brute Force alert.

## 2. Query Logs for RDP Brute Force Activity

**Steps**:

1. Log into Elasticsearch and click on the hamburger icon > **Discover**.
2. Set the time frame to "Today".
3. Filter for the Windows server by clicking on the agent name (e.g., `Challenge-WIN-Haji`).

## 3. Identify Key Fields

**Fields to Track**:

1. **Failed Attempts**: Look for failed authentication attempts (Event ID 4625)
2. **User**: Identify the user attempting to log in.
3. **Source IP**: Determine the source IP of the authentication attempts.

## 4. Filter for Failed Attempts

- **Steps**:
    1. Search for Event ID 4625 in the logs.
    2. Confirm the field name is `event.code`.
    3. Add `source.ip` and `user.name` fields to the table.
    4. Verify the data by expanding the first event and checking the message.

## 5. Save the Query

**Steps**:

Save the query as `Challenge RDP failed activity`.

## 6. Create Alert

- **Steps**:
    1. Click on the **Alerts** tab and select **Create Search Threshold Rule**.
    2. Name the alert (e.g., `my df- RDP Brute Force activity - <your_handle>`).
    3. Set the threshold (e.g., greater than 5 failed attempts within 5 minutes).
    4. Test the query to ensure it matches documents.
    5. Save the rule.

## 7. Create Detailed Detection Rule

- **Steps**:
    1. Click on **Detection Rules** and select **Create New Rule**.
    2. Choose **Threshold** as the rule type.
    3. Use the custom query from the saved search and add `user.name` and `source.ip` fields.
    4. Group by `user.name` and `source.ip`.
    5. Name the rule (e.g., `my dfir SSH Brute Force attempt - <your_handle>`).
    6. Set the severity to medium and configure advanced settings if needed.
    7. Schedule the rule to run every 5 minutes.
    8. Create and enable the rule.

## 8. Test the Rule

- **Steps**:
    1. Perform a brute force attack to generate alerts.
    2. Check the alerts for detailed information such as username and source IP.