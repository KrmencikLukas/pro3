---
description: >-
  Returns detailed information about a specific car, including basic, extended,
  or full data based on the provided scope.
---

# Endpoint: Get single car

## General Info

**URL**:&#x20;

```url
https://pro3.lukaskrmencik.cz/v2/api/v1/single-car.php
```

**Headers**:

```javascript
Content-Type: application/json; charset=utf-8
```

<table><thead><tr><th width="361">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Request Parameters</td><td><code>id</code>, <code>scope</code></td></tr><tr><td>Authentication</td><td>No authentication required</td></tr><tr><td>Request Method</td><td>GET</td></tr></tbody></table>

## Parameters

<table><thead><tr><th>Parameter</th><th>Type</th><th width="296">Description</th><th width="90">Required</th><th>Default Value</th></tr></thead><tbody><tr><td><code>id</code></td><td><code>string</code></td><td>The unique ID of the car.</td><td>Yes</td><td>-</td></tr><tr><td><code>scope</code></td><td><code>string</code></td><td>The level of detail for the car data. Options: <code>basic</code>, <code>extended</code>, <code>full</code>.</td><td>No</td><td><code>basic</code></td></tr></tbody></table>

## Response Format

The API responds with a JSON object containing the car details.

### Response Fields Explanation

| Field                    | Type     | Description                               |
| ------------------------ | -------- | ----------------------------------------- |
| `type`                   | `string` | Response type (`JSON Data` or `ERROR`)    |
| `data`                   | `object` | Object containing response data.          |
| `data.car_id`            | `string` | Unique identification number of the car.  |
| `data.car_data`          | `object` | Car details based on the requested scope. |
| `data.previous_id`       | `string` | ID of the previous car (if applicable).   |
| `data.next_id`           | `string` | ID of the next car (if applicable).       |
| `data.error`             | `int`    | Error code (if applicable).               |
| `data.documentationLink` | `string` | Link to documentation.                    |

<details>

<summary>Basic scope <code>data.car_data</code></summary>

<table><thead><tr><th width="222">Field</th><th width="89">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>custom_car_id</code></td><td>String</td><td>Custom ID for the car</td></tr><tr><td><code>manufacturer_text</code></td><td>String</td><td>Car manufacturer</td></tr><tr><td><code>model_text</code></td><td>String</td><td>Car model</td></tr><tr><td><code>type_info</code></td><td>String</td><td>Type of the car</td></tr><tr><td><code>price</code></td><td>Float</td><td>Price of the car</td></tr><tr><td><code>price_mena_text</code></td><td>String</td><td>Currency of the price</td></tr><tr><td><code>color_text</code></td><td>String</td><td>Car color</td></tr><tr><td><code>condition_text</code></td><td>String</td><td>Condition of the car</td></tr><tr><td><code>fuel_text</code></td><td>String</td><td>Fuel type</td></tr><tr><td><code>body_text</code></td><td>String</td><td>Body type</td></tr><tr><td><code>date_in</code></td><td>Date</td><td>Date when the car entered</td></tr><tr><td><code>tachometr</code></td><td>Integer</td><td>Car odometer reading</td></tr><tr><td><code>tachometr_unit_text</code></td><td>String</td><td>Odometer unit (e.g., km, miles)</td></tr><tr><td><code>note</code></td><td>String</td><td>Additional notes</td></tr></tbody></table>

</details>

<details>

<summary>Extended scope <code>data.car_data</code></summary>

