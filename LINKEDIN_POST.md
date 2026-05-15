In my LearningSteps Lockdown project, I hardened a FastAPI application in Azure by putting identity, reverse proxying, private database access, HTTPS, and edge protections in front of it.

The core challenge was not enabling individual controls in isolation. It was making them work together correctly: Microsoft Entra ID for token-based access, `oauth2-proxy` for validation, Nginx for reverse proxying and TLS, PostgreSQL in a more isolated backend tier, and additional protections such as rate limiting and ModSecurity-based filtering.

What made the project valuable was seeing how small integration details affected the actual security outcome. Correct `401`, `403`, and `200` behavior, trusted token issuers, proxy placement, and backend exposure all mattered.

This project strengthened my understanding of a practical cloud security principle: security posture depends less on the number of controls you enable and more on whether identity, network, application, and edge protections are aligned and verified end to end.

That is the kind of work I find most interesting in cybersecurity: turning layered controls into a system that behaves securely under real conditions.

#cybersecurity #azure #cloudsecurity #entra #apigateway #oauth2 #devsecops