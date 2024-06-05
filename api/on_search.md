## ON_SEARCH


**Purpose:** Delivers loan offers from lenders in response to a SEARCH request

**Endpoint:** /on_search

**Method:** POST

**Description:** The ONDC network uses this endpoint to send loan offers from interested FIs to the buyer app.


**Steps:**
  - **Preparation:** FIs that have evaluated the SEARCH request prepare their loan offers.
  - **Send Offers:** The ONDC network sends the ON_SEARCH response to the buyer app, containing a list of loan offers from different FIs.
  - **Offer Presentation:** The buyer app displays the loan offers to the borrower.


### Request Body

``` json
{
  "context": {
    "domain": "ONDC:FIS12",
    "version": "2.1.0",
    "action": "on_search",
    "bap_id": "buyer-app-abc.becknprotocol.io",
    "bap_uri": "https://buyer-app-abc.becknprotocol.io/",
    "transaction_id": "uuid-90215d70-c146-48a9-8c11-680123456789",
    "message_id": "uuid-123e4567-e89b-12d3-a456-426614174000",
    "timestamp": "2024-05-21T10:05:00Z",
    "bpp_id": "bpp.credit.becknprotocol.org",
    "bpp_uri": "https://bpp.credit.becknprotocol.org"
  },
  "message": {
    "catalog": {
      "bpp/descriptor": {
        "name": "Working Capital Loan Offers",
        "code": "WORKING_CAPITAL_LOAN_OFFERS"
      },
      "bpp/providers": [
        {
          "id": "PROVIDER_ID_ICICI",
          "descriptor": {
            "name": "ICICI Bank",
            "short_desc": "ICICI Bank Ltd",
            "long_desc": "ICICI Bank Ltd, India.",
            "images": [
              {
                "url": "https://www.icicibank.com/content/dam/icicibank/india/assets/images/header/logo.png",
                "size_type": "sm"
              }
            ]
          },
          "items": [
            {
              "id": "ITEM_ID_INVOICE_LOAN_ICICI",
              "descriptor": {
                "code": "INVOICE_BASED_LOAN",
                "name": "Invoice based Loan"
              },
              "tags": [
                {
                  "descriptor": {
                    "code": "LOAN_AMOUNT_RANGE",
                    "name": "Loan Amount Range"
                  },
                  "minimum_value": "50000",
                  "maximum_value": "5000000"
                },
                {
                  "descriptor": {
                    "code": "INTEREST_RATE_RANGE",
                    "name": "Interest Rate Range"
                  },
                  "minimum_value": "9",
                  "maximum_value": "15"
                },
                {
                  "descriptor": {
                    "code": "TENURE_RANGE_MONTHS",
                    "name": "Tenure Range (Months)"
                  },
                  "minimum_value": "5",
                  "maximum_value": "60"
                }
              ]
            },
            {
              "id": "OFFER_ID_ICICI_1",
              "descriptor": {
                "code": "INVOICE_BASED_LOAN",
                "name": "ICICI Invoice Financing - Standard"
              },
              "tags": [
                {
                  "descriptor": {
                    "code": "LOAN_AMOUNT_RANGE",
                    "name": "Loan Amount Range"
                  },
                  "minimum_value": "60000",
                  "maximum_value": "2000000"
                },
                {
                  "descriptor": {
                    "code": "INTEREST_RATE_RANGE",
                    "name": "Interest Rate Range"
                  },
                  "minimum_value": "10.5",
                  "maximum_value": "13.0"
                },
                {
                  "descriptor": {
                    "code": "TENURE_RANGE_MONTHS",
                    "name": "Tenure Range (Months)"
                  },
                  "minimum_value": "6",
                  "maximum_value": "36"
                }
              ]
            }
          ],
          "tags": [
            {
              "descriptor": {
                "code": "CONTACT_INFO",
                "name": "Contact Info"
              },
              "tags": [
                {
                  "descriptor": {
                    "code": "GRO_NAME",
                    "name": "Gro name"
                  },
                  "value": "ICICI Bank GRO"
                },
                {
                  "descriptor": {
                    "code": "GRO_EMAIL",
                    "name": "Gro email"
                  },
                  "value": "gro@icicibank.com"
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
                  "value": "https://www.icicibank.com/customer-support"
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
              "tags": [
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
                  "value": "lsp@icicibank.com"
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

[← Back to Previous File](search.md) | [Next File →](select.md)

</p>

