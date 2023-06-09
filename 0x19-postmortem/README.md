# Postmortem: Web Stack Outage on June 9, 2023

### Duration: June 9, 2023, 10:00 AM to 11:30 AM (GMT)

## Issue Summary
Web application service experienced intermittent outages and severe performance degradation, resulting in slow response times and partial unavailability. Approximately 30% of users were affected during the outage.

## Timeline (GMT)
10:00 AM: The issue was initially detected by an engineer who noticed increased latency and intermittent errors in the application logs. 
10:30 AM: After detailed investigation, it was discovered that the database servers were experiencing unusually high connection timeouts. 
11:00 AM: Upon reviewing the database connection pool settings, the misconfiguration was identified as the root cause. 
11:15 AM: The misconfiguration was corrected, and the database connection pool was optimized to handle incoming requests efficiently. 
11:30 AM: The application service was fully restored, and response times returned to normal.

## Root Cause
The root cause of the outage was a misconfiguration in the database connection pool settings. The configuration allowed only a limited number of connections, leading to a bottleneck and increasing connection timeouts. This resulted in slow response times and intermittent outages.

## Resolution
To resolve the issue, the database connection pool settings were adjusted to allow a higher number of connections, ensuring adequate resources were available to handle incoming requests. Additionally, database server performance was optimized to enhance response times and minimize connection timeouts.

## Corrective and Preventative Measures
* Perform regular audits of critical system configurations to identify potential misconfigurations and address them proactively. 
* Enhance monitoring capabilities to include alerts for abnormal connection timeouts and database performance metrics. 
* Implement automated testing of the application's performance and scalability to identify bottlenecks before they impact production. 
* Conduct thorough code reviews to ensure proper handling of database connections and resource utilization. 

Sincerely,


Desmond Afari.

