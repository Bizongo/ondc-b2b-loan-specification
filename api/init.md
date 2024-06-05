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
    "bap_id": "bap.credit.becknprotocol.io",
    "bap_uri": "https://bap.credit.becknprotocol.io/",
    "transaction_id": "uuid-90215d70-c146-48a9-8c11-680123456789",
    "message_id": "uuid-789abcdef0-1234-5678-90ab-cdef12345678",
    "timestamp": "2024-05-21T10:10:00Z",
    "bpp_id": "bpp.credit.becknprotocol.org",
    "bpp_uri": "https://bpp.credit.becknprotocol.org"
  },
  "message": {
    "order": {
      "items": [
        "ITEM_ID_INVOICE_LOAN_ICICI"
      ],
      "fulfillment": {
        "type": "LOAN_REQUIREMENTS",
        "tags": [
          {
            "descriptor": {
              "code": "KYC_PROCESS",
              "name": "KYC Process Details"
            },
            "tags": [
              {
                "descriptor": {
                  "code": "MODE"
                },
                "value": "ONLINE"
              },
              {
                "descriptor": {
                  "code": "STATUS"
                },
                "value": "COMPLETED"
              },
              {
                "descriptor": {
                  "code": "SCHEDULED_DATE"
                },
                "value": "2024-05-28"
              }
            ]
          },
          {
            "descriptor": {
              "code": "DOCUMENT_SUBMISSION",
              "name": "Document Submission Requirements"
            },
            "tags": [
              {
                "descriptor": {
                  "code": "DOCUMENTS_REQUIRED",
                  "name": "Required Documents"
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "SUBMISSION_STATUS"
                    },
                    "value": "COMPLETED"
                  },
                  {
                    "descriptor": {
                      "code": "UPLOAD_URL"
                    },
                    "value": "https://buyer-app.example.com/documents?token=secure_token"
                  }
                ]
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
                  "code": "BORROWER_ACCEPTED"
                },
                "value": true
              }
            ]
          }
        ]
      },
      "created_at": "2024-05-21T10:15:00Z",
      "updated_at": "2024-05-21T10:15:00Z"
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

