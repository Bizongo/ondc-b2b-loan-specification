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
    "domain": "ONDC:FIS12",
    "version": "2.1.0",
    "action": "on_select",
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
        "fi_name": "ICICI Bank",
        "fi_catalog": {
          "id": "PROVIDER_ID",
          "offer_details": {
            "descriptor": {
              "name": "Invoice based Loan"
            },
            "tags": [
              {
                "descriptor": {
                  "code": "KYC_PROCESS",
                  "name": "KYC Process Details"
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "MODE"
                    },
                    "value": "OFFLINE"
                  },
                  {
                    "descriptor": {
                      "code": "KYC_LINK"
                    },
                    "value": "https://www.icicibank.com/kyc-portal"
                  },
                  {
                    "descriptor": {
                      "code": "PROPOSED_SCHEDULED_DATE"
                    },
                    "value": "2024-05-28"
                  }
                ]
              },
              {
                "descriptor": {
                  "code": "DOCUMENT_SUBMISSION",
                  "name": "Document Submission Details"
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "FORM_ID"
                    },
                    "value": "F001-ICICI"
                  },
                  {
                    "descriptor": {
                      "code": "FORM_LINK"
                    },
                    "value": "https://www.icicibank.com/document-upload-form"
                  },
                  {
                    "descriptor": {
                      "code": "DOCUMENTS_REQUIRED",
                      "name": "Required Documents"
                    },
                    "list": [
                      {
                        "descriptor": {
                          "code": "FINANCIAL_DOCUMENTS",
                          "name": "Financial Documents"
                        },
                        "list": [
                          {
                            "document_name": "Debt Facility Letters",
                            "document_description": "Sanction letters of existing Debt Facilities"
                          },
                          {
                            "document_name": "Yearly Transaction Ledger",
                            "document_description": "Last 12 month sales and purchase ledger"
                          },
                          {
                            "document_name": "Asset Aging Breakdown",
                            "document_description": "Current Stock, Debtors and Creditors with ageing"
                          }
                        ]
                      },
                      {
                        "descriptor": {
                          "code": "BUSINESS_DOCUMENTS",
                          "name": "Business Documents"
                        },
                        "list": [
                          {
                            "document_name": "HUF Deed"
                          },
                          {
                            "document_name": "Form G - HUF Registration"
                          },
                          {
                            "document_name": "Udyam Registration"
                          }
                        ]
                      },
                      {
                        "descriptor": {
                          "code": "OTHER_DOCUMENTS",
                          "name": "Other Documents"
                        },
                        "list": [
                          {
                            "document_name": "6-Month Seller Forecast",
                            "document_description": "Business Projections for next 6 months with seller (Anchor)"
                          }
                        ]
                      }
                    ]
                  }
                ]
              },
              {
                "descriptor": {
                  "code": "WORKING_CAPITAL_LIMITS",
                  "name": "Working Capital Limits"
                },
                "tags": [
                  {
                    "descriptor": {
                      "code": "COUNTERPARTY_GSTINS",
                      "name": "Allowed Counterparty GSTINs"
                    },
                    "list": [
                      "98ZYXWV9876543210U",
                      "76FEDCBA5432109876"
                    ]
                  },
                  {
                    "descriptor": {
                      "code": "COUNTERPARTY_ACCEPTANCE",
                      "name": "Counterparty Acceptance Required"
                    },
                    "value": true
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

[← Back to Previous File](select.md) | [Next File →](init.md)

</p>