<table><thead><tr><th width="239">Field</th><th width="84">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>custom_car_id</code></td><td>String</td><td>Custom ID for the car</td></tr><tr><td><code>manufacturer_text</code></td><td>String</td><td>Car manufacturer</td></tr><tr><td><code>model_text</code></td><td>String</td><td>Car model</td></tr><tr><td><code>type_info</code></td><td>String</td><td>Type of the car</td></tr><tr><td><code>price</code></td><td>Float</td><td>Price of the car</td></tr><tr><td><code>price_mena_text</code></td><td>String</td><td>Currency of the price</td></tr><tr><td><code>color_text</code></td><td>String</td><td>Car color</td></tr><tr><td><code>condition_text</code></td><td>String</td><td>Condition of the car</td></tr><tr><td><code>fuel_text</code></td><td>String</td><td>Fuel type</td></tr><tr><td><code>body_text</code></td><td>String</td><td>Body type</td></tr><tr><td><code>date_in</code></td><td>Date</td><td>Date when the car entered</td></tr><tr><td><code>tachometr</code></td><td>Integer</td><td>Car odometer reading</td></tr><tr><td><code>tachometr_unit_text</code></td><td>String</td><td>Odometer unit (e.g., km, miles)</td></tr><tr><td><code>note</code></td><td>String</td><td>Additional notes</td></tr><tr><td><code>engine_power</code></td><td>Integer</td><td>Engine power (in horsepower or kW)</td></tr><tr><td><code>engine_power_text</code></td><td>String</td><td>Engine power description</td></tr><tr><td><code>engine_volume</code></td><td>Float</td><td>Engine volume (in liters)</td></tr><tr><td><code>typ_hybridu_text</code></td><td>String</td><td>Hybrid type (e.g., Plug-in)</td></tr><tr><td><code>plug_in</code></td><td>Integer</td><td>Plug-in hybrid (1 if yes, 0 if no)</td></tr><tr><td><code>t_moment</code></td><td>Integer</td><td>Torque value (e.g., in Nm)</td></tr><tr><td><code>pocet_dveri</code></td><td>Integer</td><td>Number of doors</td></tr><tr><td><code>pocet_mist</code></td><td>Integer</td><td>Number of seats</td></tr><tr><td><code>first_owner</code></td><td>Integer</td><td>First owner status (1 if yes, 0 if no)</td></tr><tr><td><code>not_crashed</code></td><td>Integer</td><td>Not crashed (1 if yes, 0 if no)</td></tr><tr><td><code>financovani_pozn</code></td><td>String</td><td>Financing notes</td></tr><tr><td><code>service_book</code></td><td>Integer</td><td>Availability of service book (1 if yes, 0 if no)</td></tr><tr><td><code>made_date</code></td><td>Date</td><td>Production date</td></tr><tr><td><code>price_puvodni</code></td><td>Float</td><td>Original price</td></tr><tr><td><code>price_end</code></td><td>Float</td><td>Final price</td></tr><tr><td><code>kategorie_text</code></td><td>String</td><td>Car category</td></tr><tr><td><code>kind_text</code></td><td>String</td><td>Car type (e.g., sedan, SUV)</td></tr></tbody></table>

</details>

<details>

<summary>Full scope <code>data.car_data</code></summary>

