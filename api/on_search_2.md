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
        "action": "on_select",
        "version": "2.0.0",
        "bap_id": "bap.credit.becknprotocol.io",
        "bap_uri": "https://bap.credit.becknprotocol.io/",
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
                            "url": "https://www.icicibank.com/content/dam/icicibank/india/assets/images/header/logo.png",
                            "size_type": "sm"
                        }
                    ],
                    "name": "ICICI Bank",
                    "short_desc": "ICICI Bank Ltd",
                    "long_desc": "ICICI Bank Ltd, India."
                }
            },
            "items": [
                {
                    "id": "ITEM_ID_PERSONAL_LOAN",
                    "descriptor": {
                        "code": "WORKING_CAPITAIL_LOAN",
                        "name": "Working Capital Loan"
                    },
                    "xinput": {
                        "head": {
                                "descriptor": {
                                    "name":  "Business & Financial Details"
                                },
                                "index": {
                                    "min": 0,
                                    "cur": 1,
                                    "max": 2
                                },
                               "headings": [
                                        "Bank Statement & GST Returns",
                                        "Business & Financial Details",
                                        "Loan Acceptance" 
                                ]
                        },
                        "form": {
                                    "id": "form_business_financial_F02",
                                    "mime_type": "text/html",
                                    "url": "https://bpp.credit.becknprotocol.org/xinput/formid/form_business_financial/F02",
                                    "resubmit": false,
                                    "multiple_sumbissions": false
                                },
                        "required": true
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

[← Back to Previous File](search_2.md) | [Go to Form →](form_business_financial.md) | [Next File →](search_3.md)

</p>

