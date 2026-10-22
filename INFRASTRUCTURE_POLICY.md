# Infrastructure and Deployment Standard

**Effective: 2026-10-22**

## Canonical runtime

When this repository has deployable web applications, APIs, or background workers, their **canonical target** is the owned Linux VPS running Docker containers. Use Coolify to manage builds, deployment, domains, runtime configuration, restarts, and previews when technically appropriate. GitHub remains the source of truth for code and CI validation.

Cloudflare may continue to provide DNS, R2, Workers, queues, or edge integrations when those specific capabilities are beneficial; such integrations do not make an externally hosted application runtime the default.

**Migration safety:** Do not claim an application has already moved or disable its existing production runtime merely because this policy has been adopted. Inventory current deployments, implement equivalent Docker/Coolify configuration, secure credentials, establish automated off-server backups and test restore, run health checks and functional smoke tests, compare rollback paths, and obtain explicit release approval before cutover.

Avoid new third-party application-hosting dependencies. When a limitation occurs, evaluate the owned VPS first and document trade-offs. Keep individual products and customer data isolated on shared infrastructure.
