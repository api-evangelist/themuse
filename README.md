# The Muse (themuse)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

The Muse is a careers and company-profiles platform that helps people find jobs at companies whose values match their own. Its free, documented public REST API (v2) exposes hundreds of thousands of live **job openings** - searchable by category, experience level, company, and location - alongside rich employer **company profiles** (industry, size, locations, and behind-the-scenes content). An optional `api_key` raises rate limits. This makes The Muse a strong source for "job openings", jobs, careers, and recruiting use cases and for building job boards, career sites, and employer-branding integrations.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/themuse/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/themuse/refs/heads/main/apis.yml)

## Access Model (Honest Summary)

The Muse public API is **free**. Access is differentiated only by whether you register and send an API key:

- **Anonymous (no key):** 500 requests per hour.
- **Registered (`api_key` query parameter):** 3,600 requests per hour.
- **Higher / commercial access:** arranged directly with The Muse at `api@themuse.com`.

There is no published paid self-serve tier. Every response carries `X-RateLimit-Limit`, `X-RateLimit-Remaining`, and `X-RateLimit-Reset` headers, and exceeding the limit returns HTTP 403. List endpoints return at most 20 results per page and require a `page` parameter. Using the API requires agreeing to the [API terms](https://www.themuse.com/developers/api/v2/terms).

- **Base URL:** `https://www.themuse.com/api/public` (the legacy host `https://api-v2.themuse.com` still resolves via redirect)
- **Auth:** optional `api_key` query parameter
- **Format:** JSON, request/response REST over HTTPS (no WebSocket / streaming surface)

> **Note on Posts:** older references to a `/posts` endpoint exist, but that path returns HTTP 404 as of this writing and is intentionally **not** cataloged here as a live API. Only the Jobs and Companies endpoints were confirmed live.

## Tags

- Job Openings
- Jobs
- Careers
- Recruiting
- Employment
- Company Profiles
- Job Search
- Hiring
- HR Tech

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### The Muse Jobs API

Search and retrieve live job openings across hundreds of thousands of listings. Filter by category (Data Science, Design, Engineering, Sales, and 20+ more), experience level (Entry Level, Mid Level, Senior Level, Management, Internship), company, and location, with paginated results and per-job company details. Retrieve a single job by its numeric ID. This is the core surface for "job openings", job search, and careers use cases.

- **Human URL:** [https://www.themuse.com/developers/api/v2](https://www.themuse.com/developers/api/v2)
- **Base URL:** `https://www.themuse.com/api/public`

**Endpoints**

- `GET /jobs` — search job openings (`page`, `category`, `level`, `company`, `location`, `descending`, `api_key`)
- `GET /jobs/{id}` — retrieve a single job by numeric ID

#### Tags

- Job Openings
- Jobs
- Careers
- Job Search
- Recruiting

#### Properties

- [Documentation](https://www.themuse.com/developers/api/v2)
- [API Reference](https://www.themuse.com/developers/api/v2)
- [OpenAPI](openapi/themuse-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/themuse.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/themuse.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### The Muse Companies API

Browse and retrieve employer company profiles that back the job listings. Filter by industry, company size, and location, with paginated results. Retrieve a single company by its numeric ID to get its description, industries, locations, size, tags, and links to its landing and jobs pages. Useful for employer-branding, company-research, and recruiting integrations.

- **Human URL:** [https://www.themuse.com/developers/api/v2](https://www.themuse.com/developers/api/v2)
- **Base URL:** `https://www.themuse.com/api/public`

**Endpoints**

- `GET /companies` — search company profiles (`page`, `industry`, `size`, `location`, `descending`, `api_key`)
- `GET /companies/{id}` — retrieve a single company by numeric ID

#### Tags

- Company Profiles
- Employers
- Employer Branding
- Recruiting

#### Properties

- [Documentation](https://www.themuse.com/developers/api/v2)
- [API Reference](https://www.themuse.com/developers/api/v2)
- [OpenAPI](openapi/themuse-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/themuse.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/themuse.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/the-muse)
- [Website](https://www.themuse.com)
- [Documentation](https://www.themuse.com/developers/api/v2)
- [Plans](plans/themuse-plans-pricing.yml)
- [Rate Limits](rate-limits/themuse-rate-limits.yml)
- [Fin Ops](finops/themuse-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
