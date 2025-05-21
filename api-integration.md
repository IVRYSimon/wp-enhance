
---

**DocumentD.md**  
```markdown
# API Integration & OpenAPI Endpoint Mapping

## 1. Authentication  
- **Bearer Token**: include `Authorization: Bearer {token}`  
- Example:
  ```php
  $client->setApiKey(getenv('ENHANCE_API_KEY'));
  $client->setBaseUrl('https://api.enhance.com/v1/');

2. Rate Limiting & Retries
Detect 429 and Retry-After header

Use exponential backoff (e.g. 1s → 2s → 4s, max 3 retries)

3. Error Mapping
Status	Meaning	Action
400	Bad Request	Throw EnhanceApiException::badRequest($msg)
401	Unauthorized	Throw EnhanceApiException::unauthorized($msg)
403	Forbidden	Throw EnhanceApiException::forbidden($msg)
404	Not Found	Throw EnhanceApiException::notFound($msg)
429	Too Many Requests	Throw EnhanceRateLimitException($retryAfter)
500	Internal Server Error	Throw EnhanceApiException::serverError($msg)

4. Endpoint–Interface Mapping
HTTP Method & Path	Interface Method	Request Schema	Response DTO
GET /v1/packages	listPackages(array $filters = [])	—	HostingPackage[]
POST /v1/packages	createPackage(array $data)	{ name, plan_id, domain? }	HostingPackage
GET /v1/packages/{id}	getPackage(string $id)	—	HostingPackage
PATCH /v1/packages/{id}	updatePackage(string $id, array $data)	Partial package fields	HostingPackage
DELETE /v1/packages/{id}	deletePackage(string $id)	—	{ deleted: bool }


---

Feel free to adjust file names or minor formatting to fit your repository conventions. Let me know if you need any further refinements!
