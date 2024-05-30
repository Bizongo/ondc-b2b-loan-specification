## UPDATE

**Purpose:** Updates the loan status and provides details for invoice financing and disbursement.

**Endpoint:** /update

**Method:** POST

**Description:** The buyer app uses this endpoint to provide details about the invoices the borrower wants to finance against their working capital line.

**Steps:**
  - **Invoice Selection:** The borrower, using the buyer app, selects the invoices for financing.
  - **Send Invoice Details:** The buyer app sends the UPDATE request, including the WORKING_CAPITAL_LINE_ID, the selected invoices with their details and buyer acceptance status, and the borrower's bank account details for disbursement.
  - **Invoice Processing:** The FI starts processing the invoices.
  - **Response (ACK):** The FI sends an ACK response to the buyer app.


### Request Body

``` json
{
  "context": {
    "domain": "ONDC:FIS12",
    "version": "2.1.0",
    "action": "update",
    "bap_id": "buyer-app-abc.becknprotocol.io",
    "bap_uri": "https://buyer-app-abc.becknprotocol.io/",
    "transaction_id": "uuid-90215d70-c146-48a9-8c11-680123456789",
    "message_id": "uuid-abcdef012-3456-7890-abcd-ef0123456789",
    "timestamp": "2024-05-21T11:00:00Z",
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
                  "code": "WORKING_CAPITAL_LINE",
                  "name": "Working Capital Line"
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "LINE_ID"
                    },
                    "value": "WCL-1234567890"
                  }
                ]
              },
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
                        "invoice_date": "2024-06-05",
                        "invoice_amount": 60000,
                        "seller_gstin": "98ZYXWV9876543210U",
                        "download_link": "https://api.example.com/invoices/INV-2024-06-001?token=ghi789",
                        "buyer_acceptance": {
                          "status": "COMPLETED",
                          "timestamp": "2024-06-06T09:30:00Z"
                        }
                      },
                      {
                        "invoice_number": "INV-2024-06-002",
                        "invoice_date": "2024-06-10",
                        "invoice_amount": 45000,
                        "seller_gstin": "76FEDCBA5432109876",
                        "download_link": "https://api.example.com/invoices/INV-2024-06-002?token=jkl456",
                        "buyer_acceptance": {
                          "status": "COMPLETED",
                          "timestamp": "2024-06-11T10:45:00Z"
                        }
                      }
                    ]
                  }
                ]
              },
              {
                "descriptor": {
                  "code": "DISBURSEMENT_BANK_ACCOUNT",
                  "name": "Disbursement Bank Account"
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

[← Back to Previous File](on_confirm.md) | [Next File →](on_update.md)

</p>

