## SEARCH


**Purpose:** Initiates a search for working capital loan offers.

**Endpoint:** /search

**Method:** POST

**Description:** The buyer app (Bizongo Next) uses this endpoint to send a loan request to the ONDC network.

**Steps:**
  - **Request Loan Offers:** The buyer app sends a SEARCH request to the ONDC network, specifying the borrower's GST details, selected invoices, bank statement information, desired loan amount, interest rate preferences, and repayment preferences.

  - **Network Broadcast:** The ONDC network broadcasts the SEARCH request to registered FIs.

  - **FI Evaluation:** Interested FIs evaluate the loan request based on their criteria.

  - **Response (ACK):** The network sends an acknowledgment (ACK) response to the buyer app, indicating that the request has been received and is being processed.


### Request Body

``` json
{
  "context": {
    "domain": "ONDC:FIS12",
    "version": "2.1.0",
    "action": "search",
    "bap_id": "buyer-app-abc.becknprotocol.io",
    "bap_uri": "https://buyer-app-abc.becknprotocol.io/",
    "transaction_id": "uuid-90215d70-c146-48a9-8c11-680123456789",
    "message_id": "uuid-123e4567-e89b-12d3-a456-426614174000",
    "timestamp": "2024-05-21T10:00:00Z",
    "ttl": "PT5M",
    "location": {
      "city": {
        "code": "*"
      },
      "country": {
        "code": "IND"
      }
    }
  },
  "message": {
    "intent": {
      "category": {
        "descriptor": {
          "code": "WORKING_CAPITAL_LOAN"
        }
      }
    },
    "criteria": {
      "gst": {
        "descriptor": {
          "name": "GST Information"
        },
        "tags": [
          {
            "descriptor": {
              "code": "GSTIN"
            },
            "value": "12ABCDE3456F7G8H9I"
          },
          {
            "descriptor": {
              "code": "BUSINESS_NAME"
            },
            "value": "Example Trader"
          },
          {
            "descriptor": {
              "code": "BUSINESS_TYPE"
            },
            "value": "Proprietorship"
          },
          {
            "descriptor": {
              "code": "REGISTRATION_DATE"
            },
            "value": "2022-08-01"
          }
        ]
      },
      "invoices": {
        "descriptor": {
          "name": "Invoice Data"
        },
        "tags": [
          {
            "descriptor": {
              "code": "INVOICE"
            },
            "list": [
              {
                "invoice_number": "INV-2024-05-001",
                "invoice_date": "2024-05-10",
                "invoice_amount": 85000,
                "seller_gstin": "98ZYXWV9876543210U",
                "download_link": "https://api.example.com/invoices/INV-2024-05-001?token=abc123"
              },
              {
                "invoice_number": "INV-2024-05-002",
                "invoice_date": "2024-05-15",
                "invoice_amount": 120000,
                "seller_gstin": "76FEDCBA5432109876",
                "download_link": "https://api.example.com/invoices/INV-2024-05-002?token=def456"
              }
            ]
          },
          {
            "descriptor": {
              "code": "BULK_INVOICES_LINK"
            },
            "value": "https://api.example.com/invoices/download-zip?token=bulk_download_token"
          }
        ]
      },
      "bank_statement": {
        "descriptor": {
          "name": "Bank Statement"
        },
        "tags": [
          {
            "descriptor": {
              "code": "FETCH_MODE"
            },
            "value": "ONLINE"
          },
          {
            "descriptor": {
              "code": "SERVICE_PROVIDER"
            },
            "value": "Perfios"
          },
          {
            "descriptor": {
              "code": "STATEMENT_LINK"
            },
            "value": "https://api.perfios.com/v2/statements/download?token=xyz123"
          },
          {
            "descriptor": {
              "code": "STATEMENT_PERIOD"
            },
            "value": "2024-04-01_to_2024-04-30"
          }
        ]
      },
      "loan_amount": {
        "descriptor": {
          "name": "Desired Loan Amount"
        },
        "value": 100000
      },
      "loan_interest_rate": {
        "descriptor": {
          "name": "Loan Interest Rate"
        },
        "tags": [
          {
            "descriptor": {
              "code": "MAXIMUM_ACCEPTABLE_RATE"
            },
            "value": 15
          }
        ]
      },
      "loan_repayment": {
        "descriptor": {
          "name": "Loan Repayment"
        },
        "tags": [
          {
            "descriptor": {
              "code": "PREFERRED_TENURE_MONTHS"
            },
            "list": [
              3,
              6
            ]
          }
        ]
      }
    },
    "payment": {
      "collected_by": "BPP",
      "tags": [
        {
          "descriptor": {
            "code": "BUYER_FINDER_FEES"
          },
          "display": false,
          "list": [
            {
              "descriptor": {
                "code": "BUYER_FINDER_FEES_TYPE"
              },
              "value": "percent-annualized"
            },
            {
              "descriptor": {
                "code": "BUYER_FINDER_FEES_PERCENTAGE"
              },
              "value": "1"
            }
          ]
        },
        {
          "descriptor": {
            "code": "SETTLEMENT_TERMS"
          },
          "display": false,
          "list": [
            {
              "descriptor": {
                "code": "DELAY_INTEREST"
              },
              "value": "2.5"
            },
            {
              "descriptor": {
                "code": "STATIC_TERMS"
              },
              "value": "https://bap.credit.becknprotocol.io/personal-banking/loans/personal-loan"
            },
            {
              "descriptor": {
                "code": "OFFLINE_CONTRACT"
              },
              "value": "true"
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

[Next File →](on_search.md)

</p>