# LearningSteps Lockdown

This repository documents an end-to-end cloud and API security project built around a FastAPI application hosted in Azure.

The project focuses on one practical goal: reduce direct exposure, enforce identity-aware access, and validate that the application behaves securely from the public entry point to the backend data tier.

The public version of this repository uses sanitized infrastructure identifiers and placeholders so the implementation can be shared without exposing tenant-specific metadata.

## Project Summary

LearningSteps Lockdown hardens a public-facing API by layering identity, reverse proxying, transport security, backend isolation, and edge protections.

The final design combines:

- Microsoft Entra ID for API identity
- `oauth2-proxy` for bearer-token validation
- Nginx for reverse proxying and HTTPS termination
- Azure PostgreSQL Flexible Server in a private backend tier
- rate limiting and ModSecurity-based request filtering

## Architecture

The project architecture is summarized in [images/linkedin-architecture-diagram.png](images/linkedin-architecture-diagram.png).

## Outcomes

- Anonymous access returned `401 Unauthorized`
- Invalid bearer tokens returned `403 Forbidden`
- Valid bearer tokens returned `200 OK`
- Direct public access to the backend database tier was removed
- Edge protections were added in front of the application path

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
- `images/linkedin-architecture-diagram.mmd` - Mermaid source for the architecture diagram
- `images/linkedin-architecture-diagram.png` - PNG export for GitHub and LinkedIn use


## Scope Note

This repository currently contains the project documentation artifacts. The full application source tree used on the VM is not included here.

That means the strongest evidence in this repository is the security design, validation logic, troubleshooting path, and implementation runbook rather than a full application codebase.

## Public Sharing Note

This repository is intended to be safe to share publicly.

- Tenant-specific IDs, IP addresses, and environment identifiers have been replaced with placeholders.
- Secret values are documented as placeholders only.
- The runbook remains technically accurate while omitting deployment-specific metadata.
