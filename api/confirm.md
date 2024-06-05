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
    "transaction_id": "uuid-90215d70-c146-48a9-8c11-680123456789",
    "message_id": "uuid-abcdef012-3456-7890-abcd-ef0123456789",
    "timestamp": "2024-05-21T10:20:00Z",
    "bpp_id": "bpp.credit.becknprotocol.org",
    "bpp_uri": "https://bpp.credit.becknprotocol.org"
  },
  "message": {
    "order": {
      "id": "order-id-123",
      "items": [
        {
          "id": "offer-pqr-789"
        }
      ],
      "tags": [
        {
          "descriptor": {
            "code": "SANCTION_ACCEPTANCE",
            "name": "Sanction Acceptance"
          },
          "value": true
        },
        {
          "descriptor": {
            "code": "LOAN_TERMS_ACCEPTED",
            "name": "Loan Terms Acceptance"
          },
          "value": true
        },
        {
          "descriptor": {
            "code": "SANCTION_REQUIREMENTS",
            "name": "Sanction Requirements Confirmation"
          },
          "tags": [
            {
              "descriptor": {
                "code": "OWNERS_KYC",
                "name": "Owner KYC"
              },
              "tags": [
                {
                  "descriptor": {
                    "code": "STATUS"
                  },
                  "value": "COMPLETED"
                }
              ]
            },
            {
              "descriptor": {
                "code": "ENACH_SETUP",
                "name": "eNACH Setup"
              },
              "tags": [
                {
                  "descriptor": {
                    "code": "STATUS"
                  },
                  "value": "COMPLETED"
                }
              ]
            },
            {
              "descriptor": {
                "code": "BANK_ACCOUNT_VERIFICATION",
                "name": "Bank Account Verification"
              },
              "tags": [
                {
                  "descriptor": {
                    "code": "STATUS"
                  },
                  "value": "COMPLETED"
                }
              ]
            },
            {
              "descriptor": {
                "code": "BANK_ACCOUNT_DETAILS",
                "name": "Bank Account Details"
              },
              "tags": [
                {
                  "descriptor": {
                    "code": "ACCOUNT_HOLDER_NAME"
                  },
                  "value": "John Doe"
                },
                {
                  "descriptor": {
                    "code": "ACCOUNT_NUMBER"
                  },
                  "value": "123456789012"
                },
                {
                  "descriptor": {
                    "code": "IFSC_CODE"
                  },
                  "value": "ABCD0001234"
                },
                {
                  "descriptor": {
                    "code": "BANK_NAME"
                  },
                  "value": "Example Bank"
                }
              ]
            }
          ]
        }
      ],
      "created_at": "2024-05-21T10:20:00Z",
      "updated_at": "2024-05-21T10:20:00Z"
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

[← Back to Previous File](on_init.md) | [Next File →](on_confirm.md)

</p>