<table><thead><tr><th width="203">Field</th><th width="80">Type</th><th width="368">Description</th></tr></thead><tbody><tr><td><code>body_klic</code></td><td>string</td><td>Key for body type</td></tr><tr><td><code>body_text</code></td><td>string</td><td>Text representation of the body type (e.g., SUV)</td></tr><tr><td><code>cebia_report</code></td><td>string</td><td>Report from CEBIA</td></tr><tr><td><code>cena_na_leasing</code></td><td>string</td><td>Leasing price</td></tr><tr><td><code>cena_na_leasing_2</code></td><td>string</td><td>Alternative leasing price</td></tr><tr><td><code>color_klic</code></td><td>string</td><td>Key for car color</td></tr><tr><td><code>color_text</code></td><td>string</td><td>Text description of car color (e.g., gray metallic)</td></tr><tr><td><code>condition_klic</code></td><td>string</td><td>Key for the condition of the car (e.g., new)</td></tr><tr><td><code>condition_text</code></td><td>string</td><td>Text description of the car's condition (e.g., new vehicle)</td></tr><tr><td><code>custom_car_id</code></td><td>string</td><td>Custom car identifier</td></tr><tr><td><code>date_in</code></td><td>string</td><td>Date the car was listed (YYYY-MM-DD)</td></tr><tr><td><code>dojezd</code></td><td>string</td><td>Range of the car (in km)</td></tr><tr><td><code>dokumenty</code></td><td>string</td><td>Documents related to the car</td></tr><tr><td><code>emise</code></td><td>string</td><td>Emissions</td></tr><tr><td><code>engine_power</code></td><td>string</td><td>Engine power (in kW)</td></tr><tr><td><code>engine_power_klic</code></td><td>string</td><td>Key for engine power</td></tr><tr><td><code>engine_power_text</code></td><td>string</td><td>Text representation of engine power (e.g., kW)</td></tr><tr><td><code>engine_volume</code></td><td>string</td><td>Engine volume (in cubic centimeters)</td></tr><tr><td><code>equipment</code></td><td>string</td><td>Equipment list for the car</td></tr><tr><td><code>evid_cislo</code></td><td>string</td><td>Evidence number</td></tr><tr><td><code>financovani</code></td><td>string</td><td>Financing options</td></tr><tr><td><code>financovani_pozn</code></td><td>string</td><td>Financing notes (e.g., VAT deduction available)</td></tr><tr><td><code>first_owner</code></td><td>string</td><td>Indicates if the car is a first-owner vehicle (0 for no, 1 for yes)</td></tr><tr><td><code>fuel_klic</code></td><td>string</td><td>Key for fuel type</td></tr><tr><td><code>fuel_text</code></td><td>string</td><td>Fuel type text (e.g., hybrid - petrol)</td></tr><tr><td><code>kap_akumulatoru</code></td><td>string</td><td>Battery capacity</td></tr><tr><td><code>kategorie_klic</code></td><td>string</td><td>Key for vehicle category</td></tr><tr><td><code>kategorie_text</code></td><td>string</td><td>Text description of the vehicle category (e.g., new)</td></tr><tr><td><code>kind_klic</code></td><td>string</td><td>Key for the vehicle type</td></tr><tr><td><code>kind_text</code></td><td>string</td><td>Text description of the vehicle type (e.g., personal car)</td></tr><tr><td><code>made_date</code></td><td>string</td><td>Manufacture date (YYYY-MM)</td></tr><tr><td><code>manufacturer_klic</code></td><td>string</td><td>Key for the manufacturer</td></tr><tr><td><code>manufacturer_text</code></td><td>string</td><td>Text description of the manufacturer (e.g., Peugeot)</td></tr><tr><td><code>max_rychlost</code></td><td>string</td><td>Maximum speed (in km/h)</td></tr><tr><td><code>met_dojezdu_klic</code></td><td>string</td><td>Key for range information</td></tr><tr><td><code>met_dojezdu_text</code></td><td>string</td><td>Range information text (e.g., unspecified)</td></tr><tr><td><code>met_spotreby_klic</code></td><td>string</td><td>Key for fuel consumption</td></tr><tr><td><code>met_spotreby_text</code></td><td>string</td><td>Fuel consumption text (e.g., unspecified)</td></tr><tr><td><code>model_klic</code></td><td>string</td><td>Key for the car model</td></tr><tr><td><code>model_text</code></td><td>string</td><td>Text description of the car model (e.g., 3008)</td></tr><tr><td><code>nabijeci_doba_1</code></td><td>string</td><td>Charging time option 1</td></tr><tr><td><code>nabijeci_doba_2</code></td><td>string</td><td>Charging time option 2</td></tr><tr><td><code>nabijeci_doba_3</code></td><td>string</td><td>Charging time option 3</td></tr><tr><td><code>nabijeci_vykon_1</code></td><td>string</td><td>Charging power option 1</td></tr><tr><td><code>nabijeci_vykon_2</code></td><td>string</td><td>Charging power option 2</td></tr><tr><td><code>nabijeci_vykon_3</code></td><td>string</td><td>Charging power option 3</td></tr><tr><td><code>neverejny</code></td><td>string</td><td>Indicates whether the car is private or public</td></tr><tr><td><code>not_crashed</code></td><td>string</td><td>Indicates whether the car has been in a crash (0 for no, 1 for yes)</td></tr><tr><td><code>note</code></td><td>string</td><td>Additional notes about the car</td></tr><tr><td><code>odpocet_2</code></td><td>string</td><td>VAT deduction eligibility (1 for yes, 0 for no)</td></tr><tr><td><code>photo_3D</code></td><td>string</td><td>3D photo availability (1 for yes, 0 for no)</td></tr><tr><td><code>photos</code></td><td>string</td><td>Photos of the car</td></tr><tr><td><code>plug_in</code></td><td>string</td><td>Indicates whether the car is a plug-in hybrid (1 for yes, 0 for no)</td></tr><tr><td><code>pocet_dveri</code></td><td>string</td><td>Number of doors</td></tr><tr><td><code>pocet_mist</code></td><td>string</td><td>Number of seats</td></tr><tr><td><code>price</code></td><td>string</td><td>Price of the car</td></tr><tr><td><code>price_2</code></td><td>string</td><td>Alternative price</td></tr><tr><td><code>price_end</code></td><td>string</td><td>Final price</td></tr><tr><td><code>price_end_2</code></td><td>string</td><td>Final alternative price</td></tr><tr><td><code>price_mena_klic</code></td><td>string</td><td>Currency key (e.g., CZK)</td></tr><tr><td><code>price_mena_klic_2</code></td><td>string</td><td>Alternative currency key</td></tr><tr><td><code>price_mena_text</code></td><td>string</td><td>Currency text (e.g., CZK)</td></tr><tr><td><code>price_mena_text_2</code></td><td>string</td><td>Alternative currency text</td></tr><tr><td><code>price_puvodni</code></td><td>string</td><td>Original price</td></tr><tr><td><code>price_puvodni_2</code></td><td>string</td><td>Alternative original price</td></tr><tr><td><code>radkova_loga</code></td><td>string</td><td>Row logo</td></tr><tr><td><code>service_book</code></td><td>string</td><td>Service book availability (1 for yes, 0 for no)</td></tr><tr><td><code>spotreba</code></td><td>string</td><td>Fuel consumption</td></tr><tr><td><code>spotreba_jedn</code></td><td>string</td><td>Unit for fuel consumption (e.g., l for liters)</td></tr><tr><td><code>state_klic</code></td><td>string</td><td>State key (e.g., CZ for Czech Republic)</td></tr><tr><td><code>state_text</code></td><td>string</td><td>State text (e.g., Czech Republic)</td></tr><tr><td><code>stk_to</code></td><td>string</td><td>Technical inspection expiry date</td></tr><tr><td><code>t_moment</code></td><td>string</td><td>Torque</td></tr><tr><td><code>tachometr</code></td><td>string</td><td>Odometer reading (in km)</td></tr><tr><td><code>tachometr_unit_klic</code></td><td>string</td><td>Unit key for odometer reading</td></tr><tr><td><code>tachometr_unit_text</code></td><td>string</td><td>Unit text for odometer reading (e.g., km)</td></tr><tr><td><code>tuning</code></td><td>string</td><td>Tuning information</td></tr><tr><td><code>typ_akumulatoru_klic</code></td><td>string</td><td>Battery type key</td></tr><tr><td><code>typ_akumulatoru_text</code></td><td>string</td><td>Battery type text</td></tr><tr><td><code>typ_klic</code></td><td>string</td><td>Key for the car type</td></tr><tr><td><code>typ_text</code></td><td>string</td><td>Car type text (e.g., electric car)</td></tr><tr><td><code>vehicle_id</code></td><td>string</td><td>Unique identifier for the vehicle</td></tr><tr><td><code>vybava</code></td><td>string</td><td>Equipment list</td></tr><tr><td><code>vybava_text</code></td><td>string</td><td>Text representation of car equipment</td></tr><tr><td><code>vin</code></td><td>string</td><td>Vehicle identification number (VIN)</td></tr><tr><td><code>vstupni_certifikat</code></td><td>string</td><td>Input certificate availability (1 for yes, 0 for no)</td></tr><tr><td><code>vystupni_certifikat</code></td><td>string</td><td>Exit certificate availability (1 for yes, 0 for no)</td></tr><tr><td><code>warranty</code></td><td>string</td><td>Warranty availability (1 for yes, 0 for no)</td></tr></tbody></table>

