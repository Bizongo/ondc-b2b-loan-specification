## ON_SEARCH


**Purpose:** Delivers loan offers from lenders in response to a SEARCH request

**Endpoint:** /on_search

**Method:** POST

**Description:** The FI's BPP responds to the peer-to-peer SEARCH request with this endpoint.


**Steps:**
  - **Process Form Data:** The FI's BPP retrieves the borrower's data using the FORM_SUBMISSION_ID.
  - **Generate Offers:** The FI evaluates the borrower's information and generates personalized loan offers.
  - **Send Response:** The FI's BPP sends the refined ON_SEARCH response, containing the tailored loan offers.


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
    "action": "on_select",
    "version": "2.0.0",
    "bap_id": "bap.credit.becknprotocol.io",
    "bap_uri": "https://bap.credit.becknprotocol.io/",
    "bpp_id": "bpp.credit.becknprotocol.org",
    "bpp_uri": "https://bpp.credit.becknprotocol.org",
    "transaction_id": "a9aaecca-10b7-4d19-b640-b047a7c62195",
    "message_id": "c8e3968c-cd78-4e46-aa34-0d541e46bd73",
    "timestamp": "2023-05-25T05:23:03.443Z",
    "ttl": "P30M"
  },
  "message": {
    "order": {
      "provider": {
        "id": "PROVIDER_ID"
      },
      "items": [
        {
          "id": "offer-pqr-789"
        }
      ],
      "fulfillment": {
        "type": "LOAN_SANCTION_DETAILS",
        "tags": [
          {
            "descriptor": {
              "code": "SANCTION_DETAILS",
              "name": "Final Sanction Details"
            },
            "tags": [
              {
                "descriptor": {
                  "code": "SANCTIONED_AMOUNT"
                },
                "value": 90000
              },
              {
                "descriptor": {
                  "code": "INTEREST_RATE"
                },
                "value": 13.5
              },
              {
                "descriptor": {
                  "code": "TENURE_MONTHS"
                },
                "value": 4
              },
              {
                "descriptor": {
                  "code": "PROCESSING_FEES"
                },
                "value": 1200
              }
            ]
          },
          {
            "descriptor": {
              "code": "LOAN_TERMS",
              "name": "Loan Terms"
            },
            "tags": [
              {
                "descriptor": {
                  "code": "GENERAL",
                  "name": "General Terms"
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "LOAN_AMOUNT",
                      "name": "Loan Amount"
                    },
                    "value": 75000
                  },
                  {
                    "descriptor": {
                      "code": "TOTAL_INTEREST_CHARGE",
                      "name": "Total Interest Charge",
                      "short_desc": "During entire tenure of loan"
                    },
                    "value": 20000
                  },
                  {
                    "descriptor": {
                      "code": "OTHER_UPFRONT_CHARGES",
                      "name": "Other up front charges",
                      "short_desc": "break-up of each component given below"
                    },
                    "value": 530
                  },
                  {
                    "descriptor": {
                      "code": "PROCESSING_FEE",
                      "name": "Processing fee"
                    },
                    "value": 231
                  },
                  {
                    "descriptor": {
                      "code": "INSURANCE_CHARGES",
                      "name": "Insurance charges"
                    },
                    "value": 231
                  },
                  {
                    "descriptor": {
                      "code": "OTHERS",
                      "name": "Others"
                    },
                    "value": 231
                  },
                  {
                    "descriptor": {
                      "code": "TENOR_OF_THE_LOAN",
                      "name": "Tenor of the loan",
                      "short_desc": "In month/days"
                    },
                    "value": "24 Months"
                  },
                  {
                    "descriptor": {
                      "code": "COUNTERPARTY_GSTIN_ALLOWED",
                      "name": "Counterparty GSTIN Alowed"
                    },
                    "value": "GSTIN1, GSTIN2, GSTIN3"
                  }
                ]
              },
              {
                "descriptor": {
                  "code": "CONTINGENT",
                  "name": "Contingent Terms"
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "RATE_ANNUALISED_PENAL_CHARGES",
                      "name": "Rate Annualised penal charges"
                    },
                    "value": 20000
                  },
                  {
                    "descriptor": {
                      "code": "ANNUALISED_OTH_PENAL_CHARGES",
                      "name": "Annualised oth penal charges",
                      "short_desc": "if any, details to be provided"
                    },
                    "value": 20000
                  }
                ]
              },
              {
                "descriptor": {
                  "code": "OTHERS",
                  "name": "Other Terms"
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "COOLING_OFF",
                      "name": "Cooling off",
                      "short_desc": "Look up period during which borrower shouldn't be charged any penalty on repayment loan."
                    },
                    "value": "12 Days"
                  }
                ]
              }
            ]
          }
        ]
      },
      "xinput": {
        "head": {
          "descriptor": {
            "name": "Loan Acceptance"
          },
          "index": {
            "min": 0,
            "cur": 2,
            "max": 2
          },
          "headings": [
            "Bank Statement & GST Returns",
            "Business & Financial Details",
            "Loan Acceptance"
          ]
        },
        "form": {
          "id": "form_accept_loan_terms_F03",
          "mime_type": "text/html",
          "url": "https://bpp.credit.becknprotocol.org/loans-kyc/xinput/form/form_accept_loan_terms/F03"
        },
        "required": true
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

[← Back to Previous File](search_2.md) | [Go to Form →](form_accept_loan_terms.md) | [Next File →](select_1.md)

</p>

