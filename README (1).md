---
description: Provides basic information about the API and data.
---

# Endpoint: Get API Information

## General Info

#### URL:

<pre class="language-url"><code class="lang-url"><strong>https://pro3.lukaskrmencik.cz/v2/api/v1/info.php
</strong></code></pre>

#### Headers:

<pre class="language-javascript"><code class="lang-javascript"><strong>Content-Type: application/json; charset=utf-8
</strong></code></pre>

<table><thead><tr><th width="361">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Request Parameters</td><td>No input data required</td></tr><tr><td>Authentication</td><td>Bearer token <a data-mention href="./">.</a></td></tr><tr><td>Request Method</td><td>GET</td></tr></tbody></table>



## **Response Format**

The API responds with a JSON object containing general information about the system, including server time, the number of cars and companies in the database, and the latest cron update.



### **Response Fields Explanation**

<table><thead><tr><th width="338">Field</th><th width="99">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>type</code></td><td><code>string</code></td><td>Response type (JSON data or ERROR)</td></tr><tr><td><code>data.info</code></td><td><code>string</code></td><td>API description</td></tr><tr><td><code>data.dashboardLink</code></td><td><code>string</code></td><td>Link to the dashboard</td></tr><tr><td><code>data.documentationLink</code></td><td>string</td><td>Link to the documentation</td></tr><tr><td><code>data.serverTime</code></td><td><code>string</code></td><td>Current server time in <code>Y-m-d H:i:s P</code> format</td></tr><tr><td><code>data.companiesInDB</code></td><td><code>int</code></td><td>Total number of companies in the database</td></tr><tr><td><code>data.carsInDB</code></td><td><code>int</code></td><td>Total number of cars in the database</td></tr><tr><td><code>data.lastCronUpdate</code></td><td><code>object</code></td><td>Last cron update details</td></tr><tr><td><code>data.lastCronUpdate.cars</code></td><td><code>int</code></td><td>Count of cars updated in last cron</td></tr><tr><td><code>data.lastCronUpdate.companies</code></td><td><code>int</code></td><td>Count of companies updated in last cron</td></tr><tr><td><code>data.lastCronUpdatetimestamp</code></td><td><code>string</code></td><td>Last crone time in <code>Y-m-d H:i:s</code> format</td></tr><tr><td><code>data.error</code></td><td><code>int</code></td><td>Error code</td></tr></tbody></table>



### Success response

```json
{
    "type": "JSON data",
    "data": {
        "info": "API providing data about used cars and companies that sell them.",
        "dashboardLink": "https://pro3.lukaskrmencik.cz/v2/dash/",
        "documentationLink": "https://sps-prosek-6.gitbook.io/projekt-api/endpoint-get-api-information",
        "serverTime": "2025-02-06 11:16:49 +01:00",
        "companiesInDB": 951,
        "carsInDB": 123,
        "lastCronUpdate": {
            "cars": 0,
            "companies": 951,
            "timestamp": "2024-10-24 09:37:36"
        }
    }
}
```



### **Error Response:**

```json
{
    "type": "ERROR",
    "data": {
        "error": 502,
        "documentationLink": "https://sps-prosek-6.gitbook.io/projekt-api/endpoint-get-api-information",
    }
}
```



### **Error codes Explanation**

<table><thead><tr><th width="137">Error Code</th><th>Error Description</th><th>Solution</th></tr></thead><tbody><tr><td>501</td><td>Error retrieving server time</td><td>Contact support</td></tr><tr><td>502</td><td>Error fetching the last cron update</td><td>Contact support</td></tr><tr><td>503</td><td>Error counting records in the database</td><td>Contact support</td></tr></tbody></table>

