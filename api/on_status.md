## ON_STATUS


### Scenario 1: Pending Disbursement

**Purpose:** Informs the buyer app that the disbursement is still pending for the requested invoices.

**Endpoint:** /on_status

**Method:** POST


### Request Body

``` json
{
  "context": {
    "domain": "ONDC:FIS",
    "version": "2.0.0",
    "action": "on_update",
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
                },
                {
                  "descriptor": {
                    "code": "DISBURSEMENT_HISTORY",
                    "name": "Disbursement History"
                  },
                  "list": [
                    {
                      "invoice_id": "invoice_submission_id_1",
                      "invoice_state": "PENDING",
                    },
                    {
                      "invoice_id": "invoice_submission_id_3",
                      "invoice_state": "REJECTED",
                      "disbursement_amount": "20000",
                      "description": "Invalid Rejected due to invalid gstin"
                    }
                  ]
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
          ]
        }
      ],
      "documents": [
        {
          "descriptor": {
            "code": "LOAN_AGREEMENT",
            "name": "Loan Agreement Document",
            "short_desc": "Download your Loan Agreement document here",
            "long_desc": "A Loan Agreement Document is a legal contract outlining terms such as loan amount, interest rate, repayment schedule, and collateral, binding a lender and borrower in a formal financial arrangement."
          },
          "mime_type": "application/pdf",
          "url": "https://lender.com/loan/loan-agreement/O1.pdf"
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


### Scenario 2: Completed Disbursement

**Purpose:** Informs the buyer app that the requested invoices have been disbursed.

**Endpoint:** /on_status

**Method:** POST


### Request Body

``` json
{
  "context": {
    "domain": "ONDC:FIS",
    "version": "2.0.0",
    "action": "on_update",
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
                },
                {
                  "descriptor": {
                    "code": "DISBURSEMENT_HISTORY",
                    "name": "Disbursement History"
                  },
                  "list": [
                    {
                      "invoice_id": "invoice_submission_id_1",
                      "invoice_state": "DISBURSED",
                      "disbursement_amount": "50000",
                      "disbursement_date": "2023-06-20",
                      "utr": "UTR-123456789",
                      "description": "Invoice Accepted"
                    },
                    {
                      "invoice_id": "invoice_submission_id_2",
                      "invoice_state": "REPAID",
                      "disbursement_amount": "75000",
                      "disbursement_date": "2023-07-05",
                      "disbursement_utr": "UTR-456789012",
                      "repayment_amount": "75000",
                      "repayment_date": "2023-08-10",
                      "repayment_utr": "UTR-789012345",
                      "description": "Invoice Accepted"
                    },
                    {
                      "invoice_id": "invoice_submission_id_3",
                      "invoice_state": "REJECTED",
                      "disbursement_amount": "20000",
                      "description": "Invalid Rejected due to invalid gstin"
                    }
                  ]
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
          ]
        }
      ],
      "documents": [
        {
          "descriptor": {
            "code": "LOAN_AGREEMENT",
            "name": "Loan Agreement Document",
            "short_desc": "Download your Loan Agreement document here",
            "long_desc": "A Loan Agreement Document is a legal contract outlining terms such as loan amount, interest rate, repayment schedule, and collateral, binding a lender and borrower in a formal financial arrangement."
          },
          "mime_type": "application/pdf",
          "url": "https://lender.com/loan/loan-agreement/O1.pdf"
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

[← Back to Previous File](status.md)

</p>

