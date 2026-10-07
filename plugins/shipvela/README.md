# Shipvela

Publish websites with the Shipvela remote OAuth MCP connector and the `publish` skill. Source: [stefanautomateed/shipvela-codex](https://github.com/stefanautomateed/shipvela-codex), public client commit `a9a843732c1d1e01a5ac60c25a8239f36351918a`, plugin 0.2.0. The hosted service is proprietary and requires a Shipvela account.

## Install

```text
/plugin marketplace add hekmon8/awesome-claude-code-plugins
/plugin install shipvela@awesome-claude-code-plugins
```

Alternatively, use the maintained source marketplace:

```text
/plugin marketplace add stefanautomateed/shipvela-codex
/plugin install shipvela@shipvela-beta
```

Complete OAuth through Claude's MCP connection flow. Keep tool approvals enabled. No AWS, GitHub or payment credentials belong in the plugin configuration.

Ask Claude to publish a website. The skill checks compatibility and the intended target, stages public files or uses a connected repository, and asks the account owner to confirm publishing in Shipvela. The assistant must never approve its own review link. Inspect the exact deployment until success before calling it live.

Hobby includes 3 projects and 20 publishes per month. Larger plans are optional; hosting is not unlimited free. Direct MCP staging supports at most 500 KB and 100 public files with a root `index.html`. Larger built output uses the separately authorized CLI or GitHub flow. Domains and HTTPS are included; domain registration is separate. See [supported frameworks and limits](https://shipvela.com/docs).

Access is revocable in Shipvela Settings. The connector has no billing modification, project deletion or environment-secret read tool.

License: MIT; the copied client instructions/configuration retain their included LICENSE. New catalog prose follows the catalog's CC0 license. Maintainer: Content Petit LLC / hello@shipvela.com.
