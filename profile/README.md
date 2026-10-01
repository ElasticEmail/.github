<div align="center">

<a href="https://elasticemail.com"><img src="https://raw.githubusercontent.com/ElasticEmail/.github/main/profile/hero.jpg" alt="Elastic Email: Email API, SMTP, marketing tools and developer infrastructure" width="100%" /></a>

### Email API and SMTP for developers. Clone a starter, add your API key, send a real email in five minutes.

[![API docs](https://img.shields.io/badge/API-v4%20docs-0A7BBB)](https://elasticemail.com/developers/api-documentation/rest-api)
[![Examples](https://img.shields.io/github/stars/ElasticEmail/elasticemail-examples?logo=github&label=examples)](https://github.com/ElasticEmail/elasticemail-examples)
[![X (Twitter)](https://img.shields.io/badge/follow-%40Elastic__Email-000000?logo=x)](https://x.com/Elastic_Email)

[Starters](#start-from-a-working-project) •
[SDKs](#official-sdks) •
[Tools](#tools-and-integrations) •
[AI agents](#ai-agents) •
[Blog](#from-the-blog) •
[Support](#support)

</div>

---

## Start from a working project

Pick one, clone it, run it. Each starter sends a real email on the first run and is a complete app you can build on.

| Starter | What you get | Stack |
|---|---|---|
| [**Next.js app**](https://github.com/ElasticEmail/elasticemail-examples/tree/main/nextjs-elasticemail-examples) | API routes for sending, batch sends, attachments, templates, webhooks, inbound email and double opt-in, with a page per feature | TypeScript, Next.js 15 |
| [**Python web app**](https://github.com/ElasticEmail/elasticemail-examples/tree/main/python-elasticemail-examples) | The same `/send` API in Flask, FastAPI and Django, plus a single-file script for every feature | Python 3 |
| [**AI agent that sends email**](https://github.com/ElasticEmail/elasticemail-examples/tree/main/ai-agents-elasticemail-examples) | A Claude agent with a `send_email` tool and a recipient allowlist, so it can only send where you let it | TypeScript, Vercel AI SDK |

Before you run one: [create an account](https://elasticemail.com/account/), [verify your sending domain](https://help.elasticemail.com/en/articles/4934400-how-to-verify-your-domain) (Elastic Email only sends from verified domains) and create an API key under **Settings → Manage API Keys**.

```bash
git clone https://github.com/ElasticEmail/elasticemail-examples.git
cd elasticemail-examples
```

<table>
<tr><th>Next.js</th><th>Python</th><th>AI agent</th></tr>
<tr valign="top">
<td>

```bash
cd nextjs-elasticemail-examples/typescript
npm install
cp .env.example .env
npm run dev
```

</td>
<td>

```bash
cd python-elasticemail-examples
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
python examples/fastapi_app.py
```

</td>
<td>

```bash
cd ai-agents-elasticemail-examples/vercel-ai-sdk
npm install
cp .env.example .env
npm start
```

</td>
</tr>
</table>

Put your API key and a sender on your verified domain in `.env`. Each starter's `QUICKSTART.md` covers the rest. Express, Laravel, Go, Rust, .NET, SvelteKit, serverless and 20+ other stacks are in [elasticemail-examples](https://github.com/ElasticEmail/elasticemail-examples).

<details>
<summary><b>No project yet? Send with curl</b></summary>

```bash
curl -X POST https://api.elasticemail.com/v4/emails/transactional \
  -H "X-ElasticEmail-ApiKey: $ELASTICEMAIL_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "Recipients": { "To": ["recipient@example.com"] },
    "Content": {
      "From": "you@your-domain.com",
      "Subject": "Hello from Elastic Email",
      "Body": [{ "ContentType": "HTML", "Content": "<p>It works!</p>" }]
    }
  }'
```

</details>

## Official SDKs

Every SDK wraps the same [REST API v4](https://elasticemail.com/developers/api-documentation/rest-api), so the same endpoints and models are available in every language.

| Language | Repository | Install | Package |
|---|---|---|---|
| **C# / .NET** | [elasticemail-csharp](https://github.com/ElasticEmail/elasticemail-csharp) | `dotnet add package ElasticEmail` | [![NuGet](https://img.shields.io/nuget/v/ElasticEmail?logo=nuget&label=&color=004880)](https://www.nuget.org/packages/ElasticEmail) |
| **PHP** | [elasticemail-php](https://github.com/ElasticEmail/elasticemail-php) | `composer require elasticemail/elasticemail-php` | [![Packagist](https://img.shields.io/packagist/v/elasticemail/elasticemail-php?logo=packagist&logoColor=white&label=&color=F28D1A)](https://packagist.org/packages/elasticemail/elasticemail-php) |
| **Python** | [elasticemail-python](https://github.com/ElasticEmail/elasticemail-python) | `pip install ElasticEmail` | [![PyPI](https://img.shields.io/pypi/v/ElasticEmail?logo=pypi&logoColor=white&label=&color=3775A9)](https://pypi.org/project/ElasticEmail/) |
| **JavaScript / Node.js** | [elasticemail-js](https://github.com/ElasticEmail/elasticemail-js) | `npm install @elasticemail/elasticemail-client` | [![npm](https://img.shields.io/npm/v/@elasticemail/elasticemail-client?logo=npm&label=&color=CB3837)](https://www.npmjs.com/package/@elasticemail/elasticemail-client) |
| **TypeScript (axios)** | [elasticemail-ts-axios](https://github.com/ElasticEmail/elasticemail-ts-axios) | `npm install @elasticemail/elasticemail-client-ts-axios` | [![npm](https://img.shields.io/npm/v/@elasticemail/elasticemail-client-ts-axios?logo=npm&label=&color=CB3837)](https://www.npmjs.com/package/@elasticemail/elasticemail-client-ts-axios) |
| **Angular** | [elasticemail-ts-angular](https://github.com/ElasticEmail/elasticemail-ts-angular) | `npm install @elasticemail/elasticemail-client-ts-angular` | [![npm](https://img.shields.io/npm/v/@elasticemail/elasticemail-client-ts-angular?logo=npm&label=&color=CB3837)](https://www.npmjs.com/package/@elasticemail/elasticemail-client-ts-angular) |
| **Java** | [elasticemail-java](https://github.com/ElasticEmail/elasticemail-java) | Maven / Gradle, see README | [![Release](https://img.shields.io/github/v/release/ElasticEmail/elasticemail-java?logo=github&label=)](https://github.com/ElasticEmail/elasticemail-java/releases) |
| **Go** | [elasticemail-go](https://github.com/ElasticEmail/elasticemail-go) | `go get github.com/elasticemail/elasticemail-go/v4@latest` | [![Release](https://img.shields.io/github/v/release/ElasticEmail/elasticemail-go?logo=github&label=)](https://github.com/ElasticEmail/elasticemail-go/releases) |
| **Ruby** | [elasticemail-ruby](https://github.com/ElasticEmail/elasticemail-ruby) | `gem install ElasticEmail` | [![RubyGems](https://img.shields.io/gem/v/ElasticEmail?logo=rubygems&logoColor=white&label=&color=E9573F)](https://rubygems.org/gems/ElasticEmail) |
| **Rust** | [elasticemail-rust](https://github.com/ElasticEmail/elasticemail-rust) | `cargo add ElasticEmail` | [![crates.io](https://img.shields.io/crates/v/ElasticEmail?logo=rust&label=&color=DEA584)](https://crates.io/crates/ElasticEmail) |
| **Perl** | [elasticemail-perl](https://github.com/ElasticEmail/elasticemail-perl) | `cpanm --installdeps .` | [![Release](https://img.shields.io/github/v/release/ElasticEmail/elasticemail-perl?logo=github&label=)](https://github.com/ElasticEmail/elasticemail-perl/releases) |
| **Bash** | [elasticemail-bash](https://github.com/ElasticEmail/elasticemail-bash) | Clone the repo, see README | [![Release](https://img.shields.io/github/v/release/ElasticEmail/elasticemail-bash?logo=github&label=)](https://github.com/ElasticEmail/elasticemail-bash/releases) |

## Tools and integrations

| Project | What it does |
|---|---|
| [**elasticemail-cli**](https://github.com/ElasticEmail/elasticemail-cli) | Command-line tool for sending email and campaigns and managing templates, contacts and domains. `npm install -g elastic-email-cli` |
| [**elasticemail-send-email-action**](https://github.com/ElasticEmail/elasticemail-send-email-action) | GitHub Action that sends email from a workflow, for example build reports or release notes. `uses: ElasticEmail/elasticemail-send-email-action@v1` |
| [**elasticemail-mautic-mailer**](https://github.com/ElasticEmail/elasticemail-mautic-mailer) | Mautic plugin for sending campaigns, segment emails and transactional mail through Elastic Email. |

## AI agents

| Project | What it does |
|---|---|
| [**elasticemail-mcp-server**](https://github.com/ElasticEmail/elasticemail-mcp-server) | MCP server that lets AI agents (Claude, Cursor, VS Code and others) send email and work with your Elastic Email account. |
| [**elasticemail-skills**](https://github.com/ElasticEmail/elasticemail-skills) | Agent skills that teach coding assistants the Elastic Email API. `npx skills add ElasticEmail/elasticemail-skills` |

## From the blog

- [Meet the Elastic Email CLI](https://elasticemail.com/blog/meet-the-elastic-email-cli): send email and campaigns and manage templates from your terminal, or script it with `--json`.
- [DMARC explained, with a guide to DMARCRadar](https://elasticemail.com/blog/dmarcradar-by-elastic-email-dmarc-explained-guide-to-the-new-monitoring-tool): what DMARC reports tell you and how to act on them.

More on the [Elastic Email blog](https://elasticemail.com/blog).

## Support

> [!IMPORTANT]
> The fastest way to get help is the **chat widget on [elasticemail.com](https://elasticemail.com)**. Our support team can help with your account, sending, deliverability and API questions.

- 💬 [Chat with support](https://elasticemail.com) (preferred)
- 📚 [API documentation](https://elasticemail.com/developers/api-documentation/rest-api)
- 🐛 GitHub issues in the relevant repository, for bugs in that SDK or tool only
- ✉️ [support@elasticemail.com](mailto:support@elasticemail.com)

## Contributing

Pull requests are welcome in every public repository. Please read our [contributing guide](https://github.com/ElasticEmail/.github/blob/main/CONTRIBUTING.md) (or the repository's own `CONTRIBUTING.md`) and follow our [Code of Conduct](https://github.com/ElasticEmail/.github/blob/main/CODE_OF_CONDUCT.md). To report a security vulnerability, follow our [security policy](https://github.com/ElasticEmail/.github/blob/main/SECURITY.md) and don't open a public issue.

> [!NOTE]
> The `ElasticEmail.WebApiClient-*` repositories contain the legacy **API v2** clients. They are archived and no longer maintained. New projects should use the v4 SDKs above.

<div align="center">
<sub>Made with ❤️ by the Elastic Email team</sub>
</div>
