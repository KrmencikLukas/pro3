# Authentication Guide

Welcome! This guide will help you authenticate and access protected API endpoints.

## Step 1: Generate Your API Credentials

1. Go to your dashboard. [`https://pro3.lukaskrmencik.cz/v2/dash/`](https://pro3.lukaskrmencik.cz/v2/dash/)
2. Go to the Auth section in the sidebar on the left.
3. Click the **"+ Generate new API key"** button.
4. Your **UID** and **Secret key** will appear. Save them somewhere safe.
5. You can reset or delete each key at any time.

## Step 2: Get Your Access Token

Once you have your UID and Secret key, use them to get your token.

### Endpoint

```
POST pro3.lukaskrmencik.cz/v2/api/v1/auth.php
```

### Request Headers

```
Content-Type: application/json
```

### Request Body

```
{
  "uid": "your_uid_here",
  "secret": "your_secret_here"
}
```

### Successful Response

```
{
  "token": "your_JWT_token_here",
  "expires_in": 3600
}
```

Save the token – you'll use it to access other endpoints.

## Step 3: Use Your Token

When calling protected endpoints, add this to the request header:

```
Authorization: Bearer your_JWT_token_here
```

## Error Codes

| Code | Meaning                                                  |
| ---- | -------------------------------------------------------- |
| 401  | Invalid UID or Secret                                    |
| 403  | Missing or invalid token                                 |
| 503  | Database error                                           |
| 504  | Offset parameter is not valid                            |
| 505  | Limit parameter is not valid or general processing error |
