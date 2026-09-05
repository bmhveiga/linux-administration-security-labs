# 04 — Linux Security & Server Hardening

Hands-on Linux security lab focused on applying initial hardening measures to a web service running on Ubuntu Server.

This activity builds on the web-service deployment completed in Topic 03 and shifts the focus from simply publishing a service to understanding its exposure, reducing unnecessary risk, and validating that the service remains operational after security changes.

---

## Objective

The objective of this activity was to apply initial security measures to the Linux web service published in Topic 03.

The work focused on:

- identifying active services and open ports
- understanding the server's attack surface
- reviewing and documenting firewall rules
- proposing and applying initial hardening measures
- validating that the web service remained accessible
- publishing technical evidence safely on GitHub

---

## Environment

- **Operating System:** Ubuntu Server
- **Web Server:** Nginx
- **Service:** Static HTML website
- **Remote Administration:** SSH
- **Firewall:** UFW
- **Web Protocol:** HTTP
- **Documentation:** GitHub / Markdown

---

## Service Analyzed

The service analyzed in this activity was a simple HTML website published with Nginx on Ubuntu Server.

This service had already been deployed in the previous lab and was used as the basis for the security and hardening work.

The objective was not to redesign the application, but to examine the Linux server hosting it from a security perspective.

---

## Security Workflow

The activity followed a simple security-review process:

~~~text
Published Web Service
        ↓
Identify Services & Ports
        ↓
Analyze Attack Surface
        ↓
Review Firewall Rules
        ↓
Apply / Propose Hardening
        ↓
Validate Service
        ↓
Document Evidence
~~~

---

## Attack Surface

The first stage involved identifying which services and ports were exposed by the server.

The purpose was to understand which components could potentially be reached by users or external systems.

This included reviewing:

- active services
- listening ports
- SSH access
- web-service exposure
- firewall configuration

The analysis is documented in:

~~~text
superficie-ataque.md
~~~

---

## Firewall Review

The firewall configuration was reviewed and documented using UFW.

The objective was to confirm that required traffic remained available while avoiding unnecessary exposure.

The firewall documentation is available in:

~~~text
firewall.md
~~~

Typical validation included reviewing the current firewall state and configured rules.

Example:

~~~bash
sudo ufw status verbose
~~~

---

## Initial Hardening

The activity also included proposing and applying initial server-hardening measures.

The goal was to reduce unnecessary exposure while preserving the functionality required by the web service.

The hardening work is documented in:

~~~text
hardening.md
~~~

The focus was on practical first steps rather than advanced production hardening.

---

## Service Validation

After reviewing and applying security measures, the web service was tested again.

This was important because security changes should not unintentionally prevent legitimate users from accessing the service.

Validation focused on confirming that:

- the Linux server remained accessible
- the required services remained operational
- the web service continued to respond
- the security changes did not break the published service

The validation process is documented in:

~~~text
validacao.md
~~~

---

## Repository Structure

~~~text
04-linux-security-hardening/
├── superficie-ataque.md
├── firewall.md
├── hardening.md
├── validacao.md
├── comandos.txt
├── evidencias/
└── README.md
~~~

Each file documents a specific part of the security-review process.

---

## Evidence

The main technical evidence for the activity is stored in:

~~~text
evidencias/topico-04-validacao-seguranca.txt
~~~

The evidence was collected from the Linux server and used to support the security analysis and validation.

---

## Commands

Commands used during the activity are documented in:

~~~text
comandos.txt
~~~

This keeps the technical work separate from the explanatory documentation while making the process easier to review and reproduce.

---

## Security Documentation

An important part of this activity was documenting technical evidence without exposing sensitive information.

The repository was reviewed to avoid publishing:

- passwords
- private SSH keys
- authentication tokens
- credentials
- other sensitive system information

This reflects an important principle when documenting real infrastructure publicly.

---

## Skills Practiced

- Linux server administration
- Linux security fundamentals
- service and port identification
- attack-surface analysis
- UFW firewall review
- server hardening concepts
- web-service validation
- SSH and remote administration
- technical troubleshooting
- security documentation
- safe handling of technical evidence

---

## Key Takeaway

This lab introduced the transition from service deployment to service security.

Instead of asking only:

~~~text
"Is the web service working?"
~~~

the activity also considered:

~~~text
What services are exposed?
Which ports are open?
What does the firewall allow?
What is the server's attack surface?
What can be hardened?
Does the service still work after the changes?
~~~

The lab reinforced that Linux administration involves not only deploying services, but also understanding their exposure, applying security controls, validating changes, and documenting the environment safely.
