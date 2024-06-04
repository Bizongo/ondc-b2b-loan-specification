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
    "tags": [
      {
        "descriptor": {
          "code": "LOAN_REQUEST",
          "name": "Loan Request Details"
        },
        "tags": [
          {
            "descriptor": {
              "code": "LOAN_AMOUNT"
            },
            "value": 100000
          },
          {
            "descriptor": {
              "code": "MAXIMUM_ACCEPTABLE_RATE"
            },
            "value": 15
          }
        ]
      },
      {
        "descriptor": {
          "code": "INVOICE_DATA",
          "name": "Invoice Details"
        },
        "tags": [
          {
            "descriptor": {
              "code": "INVOICE"
            },
            "items": [
              {
                "id": "invoice-item-1",
                "descriptor": {
                  "name": "Invoice 1"
                },
                "price": {
                  "currency": "INR",
                  "value": "85000"
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "INVOICE_NUMBER"
                    },
                    "value": "INV-2024-05-001"
                  },
                  {
                    "descriptor": {
                      "code": "INVOICE_DATE"
                    },
                    "value": "2024-05-10"
                  }
                ]
              }
            ]
          },
          {
            "descriptor": {
              "code": "BULK_INVOICE_LINK"
            },
            "value": "https://api.example.com/invoices/download?token=bulk_download_token"
          }
        ]
      },
      {
        "descriptor": {
          "code": "GST",
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
          },
          {
            "descriptor": {
              "code": "GST_RETURN_PERIOD"
            },
            "value": 4
          },
          {
            "descriptor": {
              "code": "GST_RETURNS_LINK" 
            },
            "value": "https://api.example.com/gst-returns/download?token=gst_zip_token"
          }
        ]
      },
      {
        "descriptor": {
          "code": "BANK_STATEMENT",
          "name": "Bank Statement"
        },
        "tags": [
          {
            "descriptor": {
              "code": "USE_ACCOUNT_AGGREGATOR"
            },
            "value": true
          },
          {
            "descriptor": {
              "code": "AGGREGATOR_NAME"
            },
            "value": "perfios"
          },
          {
            "descriptor": {
              "code": "STATEMENT_PERIOD_MONTHS"
            },
            "value": 12
          },
           {
            "descriptor": {
              "code": "BANK_STATEMENT_LINK" 
            },
            "value": "https://api.example.com/bank-statements/download?token=statement_zip_token"
          }
        ]
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

[Next File →](on_search.md)

</p>
