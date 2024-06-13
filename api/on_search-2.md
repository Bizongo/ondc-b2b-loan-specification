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
    "version": "2.1.0",
    "action": "on_search",
    "bap_id": "buyer-app-abc.becknprotocol.io",
    "bap_uri": "https://buyer-app-abc.becknprotocol.io/",
    "transaction_id": "uuid-90215d70-c146-48a9-8c11-680123456789",
    "message_id": "uuid-456def7890abc-1234-5678-90ab-cdef12345678",
    "timestamp": "2024-05-21T10:15:00Z",
    "bpp_id": "PROVIDER_ID_ICICI",
    "bpp_uri": "https://icicibank.becknprotocol.org"
  },
  "message": {
    "catalog": {
      "bpp/descriptor": {
        "name": "Refined Working Capital Loan Offers",
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

[← Back to Previous File](search-2.md) | [Next File →](select.md)

</p>

