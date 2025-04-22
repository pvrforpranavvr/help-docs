# 🔍 Checking Akamai Cache Status for API Responses

This guide walks through how to determine whether **API responses are cached by Akamai**, using both standard HTTP headers and the special `Pragma` debug header.

---

## 📦 1. Check Akamai Caching via HTTP Headers

### 🛠 Basic Curl or Postman Request

Use `curl` to inspect response headers:

```bash
curl -I https://api.example.com/your-endpoint
```
🔎 Headers to Look For

| **Header**            | **Meaning**                                              |
|-----------------------|----------------------------------------------------------|
| `X-Cache`             | Cache status (e.g., `TCP_HIT`, `TCP_MISS`)               |
| `X-Check-Cacheable`   | Whether the response is considered cacheable             |
| `X-Akamai-Cache`      | (Sometimes present) Cache result from Akamai             |
| `X-Cache-Key`         | Cache key used internally by Akamai                      |
| `X-True-Cache-Key`    | Final resolved cache key after normalization             |
| `X-Cache-Remote`      | Information about remote caching or origin involvement   |

🧠 X-Cache Common Values

| **Value**            | **Description**                                           |
|----------------------|-----------------------------------------------------------|
| `TCP_HIT`            | ✅ Served from Akamai cache                               |
| `TCP_MISS`           | ❌ Not in cache, fetched from origin                      |
| `TCP_REFRESH_HIT`    | Served from cache but revalidated with origin             |
| `TCP_EXPIRED_MISS`   | Cache expired, fetched from origin                        |
| `TCP_MEM_HIT`        | Cached in Akamai’s memory cache                           |
| `TCP_DENIED`         | Request denied caching due to policy/config               |
| `TCP_INVALID`        | Cache key invalid or response deemed uncacheable          |

## 📌 2. Using the Pragma Header for Debugging

## 📌 Using the `Pragma` Header for Akamai Debugging

To get extra diagnostic headers from Akamai, add the following `Pragma` header in your request.

---

### ✅ Pragma Header Example (Use [ModHeader - Modify HTTP headers](https://chromewebstore.google.com/detail/modheader-modify-http-hea/idgpnmonknjnojddfkpgkljpfnnfcklj?hl=en)
 to pass header from browser)

```bash
Pragma: akamai-x-cache-on, akamai-x-cache-remote-on, akamai-x-check-cacheable, akamai-x-get-cache-key, akamai-x-get-true-cache-key, akamai-x-get-extracted-values, akamai-x-get-request-id, akamai-x-get-client-ip, akamai-x-get-nonces, akamai-x-get-ssl-client-session-id

curl -I -H "Pragma: akamai-x-cache-on, akamai-x-get-cache-key, akamai-x-get-true-cache-key, akamai-x-get-request-id" https://api.example.com/your-endpoint
```
| **Pragma Directive**                  | **Description**                                                                 |
|---------------------------------------|---------------------------------------------------------------------------------|
| `akamai-x-cache-on`                  | Returns the `X-Cache` header                                                    |
| `akamai-x-cache-remote-on`           | Returns the `X-Cache-Remote` header (origin vs edge)                            |
| `akamai-x-check-cacheable`           | Indicates whether the response is cacheable                                     |
| `akamai-x-get-cache-key`             | Returns the `X-Cache-Key` used by Akamai                                        |
| `akamai-x-get-true-cache-key`        | Returns the `X-True-Cache-Key` (after normalization)                            |
| `akamai-x-get-request-id`            | Returns a unique ID for the request (used in Akamai logs)                       |
| `akamai-x-get-client-ip`             | Returns the client IP address as seen by Akamai                                 |
| `akamai-x-get-nonces`                | Returns any nonces associated with the request (security-related)              |
| `akamai-x-get-extracted-values`      | Returns values extracted from query/path/header/cookie by property rules        |
| `akamai-x-get-ssl-client-session-id` | Returns SSL session ID (if applicable)                                          |




