## ON_CONFIRM

**Purpose:** Provides the working capital line ID and details.

**Endpoint:** /on_confirm

**Method:** POST

**Description:** The FI uses this endpoint to formally confirm the loan and provide the working capital line ID and its details.

**Steps:**
  - **Loan Finalization:** The FI processes the CONFIRM request and finalizes the loan details.
  - **Send Confirmation:** The FI sends the ON_CONFIRM response to the buyer app, including the LINE_ID and LINE_DETAILS (like credit limit, available limit, start/end dates).
  - **Display Confirmation:** The buyer app displays the confirmation to the borrower.


### Request Body

``` json
{
  "context": {
    "domain": "ONDC:FIS",
    "version": "2.0.0",
    "action": "on_confirm",
    "bap_id": "bizongo-next.becknprotocol.io",
    "bap_uri": "https://bizongo-next.becknprotocol.io/",
    "bpp_id": "bpp.credit.becknprotocol.org",
    "bpp_uri": "https://bpp.credit.becknprotocol.org",
    "transaction_id": "a9aaecca-10b7-4d19-b640-b047a7c62195",
    "message_id": "c8e3968c-cd78-4e46-aa34-0d541e46bd71",
    "timestamp": "2023-05-25T05:23:03.443Z",
    "ttl": "P30M"
  },
  "message": {
    "order": {
      "provider": {
        "categories": [
          {
            "descriptor": {
              "code": "WORKING_CAPITAL_LOAN",
              "name": "Working Captail Loan"
            },
            "id": "101123"
          }
        ],
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
        },
        "id": "PROVIDER_ID",
        "items": [
          {
            "category_ids": [
              "101123"
            ],
            "descriptor": {
              "code": "WORKING_CAPITAL_LOAN",
              "name": "Working Captail Loan"
            },
            "id": "WORKING_CAPITAL_LOAN_ID",
            "matched": true,
            "recommended": true,
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
            ],
            "xinput": {
              "head": {
                "descriptor": {
                  "name": "Invoice Upload"
                },
                "index": {
                  "min": 0,
                  "cur": 0,
                  "max": 0
                },
                "headings": [
                  "Invoice Upload"
                ]
              },
              "form": {
                "id": "invoice_upload_form",
                "mime_type": "text/html",
                "url": "https://bpp.credit.becknprotocol.org/loans-kyc/xinput/form/invoice_upload_form"
              },
              "required": true
            }
          }
        ],
        "tags": [
          {
            "descriptor": {
              "code": "CONTACT_INFO",
              "name": "Contact Info"
            },
            "list": [
              {
                "descriptor": {
                  "code": "GRO_NAME",
                  "name": "Gro name"
                },
                "value": "ICICI"
              },
              {
                "descriptor": {
                  "code": "GRO_EMAIL",
                  "name": "Gro email"
                },
                "value": "lifeline@iciciprulife.com"
              },
              {
                "descriptor": {
                  "code": "GRO_CONTACT_NUMBER",
                  "name": "Gro contact number"
                },
                "value": "1860 266 7766"
              },
              {
                "descriptor": {
                  "code": "CUSTOMER_SUPPORT_LINK",
                  "name": "Customer support link"
                },
                "value": "https://buy.iciciprulife.com/buy/GrievanceRedStep.htm?execution=e1s1"
              },
              {
                "descriptor": {
                  "code": "CUSTOMER_SUPPORT_CONTACT_NUMBER",
                  "name": "Customer support contact number"
                },
                "value": "1800 1080"
              },
              {
                "descriptor": {
                  "code": "CUSTOMER_SUPPORT_EMAIL",
                  "name": "Customer support email"
                },
                "value": "customer.care@icicibank.com"
              }
            ]
          },
          {
            "descriptor": {
              "code": "LSP_INFO",
              "name": "Lsp Info"
            },
            "list": [
              {
                "descriptor": {
                  "code": "LSP_NAME",
                  "name": "Lsp name"
                },
                "value": "ICICI_LSP"
              },
              {
                "descriptor": {
                  "code": "LSP_EMAIL",
                  "name": "Lsp email"
                },
                "value": "lsp@iciciprulife.com"
              },
              {
                "descriptor": {
                  "code": "LSP_CONTACT_NUMBER",
                  "name": "Lsp contact number"
                },
                "value": "1860 266 7766"
              },
              {
                "descriptor": {
                  "code": "LSP_ADDRESS",
                  "name": "Lsp Address"
                },
                "value": "One Indiabulls centre, Tower 1, 18th Floor Jupiter mill compound 841, Senapati Bapat Marg, Elphinstone Road, Mumbai 400013"
              }
            ]
          }
        ]
      }
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

[← Back to Previous File](confirm.md) | [Go to Form →](form_invoice_upload.md) | [Next File →](update.md)

</p>

