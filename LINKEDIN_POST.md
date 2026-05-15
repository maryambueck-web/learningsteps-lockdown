In my LearningSteps Lockdown project, I secured a FastAPI application in Azure by combining Microsoft Entra ID, `oauth2-proxy`, Nginx, a private PostgreSQL backend, HTTPS, rate limiting, and ModSecurity-based filtering.

The most useful lesson was that cloud security is rarely about turning on one feature. It is about making identity, proxying, application behavior, and network exposure work together correctly.

What I validated in this project:
- token-based access with correct `401`, `403`, and `200` behavior
- backend isolation so the database was no longer directly reachable from the public internet
- layered controls at the edge instead of relying on the application alone

What stood out most was how much the final security outcome depended on integration details such as trusted token issuers, proxy placement, and which components were actually exposed.

This project gave me a more practical view of cloud security: strong controls matter, but verified end-to-end behavior matters more.

GitHub project: https://github.com/maryambueck-web/learningsteps-lockdown

#cybersecurity #azure #cloudsecurity #entra #oauth2 #devsecops