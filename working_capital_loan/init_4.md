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
    "version": "2.1.0",
    "action": "on_select",
    "bap_id": "bap.credit.becknprotocol.io",
    "bap_uri": "https://bap.credit.becknprotocol.io/",
    "transaction_id": "a9aaecca-10b7-4d19-b640-b047a7d62196",
    "message_id": "bb579fb8-cb82-4824-be12-fcbc405b6608",
    "ttl": "PT30M",
    "timestamp": "2023-05-25T05:23:03.443Z",
    "bpp_id": "bpp.credit.becknprotocol.org",
    "bpp_uri": "https://bpp.credit.becknprotocol.org"
  },
  "message": {
    "order": {
      "provider": {
        "id": "PROVIDER_ID"
      },
      "fulfillments": [
        {
          "id": "1333",
          "customer": {
            "person": {
              "name": "John Doe",
              "dob": "12-09-1998",
              "gender": "Male",
              "creds": [
                {
                  "id": "BXU87Y252U",
                  "type": "PAN"
                }
              ]
            }
          }
        },
        {
          "id": "1334",
          "customer": {
            "person": {
              "name": "Co Applicant 1",
              "dob": "12-09-1998",
              "gender": "Male",
              "creds": [
                {
                  "id": "BXU87Y252A",
                  "type": "PAN"
                }
              ]
            }
          }
        }
      ],
      "items": [
        {
          "id": "CHILD_ITEM_ID_WORKING_CAPITAL_LOAN",
          "parent_item_id": "ITEM_ID_WORKING_CAPITAL_LOAN",
          "xinput": {
            "form": {
              "id": "<form_esign_F07>"
            },
            "form_response": {
              "status": "SUCCESS",
              "submission_id": "<form_submission_id_esign_F07>"
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

[← Back to Previous File](on_status_3.md) | [Next File →](on_init_4.md)

</p>

