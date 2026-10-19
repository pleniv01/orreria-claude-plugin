# Release verification

October 19, 2026. Release candidate 0.1.0; not submitted or directory-approved.

- Live endpoint: https://shape-production.up.railway.app/mcp
- Streamable HTTP; no sign in, credentials, API key or custom headers.
- Official SDK: find_place, read_place and get_reading_sources passed fresh calls for Deer Isle (Maine), Montreal (Quebec) and Taos (New Mexico). Returned local timezones were America/New_York, America/Toronto and America/Denver.
- MCP Inspector 2.11.0: strict tool-schema validation passed; all three tools passed fresh production calls.
- Source data arrives in full JSON text and structured content, including citations and evidence limits.
- Final live trials returned Open-Meteo model weather. An earlier shared-quota limit was handled with seasonal fallback; weather source is now explicitly disclosed even in summary-only readings. Local timezone resolution is independent of the weather provider.
- Aggregate public-reading/contributor-event counts were unchanged across the production trials. Server-side generative AI processing was disabled.
- Plugin manifest validation, application build, provider-control/timezone tests and existing cultural-review verifiers passed. Runtime configuration targets Node 24 LTS.
- Automated browser visual testing was unavailable in this session. Inspector tests are not a claim that the owner has already tested the package inside Claude.

Public documentation and privacy: https://orreria.com/connector/ and https://orreria.com/connector/privacy.html. Directory terms and rights/provenance attestations remain the owner's responsibility. This receipt is technical verification, not an acceptance guarantee.
