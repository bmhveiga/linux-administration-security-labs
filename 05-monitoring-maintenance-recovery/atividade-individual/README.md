# 05 — Linux Monitoring, Backup & Recovery

Hands-on Linux operations lab focused on monitoring system health, reviewing logs, validating a web service, creating backups, testing recovery, and documenting a basic continuity plan.

This activity builds on the previous Linux deployment and hardening labs by focusing on the ongoing operation and recoverability of a running Ubuntu Server environment.

---

## Objective

The objective of this activity was to monitor the state of the Linux system, investigate logs, create a backup, test a recovery process, and define a simple operational continuity plan.

The work focused on:

- monitoring system resources
- checking web-service availability
- reviewing recent logs
- identifying relevant system events
- performing basic maintenance checks
- creating a backup
- restoring the backup into a test location
- documenting a simple continuity strategy

---

## Environment

- **Operating System:** Ubuntu Server
- **Critical Service:** Nginx
- **Web Service:** Static HTML website
- **Remote Administration:** SSH
- **Service Management:** systemd / `systemctl`
- **Logging:** Linux system and service logs
- **Backup:** Linux archive tools
- **Documentation:** GitHub / Markdown

---

## Critical Service

The primary service analyzed in this activity was Nginx.

Nginx was being used to publish a simple HTML website on the Ubuntu Server environment created in the earlier labs.

The activity focused on confirming that the service remained healthy and understanding how to respond if the service or its data became unavailable.

---

## Operational Workflow

The activity followed a basic systems-operations cycle:

~~~text
Monitor
   ↓
Check Services
   ↓
Review Logs
   ↓
Perform Maintenance
   ↓
Create Backup
   ↓
Test Recovery
   ↓
Plan Continuity
~~~

This represents the transition from deploying and securing a server to actively operating and maintaining it.

---

## System Monitoring

The server was monitored to understand its current operational state.

The monitoring work included checks such as:

- system uptime
- memory usage
- disk usage
- service status
- web-service availability

The monitoring documentation is available in:

~~~text
monitorizacao.md
~~~

Typical Linux monitoring commands include:

~~~bash
uptime
free -h
df -h
systemctl status nginx
~~~

These checks provide a quick overview of whether the server has sufficient resources and whether important services are operational.

---

## Service Monitoring

The state of the Nginx service was checked as part of the operational validation.

Example:

~~~bash
systemctl status nginx
~~~

This helps identify whether the service is:

- active
- inactive
- failed
- experiencing startup or runtime problems

Service monitoring is especially important when the application depends on a specific daemon remaining available.

---

## Log Review

Logs were reviewed to identify recent system and service events.

The log-analysis work is documented in:

~~~text
logs.md
~~~

Logs can provide information about:

- service errors
- startup problems
- authentication activity
- system events
- unexpected application behavior

Reviewing logs is an important part of troubleshooting because they provide evidence about what happened before and during a failure.

---

## Maintenance

Basic maintenance checks were also performed on the Linux environment.

The maintenance work is documented in:

~~~text
manutencao.md
~~~

The objective was to reinforce that a server requires ongoing operational attention after deployment.

Maintenance may include reviewing areas such as:

- system health
- service status
- available disk space
- system updates
- logs
- configuration state

---

## Backup

A backup of the web-service data was created as part of the activity.

The backup process is documented in:

~~~text
backup-recuperacao.md
~~~

A backup artifact is also included in the evidence:

~~~text
evidencias/backup-web-nginx-topico-05.tar.gz
~~~

The purpose was to practice preserving important service data so that it could be recovered if the original files were lost or damaged.

---

## Recovery Test

The activity did not stop after creating the backup.

The backup was restored into a separate test directory to confirm that the archived data could actually be recovered.

This is important because:

~~~text
A backup that has never been tested
is not a verified recovery solution.
~~~

The recovery test helped validate that:

- the backup file could be opened
- the expected content was present
- the data could be restored
- the recovery procedure was understandable and repeatable

---

## Continuity Planning

A simple operational continuity plan was documented in:

~~~text
continuidade.md
~~~

The objective was to consider what should happen if the web service became unavailable.

The continuity approach considered areas such as:

- identifying the critical service
- detecting a failure
- reviewing service status and logs
- restoring data when required
- validating the service after recovery
- documenting the recovery process

A simplified continuity workflow can be represented as:

~~~text
Service Failure
      ↓
Confirm Problem
      ↓
Check Service Status
      ↓
Review Logs
      ↓
Identify Cause
      ↓
Restore / Correct
      ↓
Validate Service
      ↓
Return to Operation
~~~

---

## Repository Structure

~~~text
05-monitoring-maintenance-recovery/
└── atividade-individual/
    ├── monitorizacao.md
    ├── logs.md
    ├── manutencao.md
    ├── backup-recuperacao.md
    ├── continuidade.md
    ├── comandos.txt
    ├── evidencias/
    └── README.md
~~~

Each file documents a different part of the operational administration process.

---

## Evidence

The main technical evidence is stored in:

~~~text
evidencias/topico-05-monitorizacao-logs.txt
evidencias/topico-05-backup-recuperacao.txt
evidencias/topico-05-manutencao-continuidade.txt
evidencias/backup-web-nginx-topico-05.tar.gz
~~~

These files provide supporting evidence for the monitoring, log analysis, maintenance, backup, recovery, and continuity work completed during the lab.

---

## Commands

Commands used during the activity are documented in:

~~~text
comandos.txt
~~~

Keeping a command record makes the operational process easier to review and repeat.

---

## Security Considerations

Technical evidence was reviewed before being published publicly.

The repository avoids exposing:

- passwords
- private SSH keys
- authentication tokens
- credentials
- other sensitive system information

This is especially important when publishing server logs, command output, configuration information, and backup-related documentation.

---

## Skills Practiced

- Linux server administration
- system monitoring
- resource monitoring
- Nginx service monitoring
- Linux log review
- troubleshooting
- system maintenance
- backup creation
- recovery testing
- operational continuity planning
- technical documentation
- safe handling of infrastructure evidence

---

## Key Takeaway

This activity reinforced that deploying and securing a Linux server is only part of systems administration.

A running service must also be:

~~~text
Monitored
   ↓
Maintained
   ↓
Investigated when problems occur
   ↓
Backed up
   ↓
Recoverable
   ↓
Supported by a continuity plan
~~~

The most important lesson was that operational reliability depends not only on keeping a service running, but also on being able to understand failures and recover from them.
