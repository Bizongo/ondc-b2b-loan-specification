## ON_CONFIRM

**Purpose:** Provides the working capital line ID and details.

**Endpoint:** /on_confirm

**Method:** POST

**Description:** The FI uses this endpoint to formally confirm the loan and provide the working capital line ID and its details.

**Steps:**
  - **Loan Finalization:** The FI processes the CONFIRM request and finalizes the loan details.
  - **Send Confirmation:** The FI sends the ON_CONFIRM response to the buyer app, including the LINE_ID and LINE_DETAILS (like credit limit, available limit, start/end dates).
  - **Display Confirmation:** The buyer app displays the confirmation to the borrower.


### Request Body

``` json
{
  "context": {
    "domain": "ONDC:FIS12",
    "version": "2.1.0",
    "action": "on_confirm",
    "bap_id": "bap.credit.becknprotocol.io",
    "bap_uri": "https://bap.credit.becknprotocol.io/",
    "transaction_id": "a9aaecca-10b7-4d19-b640-b047a7c62196",
    "message_id": "bb579fb8-cb82-4824-be12-fcbc405b6608",
    "ttl": "PT30M",
    "timestamp": "2023-05-25T05:23:03.443Z",
    "bpp_id": "bpp.credit.becknprotocol.org",
    "bpp_uri": "https://bpp.credit.becknprotocol.org"
  },
  "message": {
    "list": [
      {
        "fi_name": "ICICI Bank",
        "fi_catalog": {
          "id": "PROVIDER_ID",
          "offer_details": {
            "descriptor": {
              "name": "Invoice based Loan"
            },
            "tags": [
              {
                "descriptor": {
                  "code": "WORKING_CAPITAL_LINE",
                  "name": "Working Capital Line"
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "LINE_ID"
                    },
                    "value": "WCL-1234567890"
                  },
                  {
                    "descriptor": {
                      "code": "LINE_DETAILS"
                    },
                    "value": {
                      "limit": 100000,
                      "available_limit": 100000,
                      "start_date": "2024-05-22",
                      "end_date": "2025-05-21"
                    }
                  }
                ]
              }
            ]
          }
        }
      }
    ]
  }
}
```

### Response

```json
{
  "message": {
    "ack": {
      "status": "ACK"
    }
  }
}
```


---

<p align="center">

[← Back to Previous File](confirm.md) | [Next File →](update.md)

</p>

