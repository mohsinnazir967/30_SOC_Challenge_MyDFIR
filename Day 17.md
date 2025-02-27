# Day 17: Creating a Dashboard for RDP Activity

## 1. Introduction

**Goal**: Learn how to create a dashboard focusing on RDP activity generated from a Windows server and table visualization.

**Task**: Create a map similar to the SSH activity map, but focusing on Windows Server authentication attempts related to RDP and create table visualization.

## 3. Steps to Create the Dashboard

### 3.1 Initial Setup

- **Navigate to Elastic web GUI**: Click on the hamburger icon and select Maps.
- **Query Setup**: Use the saved search query for event code `4625` (failed logins) and agent name.

### 3.2 Adding a Layer

- **Add Layer**: Click on Add Layer, select Choropleth, and choose World Countries for the EMS boundary.
- **Data View**: Select alerts and join field `source.geo`.
- **Country ISO Code**: Use the country ISO code for the abbreviation.

### 3.3 Saving the Map

- **Save Map**: Title it "RDP Failed Authentication".
- **Add to Dashboard**: Select the existing dashboard "my dfir-authentication-das-activity".

## 4. Creating a Query for Successful Authentications

### 4.1 Modify Query

- **Event Code**: Change from `4625` to `4624` for successful logins.
- **Logon Types**: Focus on logon types `10` and `7`.

### 4.2 Save and Add to Dashboard

- **Save Query**: Title it "RDP Successful Activity".
- **Duplicate Dashboard**: Duplicate the existing dashboard and update the query.

## 5. Enhancing the Dashboard

### 5.1 Adding a Table

- **Fields to Include**: Time, source IP, username, and country.
- **Save Searches**: Create saved searches for both failed and successful activities.

### 5.2 Finalizing the Dashboard

- **Add Table to Dashboard**: Include the table with usernames, source IPs, and country names for quick reference.

## 6. Creating Visualizations

### 6.1 SSH Failed Activity Table

- **Create Visualization**: Click on Create Visualization and select Table.
- **Add Fields**: Include timestamp, source IP, username, and country name.
- **Configure Rows**: Set top values to 10 and uncheck "group remaining values as other".
- **Sort Records**: Sort by count of records in descending order.
- **Save Visualization**: Title it "SSH Failed Activity (Table)".

### 6.2 SSH Successful Activity Table

- **Duplicate Visualization**: Duplicate the SSH failed activity table.
- **Update Title**: Change to "SSH Successful Authentications".
- **Modify Query**: Update the query to focus on successful authentications.

### 6.3 RDP Failed Activity Table

- **Duplicate Visualization**: Duplicate the SSH failed activity table.
- **Update Title**: Change to "RDP Failed Authentications".
- **Modify Query**: Update the query to focus on RDP failed authentications.

### 6.4 RDP Successful Activity Table

- **Duplicate Visualization**: Duplicate the RDP failed activity table.
- **Update Title**: Change to "RDP Successful Authentications".
- **Modify Query**: Update the query to focus on RDP successful authentications.

## 7. Finalizing the Dashboard

- **Review and Save**: Ensure all visualizations are correctly configured and save the dashboard.
- **Summary**: The dashboard now includes visualizations for both SSH and RDP failed and successful authentications.

## 8. Conclusion

**Next Steps**: In the next video, the focus will be on command and control tactics and the Mythic framework.

**Giveaway**: Details about a giveaway for the My DFIR for SOC Analyst course and TryHackMe passes.

Day 18: Advanced Dashboard Customization

If you need any further assistance or additional notes, feel free to ask!