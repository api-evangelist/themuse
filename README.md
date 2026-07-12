# The Muse (themuse)

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
