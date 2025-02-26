# Day 13: Installing Elastic Agent on SSH Server

## 1. Introduction

**Goal**: Install Elastic Agent on SSH server to query logs in Elasticsearch.
## 2. Create Agent Policy

**Steps**:

1. Log into Elasticsearch web GUI.
2. Click on the hamburger icon > **Fleet** under **Management**.
3. Click on **Agent Policy** > **Create Agent Policy**.
4. Name the policy (e.g., `Challenge-Linux-Policy`).
5. Click on **Create Agent Policy**.

## 3. Configure Policy

**Steps**:

1. Select the system integration (e.g., `system-3`).
2. Verify the log paths (e.g., `/var/log/auth*` for Ubuntu).
3. Confirm the policy covers Debian, Ubuntu, Red Hat, and CentOS (`/var/log/secure*`).

## 4. Enroll Agent

**Steps**:

1. Click on **View All Agent Policies** > **Agents**.
2. Click on **Add Agent**.
3. Select the policy created (e.g., `Challenge-Linux-Policy`).
4. Choose **Enroll in Fleet** and select **Linux tar**.
5. Edit the `SOC Simulation` Firewall to add a rule that allow `Challenge-Linux-Steve` to communicate with `Challenge-ELK` on port 9200.
6. Copy the command and run it in the SSH session on `Challenge-Linux-Steve`
7. Add `--insecure` flag if using a self-signed certificate.

## 5. Verify Installation

**Steps**:

1. Confirm agent enrollment and incoming data in Elasticsearch.
2. Click on the hamburger icon > **Discover**.
3. Filter by agent name to view logs from the SSH server.
4. Search for specific events (e.g., authentication failures).

## 6. Analyze Logs

**Steps**:

1. Use the `grep` command to filter logs for failed authentication attempts on `Challenge-Linux-Steve` SSH session.
2. Use the `cut` command to extract IP addresses.

```
grep -i failed auth.log | grep -i root | cut -d ' ' -f 11
```

1. Add relevant fields to the table in Elasticsearch for easier analysis.

