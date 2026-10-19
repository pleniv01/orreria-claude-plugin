# Orreria for Claude

Orreria is a participatory, noncommercial place directory of ecology, weather, season, myth, culture and environmental memory. This development candidate connects Claude to its existing place-reading engine as a first way into that directory. Start with a named public locality in the United States or Canada, choose the intended match, then read it and inspect its sources.

**Live release candidate; not submitted.** The read-only endpoint is enabled. Every tool has passed fresh production calls through the official MCP SDK and MCP Inspector 2.11.0, including strict schema validation. Public documentation: [Orreria for Claude](https://orreria.com/connector/).

## Example prompts

- Give me an Orreria reading for Deer Isle, Maine.
- What should I notice about Montreal's landscape and season?
- Which parts of that reading are documented, and which are interpretation?
- Find Portland and let me choose which one before making a reading.

## Participation

People can contribute corrections, source leads and local knowledge through [Help Build Orreria](https://orreria.com/help-build). Contributions are reviewed before affecting readings; this connector does not automatically submit, edit or publish them. Orreria is not a restaurant ranking service or shopping directory. Possible future Buck's ingredient links in foodways are outside this connector's first release and would need clear disclosure.

## How it works

`find_place` returns supported public place matches and temporary IDs. `read_place` generates a current reading and returns selected summary, ecology, season/weather and folklore sections. `get_reading_sources` retrieves bounded citation metadata for that exact reading. It does not fetch the referenced websites.

The tools do not accept GPS coordinates, historical dates, personal reflections, customer accounts or files. Readings are not saved to public Field Notes. Source references are temporary and may expire when the server restarts; a new search/reading supplies new references. Version one requires a single server process/replica because references are held in process memory.

Regional models do not prove local species presence. Weather can be heuristic fallback and is not a safety forecast. Folklore is source-qualified interpretation, not prophecy, diagnosis, medical treatment or foraging identification. Source metadata does not itself establish rights to redistribute every underlying record.

## Data and privacy

Read the [connector privacy notice](https://orreria.com/connector/privacy.html). The declared connector receives the public place query, selected temporary IDs and optional section/limit choices. It uses the existing geocoding and weather services; AI text synthesis is separately opt-in on the server. No skills send data to a separate connector or third-party tool.

## Connect and test

Claude web/desktop/mobile: add `https://shape-production.up.railway.app/mcp` as a custom connector and select **No sign in**. No API key or custom headers are needed.

Claude Code, from a checkout of this plugin repository:

```sh
claude --plugin-dir /absolute/path/to/orreria-claude-plugin
```

Try the example prompts above. Inspector and SDK verification is recorded in [VERIFICATION.md](VERIFICATION.md); owner-run testing inside Claude and directory submission remain separate steps.

Support: [support@orreria.com](mailto:support@orreria.com). The bundled square icon uses Orreria’s existing owner-supplied logo. Directory acceptance and owner-run Claude testing remain separate from automated verification.

## License

The MIT [license](LICENSE) covers the plugin code, skills and documentation. The Orreria name and logo identify this integration; trademark rights are reserved. The license does not cover the application or third-party source datasets.
