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
                    },
                    "categories": [
                        {
                            "descriptor": {
                                "code": "WORKING_CAPITAL_LOAN",
                                "name": "Working Captail Loan"
                            },
                            "id": "101123"
                        }
                    ],
                    "items": [
                        {
                            "id": "WORKING_CAPITAL_LOAN_ID",
                            "category_ids": [
                                "101123"
                            ],
                            "descriptor": {
                                "code": "WORKING_CAPITAL_LOAN",
                                "name": "Working Captail Loan"
                            },
                            "tags": [
                                {
                                    "descriptor": {
                                        "code": "GENERAL_INFO",
                                        "name": "General Information"
                                    },
                                    "display": true,
                                    "list": [
                                        {
                                            "descriptor": {
                                                "code": "MIN_INTEREST_RATE",
                                                "name": "Minimum Interest Rate",
                                                "short_desc": "Loans starting from 9% (p.a)"
                                            },
                                            "value": "9%"
                                        },
                                        {
                                            "descriptor": {
                                                "code": "MAX_INTEREST_RATE",
                                                "name": "Maximum Interest Rate",
                                                "short_desc": "Loan Rate below from 15% (p.a)"
                                            },
                                            "value": "15%"
                                        },
                                        {
                                            "descriptor": {
                                                "code": "MIN_TENURE",
                                                "name": "Minimum Tenure",
                                                "short_desc": "Loan Tenure starting form 5 months"
                                            },
                                            "value": "5 months"
                                        },
                                        {
                                            "descriptor": {
                                                "code": "MAX_TENURE",
                                                "name": "Maximum Tenure",
                                                "short_desc": "Loan Tenure upto form 5 years"
                                            },
                                            "value": "5 years"
                                        },
                                        {
                                            "descriptor": {
                                                "code": "MIN_LOAN_AMOUNT",
                                                "name": "Minimum Loan Amount",
                                                "short_desc": "Loan Amount starting from 50,000"
                                            },
                                            "value": "50000"
                                        },
                                        {
                                            "descriptor": {
                                                "code": "MAX_LOAN_AMOUNT",
                                                "name": "Minimum Loan Amount",
                                                "short_desc": "Loan Amount upto form 50,00,000"
                                            },
                                            "value": "5000000"
                                        }
                                    ]
                                }
                            ],
                            "xinput": {
                                "form": {
                                    "id": "form_business_financial_F02",
                                    "mime_type": "text/html",
                                    "multiple_sumbissions": false,
                                    "resubmit": false,
                                    "url": "https://bpp.credit.becknprotocol.org/xinput/formid/form_business_financial/F02"
                                },
                                "head": {
                                    "descriptor": {
                                        "name": "Business & Financial Details"
                                    },
                                    "headings": [
                                        "Bank Statement & GST Returns",
                                        "Business & Financial Details",
                                        "Loan Acceptance"
                                    ],
                                    "index": {
                                        "cur": 1,
                                        "max": 2,
                                        "min": 0
                                    }
                                },
                                "required": true
                            },
                            "matched": true,
                            "recommended": true,
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

[← Back to Previous File](search_2.md) | [Go to Form →](form_business_financial.md) | [Next File →](search_3.md)

</p>

