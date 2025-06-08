# Endpoint: Search cars

## General Info

#### URL:

```url
https://pro3.lukaskrmencik.cz/v2/api/v1/search-cars.php
```

#### Headers:

<pre class="language-javascript"><code class="lang-javascript"><strong>Content-Type: application/json; charset=utf-8
</strong></code></pre>

<table><thead><tr><th width="361">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Request Parameters</td><td><code>search</code>, <code>filters</code>, <code>offset</code>, <code>limit</code></td></tr><tr><td>Authentication</td><td>Bearer token <a data-mention href="./">.</a></td></tr><tr><td>Request Method</td><td>GET</td></tr></tbody></table>

## Parameters

<table><thead><tr><th width="133">Parameter</th><th width="87">Type</th><th width="262">Description</th><th width="127">Required</th><th>Default Value</th></tr></thead><tbody><tr><td><code>search</code></td><td><code>string</code></td><td>Search string (fulltext across car metadata)</td><td>No</td><td>""</td></tr><tr><td><code>filters</code></td><td><code>object</code></td><td>JSON of key-value pairs to filter results, e.g. {"manufacturer_text": "Škoda" }</td><td>No</td><td>{}</td></tr><tr><td><code>offset</code></td><td><code>int</code></td><td>Start index for pagination</td><td>No</td><td>0</td></tr><tr><td><code>limit</code></td><td><code>int</code></td><td>Maximum number of results (1–100)</td><td>No</td><td>10</td></tr></tbody></table>

## Filterable Metadata Fields

The following keys can be used as filters (case-insensitive match):

```
body_klic, body_text, cebia_report, cena_na_leasing, cena_na_leasing_2, color_klic, color_text, condition_klic, condition_text, custom_car_id, date_in, dojezd, dokumenty, emise, engine_power, engine_power_klic, engine_power_text, engine_volume, equipment, evid_cislo, financovani, financovani_pozn, first_owner, fuel_klic, fuel_text, kap_akumulatoru, kategorie_klic, kategorie_text, kind_klic, kind_text, made_date, manufacturer_klic, manufacturer_text, max_rychlost, met_dojezdu_klic, met_dojezdu_text, met_spotreby_klic, met_spotreby_text, model_klic, model_text, nabijeci_doba_1, nabijeci_doba_2, nabijeci_doba_3, nabijeci_vykon_1, nabijeci_vykon_2, nabijeci_vykon_3, neverejny, not_crashed, note, odpocet_2, photo_3D, photos, plug_in, pocet_dveri, pocet_mist, price, price_2, price_end, price_end_2, price_mena_klic, price_mena_klic_2, price_mena_text, price_mena_text_2, price_puvodni, price_puvodni_2, radkova_loga, service_book, spotreba, spotreba_jedn, state_klic, state_text, stk_to, t_moment, tachometr, tachometr_unit_klic, tachometr_unit_text, tuning, typ_akumulatoru_klic, typ_akumulatoru_text, typ_hybridu_klic, typ_hybridu_text, typ_konektoru_klic, typ_konektoru_text, typ_zivotnosti_klic, typ_zivotnosti_text, type_info, type_info_varianta, vat, vat_2, vin, vybava_klient, vybava_maska, vyk_nabijecky, vyrazeny, zar_akumulatoru, zaruka_do, ziv_akumulatoru, zrychleni, celkova_hmotnost, ekologicka_dan, rubrika_klic, rubrika_text
```

## Response Format

The API responds with a JSON object containing list of cars.

### Response Fields Explanation

| Field                             | Type     | Description                        |
| --------------------------------- | -------- | ---------------------------------- |
| `type`                            | `string` | Response type (JSON Data or ERROR) |
| `data`                            | `object` | Data object                        |
| `data.cars`                       | `array`  | List of cars                       |
| `data.cars[].custom_car_id`       | `string` | Unique car identifier              |
| `data.cars[].manufacturer_text`   | `string` | Car manufacturer                   |
| `data.cars[].model_text`          | `string` | Car model                          |
| `data.cars[].type_info`           | `string` | Type information                   |
| `data.cars[].price`               | `float`  | Car price                          |
| `data.cars[].price_mena_text`     | `string` | Currency text                      |
| `data.cars[].color_text`          | `string` | Color                              |
| `data.cars[].condition_text`      | `string` | Condition                          |
| `data.cars[].fuel_text`           | `string` | Fuel type                          |
| `data.cars[].body_text`           | `string` | Body style                         |
| `data.cars[].date_in`             | `string` | Date the car was added             |
| `data.cars[].tachometr`           | `int`    | Odometer value                     |
| `data.cars[].tachometr_unit_text` | `string` | Odometer unit                      |
| `data.cars[].note`                | `string` | Note (if any)                      |
| `data.start`                      | `int`    | Starting index of results          |
| `data.end`                        | `int`    | Ending index of results            |
| `data.total`                      | `int`    | Total number of matched cars       |

### Success Response

```json
{
    "type": "JSON Data",
    "data": {
        "cars": [
            {
                "custom_car_id": "1025",
                "manufacturer_text": "Škoda",
                "model_text": "Octavia",
                "type_info": "Combi",
                "price": "189000",
                "price_mena_text": "CZK",
                "color_text": "Bílá",
                "condition_text": "Použité",
                "fuel_text": "Nafta",
                "body_text": "Combi",
                "date_in": "2024-01-08",
                "tachometr": "120000",
                "tachometr_unit_text": "km",
                "note": "Velmi dobrý stav"
            }
        ],
        "start": 1,
        "end": 1,
        "total": 76
    }
}
```

### Error Response

```json
{
    "type": "ERROR",
    "data": {
        "error": 401,
        "documentationLink": "https://sps-prosek-6.gitbook.io/projekt-api/endpoint-search-cars"
    }
}
```

### Error Codes Explanation

| Error Code | Description                      |
| ---------- | -------------------------------- |
| `400`      | Invalid input                    |
| `401`      | Invalid offset                   |
| `402`      | Invalid limit                    |
| `504`      | Offset parsing error             |
| `505`      | Limit parsing error              |
| `506`      | Internal search processing error |
| `500`      | Unhandled server error           |
| `501`      | Error while reporting an error   |
| `502`      | sendResponse failed              |
| `551`      | getCarMetaValue failed           |
| 403        | Invalid or expired token         |
