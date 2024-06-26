## ON_SELECT

**Purpose:** Provides KYC details, operational limits, and document requirements for the selected loan offer.

**Endpoint:** /on_select

**Method:** POST

**Description:** The ONDC network (or the selected FI) uses this endpoint to send detailed information about the selected loan offer, including KYC requirements, working capital limits, and document submission details.

**Steps:**
  - **Prepare Offer Details:** The FI prepares details about the KYC process, operational limits, and document requirements.
  - **Send Details:** The network sends the ON_SELECT response to the buyer app, including the detailed information about the selected offer.
  - **Present Details:** The buyer app displays the details to the borrower.



### Request Body

``` json
{
  "context": {
    "domain": "ONDC:FIS",
    "version": "2.0.0",
    "action": "on_select",
    "bap_id": "bizongo-next.becknprotocol.io",
    "bap_uri": "https://bizongo-next.becknprotocol.io/",
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
            "name": "Field Visit"
          },
          "index": {
            "min": 0,
            "cur": 0,
            "max": 0
          },
          "headings": [ 
           "Field Visit" 
          ]
        },
        "form": {
          "id": "ACCEPTANCE_FORM",
          "mime_type": "application/html",
          "url": "https://bpp.credit.becknprotocol.org/loans-kyc/xinput/form/form_addtional_kyc_field_visit/F03"
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

[← Back to Previous File](select_1.md) | [Go to Form →](form_addtional_kyc_field_visit.md) | [Next File →](init_1.md)

</p>

