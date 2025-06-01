# Create API Documentation Workflow

## Overview

This workflow guides you through the process of creating comprehensive API documentation. It provides a structured approach to documenting APIs in a way that is clear, accurate, and useful for developers.

## When to Use

- When creating documentation for a new API
- When updating documentation for an existing API
- When standardizing API documentation across a project
- When preparing API documentation for public release
- When improving developer experience with your API

## Prerequisites

- Access to API source code or specifications
- Understanding of API functionality and use cases
- Knowledge of API request/response formats
- Access to API for testing examples

## Workflow Steps

### Step 1: Gather API Information

**Actions:**
1. Collect API specifications and design documents
2. Identify all endpoints and their purposes
3. Document authentication and authorization requirements
4. Gather information about request/response formats
5. Identify common use cases and examples

**Information Gathering Checklist:**
- [ ] API version and release information
- [ ] Base URL and environment information
- [ ] Authentication mechanisms
- [ ] Complete list of endpoints
- [ ] Request parameters for each endpoint
- [ ] Response formats and status codes
- [ ] Rate limiting and quota information
- [ ] Error handling approach
- [ ] Common use cases and examples

### Step 2: Plan API Documentation Structure

**Actions:**
1. Define documentation organization and hierarchy
2. Determine appropriate level of detail
3. Plan navigation and cross-references
4. Decide on documentation format and tools
5. Create documentation outline

**API Documentation Outline:**
```markdown
# API Documentation

## Overview
- API purpose and capabilities
- Version information
- Base URLs for different environments

## Authentication
- Authentication methods
- Obtaining credentials
- Token management
- Authorization scopes

## Getting Started
- Basic request example
- Authentication example
- Common use cases

## Endpoints
- Endpoint categories/resources
- Individual endpoint documentation

## Common Patterns
- Pagination
- Filtering
- Sorting
- Error handling
- Rate limiting

## Reference
- Status codes
- Error codes
- Data types
- Glossary

## SDKs and Tools
- Official client libraries
- Community tools
- API explorers
```

### Step 3: Document API Overview and Authentication

**Actions:**
1. Write introduction and overview of the API
2. Document API versioning and compatibility
3. Explain authentication and authorization methods
4. Provide step-by-step authentication examples
5. Document security best practices

**API Overview Template:**
```markdown
# API Overview

## Introduction

[Brief description of the API, its purpose, and key capabilities]

## Base URLs

| Environment | Base URL | Description |
|-------------|----------|-------------|
| Production | `https://api.example.com/v1` | Production environment |
| Staging | `https://staging-api.example.com/v1` | Staging environment for testing |
| Development | `https://dev-api.example.com/v1` | Development environment |

## Versioning

[Explain versioning strategy, e.g., URL path, header, parameter]

Current version: `v1`

### Version Lifecycle

| Version | Status | Released | Sunset Date |
|---------|--------|----------|-------------|
| v1 | Active | 2023-01-15 | - |
| v0 | Deprecated | 2022-06-01 | 2023-06-01 |

## Rate Limiting

[Explain rate limits, quotas, and throttling policies]

| Plan | Requests per minute | Daily quota |
|------|---------------------|-------------|
| Free | 60 | 10,000 |
| Pro | 300 | 100,000 |
| Enterprise | 1,000 | Unlimited |

## Authentication

[Explain authentication methods and when to use each]

### API Key Authentication

```http
GET /resource HTTP/1.1
Host: api.example.com
X-API-Key: your_api_key_here
```

### OAuth 2.0 Authentication

[Step-by-step OAuth flow explanation with examples]

### JWT Authentication

[JWT structure, obtaining tokens, refreshing tokens]
```

### Step 4: Document API Endpoints

**Actions:**
1. Group endpoints by resource or functionality
2. Document each endpoint with complete details
3. Include request parameters and response formats
4. Provide example requests and responses
5. Document error scenarios and handling

**Endpoint Documentation Template:**
```markdown
# Endpoint: [HTTP Method] [Path]

[Brief description of what this endpoint does]

## URL

```
[HTTP Method] [Path]
```

## Authentication

[Authentication requirements for this endpoint]

## Request Parameters

### Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `id` | string | Yes | Unique identifier of the resource |

### Query Parameters

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| `limit` | integer | No | 20 | Number of items to return (max 100) |
| `offset` | integer | No | 0 | Number of items to skip |
| `sort` | string | No | `created_at` | Field to sort by |
| `order` | string | No | `desc` | Sort order (`asc` or `desc`) |

