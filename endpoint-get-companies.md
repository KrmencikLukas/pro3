---
description: >-
  Returns a list of companies, including their basic information. It supports
  pagination using the offset and limit parameters.
---

# Endpoint: Get companies

## General Info

#### URL:

```url
https://pro3.lukaskrmencik.cz/v2/api/v1/companies.php
```

#### Headers:

<pre class="language-javascript"><code class="lang-javascript"><strong>Content-Type: application/json; charset=utf-8
</strong></code></pre>

<table><thead><tr><th width="361">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Request Parameters</td><td><code>offset</code>, <code>limit</code></td></tr><tr><td>Authentication</td><td>Bearer token <a data-mention href="./">.</a></td></tr><tr><td>Request Method</td><td>GET</td></tr></tbody></table>

## Parameters

<table><thead><tr><th width="133">Parameter</th><th width="77">Type</th><th width="258">Description</th><th width="127">Required</th><th data-type="number">Default Value</th></tr></thead><tbody><tr><td><code>offset</code></td><td><code>int</code></td><td>The starting point for the results, used for pagination.</td><td>No</td><td>0</td></tr><tr><td><code>limit</code></td><td><code>int</code></td><td>The number of results to return. Max value is 100.</td><td>No</td><td>10</td></tr></tbody></table>

## **Response Format**

The API responds with a JSON object containing list of companies.

### **Response Fields Explanation**

<table><thead><tr><th width="358">Field</th><th width="119">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>type</code></td><td><code>string</code></td><td>Response type (JSON Data or ERROR)</td></tr><tr><td><code>data</code></td><td><code>object</code></td><td>Object containing response data.</td></tr><tr><td><code>data.companies</code></td><td><code>array</code></td><td>List of companies with their details.</td></tr><tr><td><code>data.companies[].id</code></td><td><code>string</code></td><td>Unique identification number of the company's license</td></tr><tr><td><code>data.companies[].name</code></td><td><code>string</code></td><td>Company name</td></tr><tr><td><code>data.companies[].street</code></td><td><code>string</code></td><td>Street where the company is located.</td></tr><tr><td><code>data.companies[].town</code></td><td><code>string</code></td><td>Town where the company is located.</td></tr><tr><td><code>data.start</code></td><td><code>int</code></td><td>The starting position of the displayed list (based on the offset).</td></tr><tr><td><code>data.end</code></td><td><code>int</code></td><td>The ending position of the displayed list (based on the number of returned items).</td></tr><tr><td><code>data.total</code></td><td><code>int</code></td><td>Total number of companies in the database.</td></tr><tr><td><code>data.error</code></td><td><code>int</code></td><td>Error code</td></tr><tr><td><code>data.documentationLink</code></td><td><code>string</code></td><td>Link to documentation</td></tr></tbody></table>



### Success response

```json
{
    "type": "JSON Data",
    "data": {
        "companies": [
            {
                "id": "0001",
                "name": "ŠUDOMA s.r.o. NOVÝ JIČÍN",
                "street": "Suvorovova 577",
                "town": "Nový Jičín"
            },
            {
                "id": "0003",
                "name": "AUTORENT s.r.o.",
                "street": "Líšný 2.díl 6",
                "town": "Líšný"
            }
        ],
        "start": 1,
        "end": 2,
        "total": 951
    }
}
```



### **Error Response:**

```json
{
    "type": "ERROR",
    "data": {
        "error": 401,
        "documentationLink": "https://sps-prosek-6.gitbook.io/projekt-api/endpoint-get-companies"
    }
}
```



### **Error codes Explanation**

<table><thead><tr><th width="137">Error Code</th><th>Error Description</th><th>Solution</th></tr></thead><tbody><tr><td><code>401</code></td><td>Invalid <code>offset</code> parameter. </td><td><code>offset</code> parameter must be a whole number greater than or equal to 0.</td></tr><tr><td><code>402</code></td><td>Invalid <code>limit</code> parameter. </td><td><code>limit</code> parameter must be a number between 0 and 100.</td></tr><tr><td><code>501</code></td><td>Internal server error while generating an error response.</td><td>Contact support</td></tr><tr><td><code>502</code></td><td>Internal server error while generating a response.</td><td>Contact support</td></tr><tr><td><code>503</code></td><td>Internal server error retrieving the company count from the database.</td><td>Contact support</td></tr><tr><td><code>504</code></td><td>Internal server error processing the <code>offset</code> parameter.</td><td>Contact support</td></tr><tr><td><code>505</code></td><td>Internal server error processing the <code>limit</code> parameter.</td><td>Contact support</td></tr><tr><td>403</td><td>Invalid or expired token</td><td><a data-mention href="./">.</a></td></tr></tbody></table>

