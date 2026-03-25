# NestUI API Documentation 🧠

Welcome to the NestUI API reference. Our API allows you to integrate state-of-the-art AI generation directly into your own applications. 

## 🌍 Global API Concepts

**Base URL (Production):**
All API requests should be made to the live environment endpoint:
`https://nestui.store/api/1.1/wf/`

### 🔐 Authentication
Secure your API requests with API key authentication. 
> **⚠️ CRITICAL:** NestUI requires the API key to be passed **directly inside the JSON payload (body)** of your requests. Do not use HTTP headers or query strings for authentication.

**Required Parameter (JSON Body):**
```json
{
  "api_key": "YOUR_API_KEY"
}
