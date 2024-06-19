## INIT

**Purpose:** Signals the borrower's intent to proceed with the loan and provides fulfillment details for sanction requirements.

**Endpoint:** /init

**Method:** POST

**Description:** The buyer app uses this endpoint to inform the FI that the borrower intends to proceed with the loan and to provide details about the fulfillment of pre-sanction requirements, including KYC, document submission, and acceptance of operational limits.

**Steps:**
  - **Confirmation of Intent:** The borrower confirms their intent to proceed with the loan.
  - **Fulfilment Details:** The buyer app sends the INIT request with details about KYC completion (or scheduling), document submission status (including upload URLs), and confirmation of acceptance of the working capital limits.
  - **Process Initiation:** The FI initiates the loan processing steps.
  - **Response (ACK):** The FI sends an ACK response to the buyer app.


### Request Body

``` json
{
    "context": {
        "domain": "ONDC:FIS12",
        "location": {
            "country": {
                "code": "IND"
            },
            "city": {
                "code": "*"
            }
        },
        "transaction_id": "a9aaecca-10b7-4d19-b640-b047a7c62196",
        "message_id": "bb579fb8-cb82-4824-be12-fcbc405b6608",
        "action": "select",
        "timestamp": "2023-05-25T05:23:03.443Z",
        "version": "2.0.0",
        "bap_uri": "https://bap.credit.becknprotocol.io/",
        "bap_id": "bap.credit.becknprotocol.io",
        "ttl": "PT10M",
        "bpp_id": "bpp.credit.becknprotocol.org",
        "bpp_uri": "https://bpp.credit.becknprotocol.org"
    },
    "message": {
        "order": {
            "provider": {
                "id": "PROVIDER_ID"
            },
            "items": [
                {
                    "id": "ITEM_ID_WORKING_CAPITAL_LOAN",
                    "xinput": {
                        "form": {
                            "id": "F12"
                        },
                        "form_response": {
                            "status": "SUCCESS",
                            "submission_id": "F12_SUBMISSION_ID"
                        }
                    }
                }
            ]
        }
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

[← Back to Previous File](on_select_2.md) | [Next File →](on_init_1.md)

</p>

