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
                                "value": "PENDING" 
                              }
                              // No UTR_NUMBER as disbursement is pending
                            ]
                          }
                          // No REPAYMENT tag as disbursement hasn't happened yet 
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
                                "value": "PENDING" 
                              }
                              // No UTR_NUMBER as disbursement is pending
                            ]
                          }
                          // No REPAYMENT tag as disbursement hasn't happened yet
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
                                "value": "PENDING" 
                              }
                              // No UTR_NUMBER as disbursement is pending
                            ]
                          }
                          // No REPAYMENT tag as disbursement hasn't happened yet
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

