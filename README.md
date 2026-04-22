**Windows Security Logon Event Review Lab**

I built this hands-on Windows Server lab in Oracle VM VirtualBox to practice reviewing Windows Security logs following both successful and failed authentication attempts. My lab shows how Event Viewer records failed login attempts, how successful logins appear nearby in the log, and how comparing timestamps helps explain what happened during authentication.

Lab Objectives
- Open Event Viewer and review Windows Security logs
- Filter Security logs by Event ID 4625
- Identify failed login attempts
- Record the event time to locate nearby authentication activity
- Compare failed login events with successful login events
- Interpret the authentication sequence inside the Security log
- Virtual Lab Environment

I built this lab in Oracle VM VirtualBox using Windows Server 2022 to create an isolated practice environment. This shows how a virtual machine can support security log review and authentication troubleshooting.

Failed Login Event Review

I filtered the Security log by Event ID 4625 after intentionally creating a failed login attempt. This showed how Windows records failed authentication activity and labels it as an audit failure. I used the filtered view to isolate failed login attempts before returning to the full Security log for comparison.

<img src="images/Event ID 4625 Failed Login.png" alt="Event ID 4625 Failed Login" width="700"/>

Authentication Timeline Verification

After identifying the failed login event, I recorded the event time in a notebook and returned to the full Security log to locate related authentication activity. I compared the failed login event at 8:28:08 PM with the successful login event at 8:28:17 PM.

The failed login appeared first as Event ID 4625, followed 9 seconds later by Event ID 4624, which confirmed successful authentication.

This showed how timestamp comparison helps explain whether failed authentication was followed by normal user access.

<img src="images/Event ID 4624 Successful Login Timeline.png" alt="Event ID 4624 Successful Login Timeline" width="700"/>

Event Sequence Interpretation

The failed login event appeared first, followed by successful authentication a few seconds later. Other nearby events, such as logoff, special logon, and credential validation, appeared in the same sequence.

This showed how one login attempt can generate multiple related security events inside the log.

The timing pattern suggested normal user behavior: an incorrect password attempt followed shortly by a successful login.

Skills Practiced
- Windows Event Viewer navigation
- Security log filtering
- Failed authentication review
- Successful login verification
- Timestamp comparison
- Authentication sequence analysis

Summary

This lab demonstrates practical Windows security log review in a virtual environment. It shows how failed login events can be identified, compared with nearby successful authentication events, and interpreted as part of normal troubleshooting in an IT support environment.

Navigation

[`Back to GitHub Profile`](https://www.github.com/cbueker-it)


