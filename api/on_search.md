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
                  "code": "INFO",
                  "name": "Information"
                },
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
                ],
                "display": true
              }
            ]
          }
        }
      },
      {
        "fi_name": "HDFC Bank",
        "fi_catalog": {
          "id": "PROVIDER_ID_2",
          "offer_details": {
            "descriptor": {
              "name": "Invoice Discounting"
            },
            "tags": [
              {
                "descriptor": {
                  "code": "INFO",
                  "name": "Information"
                },
                "list": [
                  {
                    "descriptor": {
                      "code": "MIN_INTEREST_RATE",
                      "name": "Minimum Interest Rate",
                      "short_desc": "Loans starting from 10% (p.a)"
                    },
                    "value": "10%"
                  },
                  {
                    "descriptor": {
                      "code": "MAX_INTEREST_RATE",
                      "name": "Maximum Interest Rate",
                      "short_desc": "Loan Rate below from 16% (p.a)"
                    },
                    "value": "16%"
                  },
                  {
                    "descriptor": {
                      "code": "MIN_TENURE",
                      "name": "Minimum Tenure",
                      "short_desc": "Loan Tenure starting form 3 months"
                    },
                    "value": "3 months"
                  },
                  {
                    "descriptor": {
                      "code": "MAX_TENURE",
                      "name": "Maximum Tenure",
                      "short_desc": "Loan Tenure upto form 4 years"
                    },
                    "value": "4 years"
                  },
                  {
                    "descriptor": {
                      "code": "MIN_LOAN_AMOUNT",
                      "name": "Minimum Loan Amount",
                      "short_desc": "Loan Amount starting from 25,000"
                    },
                    "value": "25000"
                  },
                  {
                    "descriptor": {
                      "code": "MAX_LOAN_AMOUNT",
                      "name": "Minimum Loan Amount",
                      "short_desc": "Loan Amount upto form 40,00,000"
                    },
                    "value": "4000000"
                  }
                ],
                "display": true
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

[← Back to Previous File](search.md) | [Next File →](select.md)

</p>

