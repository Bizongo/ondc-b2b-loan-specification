## ON_INIT

**Purpose:** Provides final sanction details, loan terms, and any additional requirements for loan disbursement.

**Endpoint:** /on_init

**Method:** POST

**Description:** The FI uses this endpoint to send the final loan sanction details and terms to the buyer app.

**Steps:**
  - **Loan Sanction:** The FI processes the INIT request, performs final checks, and sanctions the loan.
  - **Final Details and Terms:** The FI sends the ON_INIT response with the final sanction details (amount, interest rate, tenure, fees), detailed loan terms, and any additional requirements (e.g., owner KYC, eNACH setup, bank account verification).
  - **Present Details:** The buyer app displays the final sanction details and loan terms to the borrower.




### Request Body

``` json
{
  "context": {
    "domain": "ONDC:FIS",
    "version": "2.0.0",
    "action": "on_init",
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
        "id": "PROVIDER_ID",
        "descriptor": {
          "images": [
            {
              "size_type": "sm",
              "url": "https://www.icicibank.com/content/dam/icicibank/india/assets/images/header/logo.png"
            }
          ],
          "long_desc": "ICICI Bank Ltd, India.",
          "name": "ICICI Bank",
          "short_desc": "ICICI Bank Ltd"
        }
      },
      "items": [
        {
          "id": "WORKING_CAPITAL_LOAN_ID",
          "descriptor": {
            "code": "WORKING_CAPITAL_LOAN",
            "name": "Working Captail Loan"
          },
          "tags": [
            {
              "descriptor": {
                "code": "SANCTION_DETAILS",
                "name": "Final Sanction Details"
              },
              "list": [
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
                  "list": [
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
                  "list": [
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
                  "list": [
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
          ],
          "xinput": {
            "head": {
              "descriptor": {
                "name": "Verify Bank Account"
              },
              "index": {
                "min": 0,
                "cur": 2,
                "max": 3
              },
              "headings": [
                "KYC Verification"
                "Physical Verification",
                "Verify Bank Account",
                "eNACH Setup",
              ]
            },
            "form": {
              "id": "KYC_LINK",
              "mime_type": "application/html",
              "url": "https://bpp.credit.becknprotocol.org/xinput/link/link_verify_bank_details"
            },
            "required": true
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

[← Back to Previous File](init_3.md) | [Go to Form →](link_verify_bank_details.md) | [Next File →](on_status_3.md)

</p>

