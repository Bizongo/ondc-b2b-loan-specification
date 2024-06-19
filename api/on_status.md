## ON_STATUS


### Scenario 1: Pending Disbursement

**Purpose:** Informs the buyer app that the disbursement is still pending for the requested invoices.

**Endpoint:** /on_status

**Method:** POST


### Request Body

``` json
{
    "context": {
        "domain": "ONDC:FIS12",
        "version": "2.1.0",
        "action": "on_confirm",
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
        "order": {
            "id": "order-id-123",
            "state": "CONFIRMED",
            "items": [
                {
                    "id": "offer-pqr-789",
                    "fulfillment": {
                        "type": "WORKING_CAPITAL_LINE",
                        "tags": [
                            {
                                "descriptor": {
                                    "code": "TOTAL_LINE_AMOUNT",
                                    "name": "Working Capital Line Amount"
                                },
                                "value": "1000000"
                            },
                            {
                                "descriptor": {
                                    "code": "AVAILABLE_LINE_AMOUNT",
                                    "name": "Working Capital Line Amount"
                                },
                                "value": "950000"
                            },
                            {
                                "descriptor": {
                                    "code": "INTEREST_RATE",
                                    "name": "Interest Rate"
                                },
                                "value": "9.5%"
                            },
                            {
                                "descriptor": {
                                    "code": "TENURE",
                                    "name": "Tenure"
                                },
                                "value": "12 Months"
                            },
                            {
                                "descriptor": {
                                    "code": "DRAWDOWN_PERIOD",
                                    "name": "Drawdown Period"
                                },
                                "value": "6 Months"
                            },
                            {
                                "descriptor": {
                                    "code": "REPAYMENT_FREQUENCY",
                                    "name": "Repayment Frequency"
                                },
                                "value": "Monthly"
                            },
                            {
                                "descriptor": {
                                    "code": "DISBURSEMENT_HISTORY",
                                    "name": "Disbursement History"
                                },
                                "value": [
                                    {
                                        "invoice_id": "invoice_submission_id_1",
                                        "invoice_state": "DISBURSED",
                                        "disbursement_amount": "50000",
                                        "disbursement_date": "2023-06-20",
                                        "utr": "UTR-123456789",
                                        "description": "Invalid Accepted"
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
                                        "description": "Invalid Accepted"
                                    },
                                    {
                                        "invoice_id": "invoice_submission_id_3",
                                        "invoice_state": "REJECTED",
                                        "disbursement_amount": "20000",
                                        "description": "Invalid invoice"
                                    }
                                ]
                            }
                        ]
                    }
                }
            ],
            "ack": {
                "status": "ACK"
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


### Scenario 2: Completed Disbursement

**Purpose:** Informs the buyer app that the requested invoices have been disbursed.

**Endpoint:** /on_status

**Method:** POST


### Request Body

``` json
{
  "context": {
    "domain": "ONDC:FIS12",
    "version": "2.1.0",
    "action": "on_status",
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
                  "code": "STATUS_TYPE" 
                },
                "value": "DISBURSEMENT"
              },
              {
                "descriptor": {
                  "code": "INVOICE_FINANCING", 
                  "name": "Invoice Financing Details" 
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "INVOICE"
                    },
                    "list": [
                      {
                        "invoice_number": "INV-2024-06-001",
                        "tags": [
                          {
                            "descriptor": {
                              "code": "DISBURSEMENT"
                            },
                            "tags": [
                              {
                                "descriptor": {
                                  "code": "STATUS" 
                                },
                                "value": "COMPLETED"
                              },
                              {
                                "descriptor": {
                                  "code": "UTR_NUMBER" 
                                },
                                "value": "UTR9876543210"
                              }
                            ]
                          },
                          {
                            "descriptor": {
                              "code": "REPAYMENT" 
                            },
                            "tags": [
                              {
                                "descriptor": {
                                  "code": "STATUS" 
                                },
                                "value": "NOT_REPAID"
                              }
                            ]
                          }
                        ]
                      },
                      {
                        "invoice_number": "INV-2024-06-002",
                        "tags": [
                          {
                            "descriptor": {
                              "code": "DISBURSEMENT"
                            },
                            "tags": [
                              {
                                "descriptor": {
                                  "code": "STATUS" 
                                },
                                "value": "COMPLETED"
                              },
                              {
                                "descriptor": {
                                  "code": "UTR_NUMBER" 
                                },
                                "value": "UTR0123456789"
                              }
                            ]
                          },
                          {
                            "descriptor": {
                              "code": "REPAYMENT" 
                            },
                            "tags": [
                              {
                                "descriptor": {
                                  "code": "STATUS" 
                                },
                                "value": "NOT_REPAID"
                              }
                            ]
                          }
                        ]
                      },
                      {
                        "invoice_number": "INV-2024-06-003", 
                        "tags": [
                          {
                            "descriptor": {
                              "code": "DISBURSEMENT"
                            },
                            "tags": [
                              {
                                "descriptor": {
                                  "code": "STATUS" 
                                },
                                "value": "COMPLETED" 
                              },
                              {
                                "descriptor": {
                                  "code": "UTR_NUMBER" 
                                },
                                "value": "UTR9988776655"
                              }
                            ]
                          },
                          {
                            "descriptor": {
                              "code": "REPAYMENT"
                            },
                            "tags": [
                              {
                                "descriptor": {
                                  "code": "STATUS" 
                                },
                                "value": "NOT_REPAID"
                              }
                            ]
                          }
                        ] 
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

[← Back to Previous File](status.md)

</p>

