## CONFIRM

**Purpose:** Confirms the borrower's acceptance of the final sanction details and loan terms and provides confirmation of fulfillment for sanction requirements.

**Endpoint:** /confirm

**Method:** POST

**Description:** The buyer app uses this endpoint to send the borrower's final confirmation to the FI, including their acceptance of the sanction details, loan terms, and the fulfillment status of additional requirements.

**Steps:**
  - **Review and Acceptance:** The borrower reviews the final sanction details, loan terms, and any additional requirements.
  - **Fulfill Requirements:** The borrower completes any outstanding requirements (e.g., owner KYC, eNACH setup).
  - **Confirmation:** The buyer app sends the CONFIRM request, indicating the borrower's acceptance of the loan terms and the completion status of the additional requirements.
  - **Response (ACK):** The FI sends an ACK response.



### Request Body

``` json
{
  "context": {
    "domain": "ONDC:FIS12",
    "version": "2.1.0",
    "action": "confirm",
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

[← Back to Previous File](on_status_4.md) | [Next File →](on_confirm.md)

</p>