### Request Body

[For POST, PUT, PATCH requests]

```json
{
  "name": "string",
  "description": "string",
  "status": "active"
}
```

#### Request Body Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `name` | string | Yes | Name of the resource |
| `description` | string | No | Description of the resource |
| `status` | string | No | Status of the resource (`active` or `inactive`) |

## Response

### Success Response

**Status Code:** 200 OK

```json
{
  "id": "123456",
  "name": "Example Resource",
  "description": "This is an example resource",
  "status": "active",
  "created_at": "2023-01-15T12:00:00Z",
  "updated_at": "2023-01-15T12:00:00Z"
}
```

#### Response Fields

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier of the resource |
| `name` | string | Name of the resource |
| `description` | string | Description of the resource |
| `status` | string | Status of the resource |
| `created_at` | string | ISO 8601 timestamp of creation |
| `updated_at` | string | ISO 8601 timestamp of last update |

### Error Responses

**Status Code:** 400 Bad Request

```json
{
  "error": "invalid_request",
  "message": "Invalid request parameters",
  "details": {
    "name": "Name is required"
  }
}
```

**Status Code:** 401 Unauthorized

```json
{
  "error": "unauthorized",
  "message": "Authentication required"
}
```

**Status Code:** 404 Not Found

```json
{
  "error": "not_found",
  "message": "Resource not found"
}
```

## Example Requests

### cURL

```bash
curl -X GET "https://api.example.com/v1/resources/123456" \
  -H "X-API-Key: your_api_key_here"
```

### JavaScript

```javascript
fetch('https://api.example.com/v1/resources/123456', {
  headers: {
    'X-API-Key': 'your_api_key_here'
  }
})
.then(response => response.json())
.then(data => console.log(data));
```

### Python

```python
import requests

headers = {
    'X-API-Key': 'your_api_key_here'
}

response = requests.get('https://api.example.com/v1/resources/123456', headers=headers)
data = response.json()
print(data)
```

## Notes

- [Any special considerations for this endpoint]
- [Rate limiting considerations]
- [Common errors and troubleshooting]
```

### Step 5: Document Common Patterns and Error Handling

**Actions:**
1. Document pagination, filtering, and sorting patterns
2. Explain error handling and status codes
3. Document rate limiting and throttling
4. Provide troubleshooting guidance
5. Include best practices for API usage

**Common Patterns Template:**
```markdown
# Common API Patterns

## Pagination

This API uses offset-based pagination for list endpoints.

### Pagination Parameters

| Parameter | Description |
|-----------|-------------|
| `limit` | Number of items to return (default: 20, max: 100) |
| `offset` | Number of items to skip (default: 0) |

### Pagination Response

```json
{
  "data": [...],
  "pagination": {
    "total": 100,
    "limit": 20,
    "offset": 0,
    "next": "/resources?limit=20&offset=20",
    "previous": null
  }
}
```

## Filtering

Most list endpoints support filtering using query parameters.

### Common Filters

| Parameter | Description | Example |
|-----------|-------------|---------|
| `status` | Filter by status | `?status=active` |
| `created_after` | Filter by creation date | `?created_after=2023-01-01T00:00:00Z` |
| `search` | Search across fields | `?search=keyword` |

### Multiple Filters

Multiple filters can be combined using `&`:

```
/resources?status=active&created_after=2023-01-01T00:00:00Z
```

## Sorting

Most list endpoints support sorting using the `sort` and `order` parameters.

| Parameter | Description | Example |
|-----------|-------------|---------|
| `sort` | Field to sort by | `?sort=created_at` |
| `order` | Sort order (`asc` or `desc`) | `?order=desc` |

Example: `/resources?sort=created_at&order=desc`

## Error Handling

### Error Response Format

```json
{
  "error": "error_code",
  "message": "Human-readable error message",
  "details": {
    "field": "Specific error for this field"
  }
}
```

### Common Error Codes

| Status Code | Error Code | Description |
|-------------|------------|-------------|
| 400 | `invalid_request` | The request was malformed or contained invalid parameters |
| 401 | `unauthorized` | Authentication is required or failed |
| 403 | `forbidden` | The authenticated user doesn't have permission |
| 404 | `not_found` | The requested resource doesn't exist |
| 422 | `validation_failed` | The request body failed validation |
| 429 | `rate_limited` | The request was rate limited |
| 500 | `server_error` | An unexpected server error occurred |

