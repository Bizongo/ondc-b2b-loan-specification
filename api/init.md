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
    "action": "init",
    "bap_id": "buyer-app-abc.becknprotocol.io",
    "bap_uri": "https://buyer-app-abc.becknprotocol.io/",
    "transaction_id": "uuid-90215d70-c146-48a9-8c11-680123456789", 
    "message_id": "uuid-0123456789abcdef-1234-5678-90ab-cdef01234567",
    "timestamp": "2024-05-21T10:15:00Z",
    "bpp_id": "bpp.credit.becknprotocol.org",
    "bpp_uri": "https://bpp.credit.becknprotocol.org"
  },
  "message": {
    "order": {
      "provider": {
        "id": "lender-xyz" 
      },
      "items": [
        {
          "id": "offer-pqr-789" 
        }
      ],
      "tags": [
        {
          "descriptor": {
            "code": "KYC_PROCESS",
            "name": "KYC Process" 
          },
          "tags": [
            {
              "descriptor": {
                "code": "STATUS"
              },
              "value": "COMPLETED" // Or "PENDING" if offline
            },
            {
              "descriptor": {
                "code": "SCHEDULED_DATE" // If offline
              },
              "value": "2024-05-28" // Provided by buyer app
            }
          ]
        },
        {
          "descriptor": {
            "code": "DOCUMENT_SUBMISSION",
            "name": "Document Submission"
          },
          "tags": [
            {
              "descriptor": {
                "code": "FORM_ID"
              },
              "value": "F001-ICICI"
            },
            {
              "descriptor": {
                "code": "SUBMISSION_STATUS" 
              },
              "value": "COMPLETED"
            }
          ]
        },
        {
          "descriptor": {
            "code": "WORKING_CAPITAL_LIMITS",
            "name": "Working Capital Limits"
          },
          "tags": [
            {
              "descriptor": {
                "code": "COUNTERPARTY_GSTINS",
                "name": "Allowed Counterparty GSTINs" 
              },
              "list": [
                "98ZYXWV9876543210U",
                "76FEDCBA5432109876" 
              ]
            },
            {
              "descriptor": {
                "code": "COUNTERPARTY_ACCEPTANCE", 
                "name": "Counterparty Acceptance Required" 
              },
              "value": true
            },
            {
              "descriptor": {
                "code": "ACCEPTED"
              },
              "value": true
            }
          ]
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

[← Back to Previous File](on_select.md) | [Next File →](on_init.md)

</p>

