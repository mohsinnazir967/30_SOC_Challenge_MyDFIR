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

**Steps**:

1. Search for Event ID 4625 in the logs.
2. Confirm the field name is `event.code`.
3. Add `source.ip` and `user.name` fields to the table.
4. Verify the data by expanding the first event and checking the message.

## 5. Save the Query

**Steps**:

Save the query as `Challenge RDP failed activity`.

## 6. Create Alert

**Steps**:

1. Click on the **Alerts** tab and select **Create Search Threshold Rule**.
2. Name the alert (e.g., `Challenge Failed RDP alert`).
3. Set the threshold (e.g., greater than 5 failed attempts within 5 minutes).
4. Test the query to ensure it matches documents.
5. Save the rule.

## 7. Create Detailed Detection Rule for RDP

**Steps**:

1. Click on **Rules** and select **Create New Rule**.
2. Choose **Threshold** as the rule type.
3. Use the custom query from the saved search

```
event.code:4625 AND agent.name:"Challenge-WIN-Haji" and user.name:"Administrator" 
```

4. In the `Group by` add `user.name` and `source.ip` fields.
5. For the required field also add these two `user.name` and `source.ip`.
6. Name the rule (e.g., `Challenge-RDP-Brute-Force-Attempt-Haji`).
7. Set the severity to medium and configure advanced settings if needed.
8. Schedule the rule to run every 5 minutes.
9. Create and enable the rule.

## 8. Create Detailed Detection Rule for RDP

**Steps**:

1. Click on **Rules** and select **Create New Rule**.
2. Choose **Threshold** as the rule type.
3. Use the custom query from the saved search

```
system.auth.ssh.event : * and agent.name:"Challenge-Linux-Steve" and system.auth.ssh.event : "Failed" AND user.name:"root" 
```

1. In the `Group by` add `user.name` and `source.ip` fields.
2. For the required field also add these two `user.name` and `source.ip`.
3. Name the rule (e.g., `Challenge-SSH-Brute-Force-Attempt-Steve`).
4. Set the severity to medium and configure advanced settings if needed.
5. Schedule the rule to run every 5 minutes.
6. Create and enable the rule.

## 8. Test the Rule

**Steps**:

1. Perform a brute force attack to generate alerts.
2. Check the alerts for detailed information such as username and source IP.

[Day 16 Creating RDP & SSH Brute Force Rules](Day%2016%20Creating%20RDP%20&%20SSH%20Brute%20Force%20Rules.md)