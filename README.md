**Windows Security Logon Event Review Lab**

I built this hands-on Windows Server lab in Oracle VM VirtualBox to practice reviewing Windows Security logs after failed and successful authentication attempts. My lab shows how Event Viewer records failed login attempts, how successful logins appear nearby in the log, and how comparing timestamps helps explain what happened during authentication.

Lab Objectives
- Open Event Viewer and review Windows Security logs
- Filter Security logs by Event ID 4625
- Identify failed login attempts
- Record the event time to locate nearby authentication activity
- Compare failed login events with successful login events
- Interpret authentication sequence inside the Security log
- Virtual Lab Environment

I built this lab in Oracle VM VirtualBox using Windows Server 2022 to create an isolated practice environment. This shows how a virtual machine can support security log review and authentication troubleshooting.

<img src="images/Windows Server Event Viewer Security Log.png" alt="Windows Server Event Viewer Security Log" width="700"/>

Failed Login Event Review

I filtered the Security log by Event ID 4625 after intentionally creating a failed login attempt. This showed how Windows records failed authentication activity and labels it as an audit failure.

<img src="images/Event ID 4625 Failed Login.png" alt="Event ID 4625 Failed Login" width="700"/>

Authentication Timeline Verification

I wrote down the failed login time and then returned to the full Security log to locate nearby authentication events. This showed how comparing timestamps helps explain whether the failed login was followed by successful authentication.

<img src="images/Event ID 4624 Successful Login.png" alt="Event ID 4624 Successful Login" width="700"/>

Event Sequence Interpretation

The failed login event appeared first, followed by nearby successful authentication activity. This showed how one user action can generate multiple security events inside the log, including failed authentication, credential validation, and successful login.

This sequence suggested normal behavior: a failed password attempt followed by a successful login a few seconds later.

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