</details>

## Success Response

```json
{
    "type": "JSON Data",
    "data": {
        "car_id": "12345",
        "car_data": {
            "custom_car_id": "12345",
            "manufacturer_text": "Ford",
            "model_text": "Focus",
            "price": "20000",
            "color_text": "Red",
            "condition_text": "New",
            "fuel_text": "Petrol",
            "body_text": "Hatchback"
        },
        "previous_id": "12344",
        "next_id": "12346"
    }
}
```

## Error Response

```json
{
    "type": "ERROR",
    "data": {
        "error": 401,
        "documentationLink": "https://sps-prosek-6.gitbook.io/projekt-api/endpoint-get-cars"
    }
}
```

## Error Codes Explanation

<table><thead><tr><th width="136">Error Code</th><th width="393">Description</th><th>Solution</th></tr></thead><tbody><tr><td><code>401</code></td><td>Missing ID parameter.</td><td>ID cannot be empty</td></tr><tr><td><code>402</code></td><td>Car not found.</td><td>Make sure the car is in the DB</td></tr><tr><td><code>403</code></td><td>Invalid scope parameter.</td><td>Scope must be one of the values <code>basic</code>, <code>extended</code>, <code>full</code></td></tr><tr><td><code>503</code></td><td>Server error (e.g. database connection issue).</td><td>Contact support</td></tr><tr><td><code>504</code></td><td>Error fetching car metadata.</td><td>Contact support</td></tr><tr><td><code>505</code></td><td>Error processing scope data.</td><td>Contact support</td></tr><tr><td><code>506</code></td><td>Error fetching previous or next car details.</td><td>Contact support</td></tr><tr><td><code>501</code></td><td>Error while sending error</td><td>Contact support</td></tr><tr><td><code>502</code></td><td>Failed to send response.</td><td>Contact support</td></tr><tr><td><code>551</code></td><td>Error fetching metadata for the car.</td><td>Contact support</td></tr></tbody></table>

