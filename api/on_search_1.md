## ON_SEARCH


**Purpose:** Provides the initial response to the SEARCH request, including generic loan offers and a form for the borrower to provide more details.

**Endpoint:** /on_search

**Method:** POST

**Description:** The gateway responds to the SEARCH request with this endpoint.


**Steps:**
  - **Generic Loan Offers:** The gateway provides a general catalog of loan offers from interested FIs.
  - **Input Form:** The gateway includes an xinput form for the borrower to submit their specific details.


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
            }
          ],
          "xinput": {
            "head": {
              "descriptor": {
                "name": "Borrower and Loan Details"
              }
            },
            "form": {
              "id": "F01",
              "mime_type": "text/html",
              "url": "https://buyer-app-abc.becknprotocol.io/loan-form"
            }
          }
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

[← Back to Previous File](search_1.md) | [Go to Form →](form_1.md) | [Next File →](search_2.md)

</p>

