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
    "domain": "ONDC:FIS12",
    "version": "2.1.0",
    "action": "on_init",
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
                        "value": 75000.00
                      },
                      {
                        "descriptor": {
                          "code": "TOTAL_INTEREST_CHARGE",
                          "name": "Total Interest Charge",
                          "short_desc": "During entire tenure of loan"
                        },
                        "value": 20000.00
                      },
                      {
                        "descriptor": {
                          "code": "OTHER_UPFRONT_CHARGES",
                          "name": "Other up front charges",
                          "short_desc": "break-up of each component given below"
                        },
                        "value": 530.00
                      },
                      {
                        "descriptor": {
                          "code": "PROCESSING_FEE",
                          "name": "Processing fee"
                        },
                        "value": 231.00
                      },
                      {
                        "descriptor": {
                          "code": "INSURANCE_CHARGES",
                          "name": "Insurance charges"
                        },
                        "value": 231.00
                      },
                      {
                        "descriptor": {
                          "code": "OTHERS",
                          "name": "Others"
                        },
                        "value": 231.00
                      },
                      {
                        "descriptor": {
                          "code": "TENOR_OF_THE_LOAN",
                          "name": "Tenor of the loan",
                          "short_desc": "In month/days"
                        },
                        "value": "24 Months"
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
                        "value": 20000.00
                      },
                      {
                        "descriptor": {
                          "code": "ANNUALISED_OTH_PENAL_CHARGES",
                          "name": "Annualised oth penal charges",
                          "short_desc": "if any, details to be provided"
                        },
                        "value": 20000.00
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
                      },
                      {
                        "descriptor": {
                          "code": "DETAILS_OF_LSP",
                          "name": "Details of LSP",
                          "short_desc": "Acting as recovery agent and authorised to approach borrower"
                        },
                        "value": "Contact details to be provided"
                      }
                    ]
                  }
                ]
              },
              {
                "descriptor": {
                  "code": "SANCTION_REQUIREMENTS",
                  "name": "Additional Requirements"
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "ENACH_SETUP",
                      "name": "eNACH Setup"
                    },
                    "tags": [
                      {
                        "descriptor": {
                          "code": "LINK"
                        },
                        "value": "https://www.icicibank.com/enach-setup"
                      }
                    ]
                  },
                  {
                    "descriptor": {
                      "code": "BANK_VERIFICATION",
                      "name": "Bank Verification"
                    },
                    "tags": [
                      {
                        "descriptor": {
                          "code": "MODE"
                        },
                        "value": "PENNY_DROP"
                      },
                    ]
                  },
                  {
                    "descriptor": {
                      "code": "BORROWER_BANK_ACCOUNT", 
                      "name": "Borrower Bank Account Details" 
                    },
                    "tags": [ 
                      {
                        "descriptor": {
                          "code": "REQUIRED"
                        },
                        "value": true 
                      }
                    ]
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

[← Back to Previous File](init.md) | [Next File →](confirm.md)

</p>

