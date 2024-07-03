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
    "action": "on_search",
    "bap_id": "bap.credit.becknprotocol.io",
    "bap_uri": "https://bap.credit.becknprotocol.io/",
    "bpp_id": "bpp.credit.becknprotocol.org",
    "bpp_uri": "https://bpp.credit.becknprotocol.org",
    "domain": "ONDC:FIS12",
    "location": {
      "city": {
        "code": "*"
      },
      "country": {
        "code": "IND"
      }
    },
    "message_id": "bb579fb8-cb82-4824-be12-acbc415b6608",
    "timestamp": "2023-05-25T05:23:03.443Z",
    "transaction_id": "a9aaecca-10b7-4d19-b640-b047a7c62196",
    "ttl": "PT30M",
    "version": "2.0.0"
  },
  "message": {
    "catalog": {
      "descriptor": {
        "name": "ICICI Bank"
      },
      "providers": [
        {
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

[← Back to Previous File](search_2.md) | [Go to Form →](form_accept_loan_terms.md) | [Next File →](select_1.md)

</p>

