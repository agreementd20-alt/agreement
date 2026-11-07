# POD Engineering architecture

## Responsibilities
- **Floot** — operational application, authentication, design/revision database and engineering job records.
- **GitHub** — source control, reviews, CI configuration and integration contracts.
- **Hercules** — optional development companion; not yet integrated.
- **FreeCAD/CalculiX workers** — planned CAD generation and structural FEA, not yet deployed.

## Engineering job lifecycle
1. Authenticated user submits an immutable design revision.
2. Server validates parameter bounds and creates a queued job.
3. Authorized isolated worker retrieves the job and performs actual computation.
4. Worker stores immutable artifacts, tool versions, units, checksums and logs.
5. Qualified engineer reviews results; manufacturing release requires approval.

## Safety and data integrity
No conceptual drawing, simplified calculation or unvalidated simulation is a certified engineering result. Do not automatically approve structural, hydraulic, axle-load or roadworthiness compliance. Apply revision locks, audit logs, least-privilege service authentication and signed worker callbacks.

## Current limitations
GitHub write access is verified, but Floot source export/synchronization, Hercules linkage and solver workers are not yet configured.
