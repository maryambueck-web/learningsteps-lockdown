# LearningSteps Lockdown

This repository documents an end-to-end cloud and API security lab built around a FastAPI application hosted in Azure.

The project demonstrates practical work across identity, reverse proxying, database isolation, HTTPS hardening, rate limiting, and web application firewall controls. The repository contains the implementation runbook and final documentation used to build and verify the environment.

The public version of this repository uses sanitized infrastructure identifiers and placeholders so the implementation can be shared without exposing tenant-specific metadata.

## Project Highlights

- Secured a FastAPI API with Microsoft Entra ID and `oauth2-proxy`
- Enforced token-based access with correct `401`, `403`, and `200` behavior
- Migrated application data to Azure PostgreSQL Flexible Server
- Rebuilt the database tier with private networking and restored data from backup
- Put Nginx in front of the API for HTTPS termination and reverse proxying
- Added edge protections including rate limiting and ModSecurity-based request filtering

## Skills Demonstrated

- Azure infrastructure and platform services
- Microsoft Entra ID application registration and token validation
- OAuth2 / OIDC proxy integration
- FastAPI deployment and service management with `systemd`
- PostgreSQL backup, restore, and private connectivity
- Nginx reverse proxy configuration
- HTTPS and TLS setup
- WAF and request filtering with ModSecurity
- Command-line troubleshooting across macOS and Linux
- Technical documentation and reproducible runbooks

## Repository Contents

- `LearningSteps-Lockdown-API-Security-Runbook.md` - sanitized implementation runbook with commands, troubleshooting notes, and verification steps
- `LINKEDIN_POST.md` - LinkedIn-ready project summary for public sharing
- `images/linkedin-architecture-diagram.mmd` - Mermaid source for a simple architecture diagram

## Why This Repository Exists

This repository is meant to show the ability to design, implement, troubleshoot, and document a realistic API security setup rather than only describe it at a high level.

It reflects hands-on work with:

- securing public access paths
- isolating backend services from direct exposure
- validating identity and token flows
- migrating data into a private database tier
- applying layered edge protections in front of an application

## Scope Note

This repository currently contains the project documentation artifacts. The full application source tree used on the VM is not included here.

## Public Sharing Note

This repository is intended to be safe to share publicly.

- Tenant-specific IDs, IP addresses, and environment identifiers have been replaced with placeholders.
- Secret values are documented as placeholders only.
- The runbook remains technically accurate while omitting deployment-specific metadata.