## Rate Limiting

### Rate Limit Headers

| Header | Description |
|--------|-------------|
| `X-RateLimit-Limit` | The maximum number of requests allowed in a period |
| `X-RateLimit-Remaining` | The number of requests remaining in the current period |
| `X-RateLimit-Reset` | The time when the rate limit will reset (Unix timestamp) |

### Rate Limit Exceeded Response

```json
{
  "error": "rate_limited",
  "message": "Rate limit exceeded",
  "details": {
    "retry_after": 30
  }
}
```
```

### Step 6: Create Code Examples and SDKs Documentation

**Actions:**
1. Provide code examples in multiple languages
2. Document official client libraries and SDKs
3. Include installation and setup instructions
4. Provide common usage patterns and examples
5. Document SDK-specific features and considerations

**SDK Documentation Template:**
```markdown
# API Client Libraries

## Official SDKs

| Language | Repository | Installation |
|----------|------------|--------------|
| JavaScript | [GitHub](https://github.com/example/js-sdk) | `npm install @example/sdk` |
| Python | [GitHub](https://github.com/example/python-sdk) | `pip install example-sdk` |
| Ruby | [GitHub](https://github.com/example/ruby-sdk) | `gem install example-sdk` |

## JavaScript SDK

### Installation

```bash
npm install @example/sdk
# or
yarn add @example/sdk
```

### Authentication

```javascript
const ExampleSDK = require('@example/sdk');

// Initialize with API key
const client = new ExampleSDK({
  apiKey: 'your_api_key_here'
});

// Or with OAuth token
const client = new ExampleSDK({
  accessToken: 'your_access_token_here'
});
```

### Usage Examples

#### Get a resource

```javascript
client.resources.get('123456')
  .then(resource => console.log(resource))
  .catch(error => console.error(error));
```

#### List resources with filtering and pagination

```javascript
client.resources.list({
  status: 'active',
  limit: 50,
  offset: 0
})
  .then(response => {
    console.log(response.data); // Array of resources
    console.log(response.pagination); // Pagination info
  })
  .catch(error => console.error(error));
```

#### Create a resource

```javascript
client.resources.create({
  name: 'New Resource',
  description: 'This is a new resource',
  status: 'active'
})
  .then(resource => console.log(resource))
  .catch(error => console.error(error));
```

### Error Handling

```javascript
client.resources.get('nonexistent')
  .then(resource => console.log(resource))
  .catch(error => {
    if (error.statusCode === 404) {
      console.error('Resource not found');
    } else {
      console.error('An error occurred:', error.message);
    }
  });
```

## Python SDK

[Similar documentation for Python SDK]

## Ruby SDK

[Similar documentation for Ruby SDK]
```

### Step 7: Document API Changelog and Versioning

**Actions:**
1. Create API changelog with version history
2. Document breaking vs. non-breaking changes
3. Explain versioning strategy and compatibility
4. Provide migration guides for major versions
5. Document deprecation policies and timelines

**Changelog Template:**
```markdown
# API Changelog

## v1.2.0 (2023-03-15)

### New Features

- Added new endpoint `GET /resources/{id}/history` to retrieve resource history
- Added support for filtering resources by `tags`
- Added new `archived` status for resources

### Improvements

- Improved error messages for validation failures
- Enhanced rate limit headers with more detailed information
- Optimized performance for large result sets

### Bug Fixes

- Fixed an issue where sorting by `updated_at` didn't work correctly
- Fixed inconsistent date format in responses
- Corrected documentation for the `limit` parameter maximum value

## v1.1.0 (2023-02-01)

### New Features

- Added bulk operations endpoint `POST /resources/bulk`
- Added support for resource webhooks
- Introduced new query parameter `include` for related resources

### Improvements

- Enhanced pagination with `total_pages` information
- Added request ID to all responses for better debugging
- Improved validation error details

### Bug Fixes

- Fixed an issue with Unicode characters in resource names
- Corrected status code for rate limiting (429 instead of 403)
- Fixed inconsistent error response format

## v1.0.0 (2023-01-15)

Initial release of the API.

### Features

- Resource management (CRUD operations)
- User management
- Authentication via API keys and OAuth 2.0
- Pagination, filtering, and sorting
- Comprehensive error handling
```

**Versioning and Migration Guide:**
```markdown
# API Versioning and Migration

## Versioning Strategy

This API uses semantic versioning (MAJOR.MINOR.PATCH) with the following guidelines:

- **MAJOR** version increments for breaking changes
- **MINOR** version increments for new features (backward compatible)
- **PATCH** version increments for bug fixes (backward compatible)

The API version is specified in the URL path: `https://api.example.com/v1/`

## Compatibility Policy

- We maintain backward compatibility within a major version
- We provide at least 6 months of support for previous major versions after a new major version is released
- Deprecated features are marked in the documentation and will be removed in the next major version

## Migration Guide: v0 to v1

### Authentication Changes

**v0:**
```http
GET /resource HTTP/1.1
Host: api.example.com
Authorization: ApiKey your_api_key_here
```

**v1:**
```http
GET /resource HTTP/1.1
Host: api.example.com
X-API-Key: your_api_key_here
```

### Response Format Changes

**v0:**
```json
{
  "result": {
    "id": "123456",
    "name": "Example Resource"
  },
  "success": true
}
```

**v1:**
```json
{
  "id": "123456",
  "name": "Example Resource"
}
```

### Endpoint Changes

| v0 Endpoint | v1 Endpoint | Notes |
|-------------|-------------|-------|
| `GET /get_resource/{id}` | `GET /resources/{id}` | Path changed to follow REST conventions |
| `POST /create_resource` | `POST /resources` | Path changed to follow REST conventions |
| `POST /update_resource/{id}` | `PUT /resources/{id}` | Method changed from POST to PUT |
| `GET /list_resources` | `GET /resources` | Path changed to follow REST conventions |
| `POST /delete_resource/{id}` | `DELETE /resources/{id}` | Method changed from POST to DELETE |
```

### Step 8: Review and Publish API Documentation

**Actions:**
1. Review documentation for accuracy and completeness
2. Validate all examples and code snippets
3. Check for consistency in terminology and formatting
4. Gather feedback from API users and developers
5. Publish documentation in appropriate formats

**Review Checklist:**
- [ ] All endpoints are documented
- [ ] Authentication methods are clearly explained
- [ ] Request and response formats are accurate
- [ ] Examples are provided for all endpoints
- [ ] Code samples work as expected
- [ ] Error scenarios are documented
- [ ] Common patterns are explained
- [ ] Versioning and changelog are included
- [ ] Documentation is consistent in style and terminology
- [ ] Navigation and cross-references work correctly

**Publication Options:**
- Static documentation site (e.g., GitHub Pages, Netlify)
- API documentation platforms (e.g., Swagger UI, Redoc)
- Developer portal integration
- PDF export for offline reference
- Interactive API explorer

## Best Practices

### Content Quality

- Use clear, concise language
- Be consistent with terminology
- Provide real-world examples
- Include both basic and advanced use cases
- Document limitations and edge cases
- Keep examples simple but realistic

### Documentation Structure

- Organize by resource or user task
- Use consistent formatting for endpoints
- Provide a clear navigation structure
- Include a search function if possible
- Link related endpoints and concepts
- Use proper heading hierarchy

### Code Examples

- Provide examples in multiple languages
- Keep examples concise and focused
- Use realistic values in examples
- Include error handling in examples
- Test all examples to ensure they work
- Update examples when the API changes

## Troubleshooting

### Common Documentation Issues

**Incomplete Parameter Documentation**
- Solution: Create a comprehensive parameter table
- Action: Include type, required status, default value, and constraints

**Outdated Examples**
- Solution: Implement automated testing for examples
- Action: Update examples when the API changes

**Unclear Error Documentation**
- Solution: Document all possible error codes and messages
- Action: Include troubleshooting guidance for common errors

**Inconsistent Terminology**
- Solution: Create a glossary of terms
- Action: Review documentation for consistency

## Success Criteria

- Developers can successfully use the API with minimal support
- Documentation is comprehensive and accurate
- Examples work as described
- Error scenarios are well-documented
- Feedback from API users is positive
- Support tickets related to API usage decrease

## Notes

- API documentation is a living document that should evolve with the API
- Regular updates are essential to maintain accuracy
- User feedback is valuable for improving documentation
- Consider different learning styles and experience levels
- Good API documentation is a competitive advantage

**Remember**: The goal of API documentation is to help developers successfully integrate with your API with minimal friction and support needs.
