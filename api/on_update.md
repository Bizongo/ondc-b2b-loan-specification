## ON_UPDATE

**Purpose:** Provides the status of invoice acceptance/rejection, repayment schedule, and repayment account details.

**Endpoint:** /on_update

**Method:** POST

**Description:** The FI uses this endpoint to send updates about the financing request to the buyer app.

**Steps:**
  - **Invoice Evaluation:** The FI evaluates the invoices submitted for financing.
  - **Repayment Schedule Calculation:** The FI calculates the repayment schedule, including due dates, amounts, and interest.
  - **Send Update:** The FI sends the ON_UPDATE response to the buyer app, including the status of each invoice (accepted or rejected with a reason), the calculated repayment schedule, repayment account details, and disbursement details (payment mode and UTR number if applicable).
  - **Display Update:** The buyer app displays the update to the borrower.


### Request Body

``` json
{
  "context": {
    "domain": "ONDC:FIS12",
    "version": "2.1.0",
    "action": "on_update",
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
        "fi_name": "TATA Capital",
        "fi_catalog": {
          "id": "PROVIDER_ID",
          "offer_details": {
            "descriptor": {
              "name": "Invoice based Loan"
            },
            "tags": [
              {
                "descriptor": {
                  "code": "INVOICE_FINANCING",
                  "name": "Invoice Financing Details"
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "INVOICE"
                    },
                    "list": [
                      {
                        "invoice_number": "INV-2024-06-001",
                        "status": "ACCEPTED",
                        "disbursement_status": "PENDING"
                      },
                      {
                        "invoice_number": "INV-2024-06-002",
                        "status": "REJECTED",
                        "disbursement_status": "PENDING"
                      }
                    ]
                  }
                ]
              },
              {
                "descriptor": {
                  "code": "REPAYMENT_SCHEDULE",
                  "name": "Repayment Schedule"
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "REPAYMENT"
                    },
                    "list": [
                      {
                        "due_date": "2024-07-05",
                        "amount": 25000,
                        "interest_percentage": 1.25
                      },
                      {
                        "due_date": "2024-08-05",
                        "amount": 25000,
                        "interest_percentage": 1.25
                      },
                      {
                        "due_date": "2024-09-05",
                        "amount": 25000,
                        "interest_percentage": 1.25
                      },
                      {
                        "due_date": "2024-10-05",
                        "amount": 25000,
                        "interest_percentage": 1.25
                      }
                    ]
                  }
                ]
              },
              {
                "descriptor": {
                  "code": "REPAYMENT_ACCOUNT",
                  "name": "Repayment Account Details"
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "ACCOUNT_HOLDER_NAME"
                    },
                    "value": "TATA Capital"
                  },
                  {
                    "descriptor": {
                      "code": "ACCOUNT_NUMBER"
                    },
                    "value": "98765432101234"
                  },
                  {
                    "descriptor": {
                      "code": "IFSC_CODE"
                    },
                    "value": "DCBA0123456"
                  },
                  {
                    "descriptor": {
                      "code": "BANK_NAME"
                    },
                    "value": "Capital Bank"
                  }
                ]
              },
              {
                "descriptor": {
                  "code": "DISBURSEMENT_DETAILS",
                  "name": "Disbursement Details"
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "PAYMENT_MODE"
                    },
                    "value": "SINGLE" // Or "MULTIPLE" if disbursed per invoice
                  },
                  {
                    "descriptor": {
                      "code": "UTR_NUMBER"
                    },
                    "value": "UTR1234567890"
                  }
                  // If PAYMENT_MODE is MULTIPLE, provide UTRs per invoice 
                  // using a similar structure to the INVOICE list
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

[← Back to Previous File](update.md) | [Next File →](status.md)

</p>

