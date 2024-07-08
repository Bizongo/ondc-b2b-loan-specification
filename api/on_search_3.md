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
    "version": "2.0.0",
    "action": "on_search",
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
    "catalog": {
      "descriptor": {
        "name": "ICICI Bank"
      },
      "providers": [
        {
          "id": "PROVIDER_ID",
          "descriptor": {
            "images": [
              {
                "url": "https://www.icicibank.com/content/dam/icicibank/india/assets/images/header/logo.png",
                "size_type": "sm"
              }
            ],
            "name": "ICICI Bank",
            "short_desc": "ICICI Bank Ltd",
            "long_desc": "ICICI Bank Ltd, India."
          },
          "categories": [
            {
              "id": "101123",
              "descriptor": {
                "code": "WORKING_CAPITAL_LOAN",
                "name": "Working Captail Loan"
              }
            }
          ],
          "items": [
            {
              "id": "CHILD_ITEM_ID_WORKING_CAPITAL_LOAN",
              "parent_item_id": "ITEM_ID_WORKING_CAPITAL_LOAN",
              "descriptor": {
                "code": "LOAN",
                "name": "Loan"
              },
              "category_ids": [
                "101123"
              ],
              "tags": [
                {
                  "descriptor": {
                    "code": "INFO",
                    "name": "Information"
                  },
                  "list": [
                    {
                      "descriptor": {
                        "code": "PRINCIPAL_AMOUNT",
                        "name": "Loan Amount"
                      },
                      "value": "90000 INR"
                    },
                    {
                      "descriptor": {
                        "code": "INTEREST_AMOUNT",
                        "name": "Total Interest Charge",
                        "short_desc": "During entire tenure of loan"
                      },
                      "value": "20000 INR"
                    },
                    {
                      "descriptor": {
                        "code": "INTEREST_RATE",
                        "name": "Interest Rate"
                      },
                      "value": "13.5 %"
                    },
                    {
                      "descriptor": {
                        "code": "PROCESSING_FEE",
                        "name": "Processing Fee"
                      },
                      "value": "1200 INR"
                    },
                    {
                      "descriptor": {
                        "code": "INSURANCE_CHARGES",
                        "name": "Insurance Charges"
                      },
                      "value": "231 INR"
                    },
                    {
                      "descriptor": {
                        "code": "OTHER_UPFRONT_CHARGES",
                        "name": "Other up front charges",
                        "short_desc": "Other up front charges"
                      },
                      "value": "530 INR"
                    },
                    {
                      "descriptor": {
                        "code": "TERM",
                        "name": "Loan Term"
                      },
                      "value": "PT24M"
                    },
                    {
                      "descriptor": {
                        "code": "REPAYMENT_FREQUENCY",
                        "name": "Repayment Frequency",
                        "short_desc": "Repayment Frequency by borrower"
                      },
                      "value": "PT1M"
                    },
                    {
                      "descriptor": {
                        "code": "NUMBER_OF_INSTALLMENTS",
                        "name": "Number of installments of repayment",
                        "short_desc": "Number of installments borrower has to make to payback the loan"
                      },
                      "value": "45"
                    },
                    {
                      "descriptor": {
                        "code": "RATE_ANNUALISED_PENAL_CHARGES",
                        "name": "Rate Annualised penal charges"
                      },
                      "value": "2 %"
                    },
                    {
                      "descriptor": {
                        "code": "OTHER_CHARGES",
                        "name": "Other Charges"
                      },
                      "value": "231 INR"
                    },
                    {
                      "descriptor": {
                        "code": "COOL_OFF_PERIOD",
                        "name": "Cooling off",
                        "short_desc": "Look up period during which borrower shouldn't be charged any penalty on repayment loan."
                      },
                      "value": "PT12D"
                    }
                  ],
                  "display": true
                }
              ],
              "matched": true,
              "recommended": true
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
