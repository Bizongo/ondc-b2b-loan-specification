## SEARCH


**Purpose:** Initiates a search for working capital loan offers.

**Endpoint:** /search

**Method:** POST

**Description:** The buyer app sends this request directly to the BPP of the selected FI after the borrower submits the loan application form.

**Steps:**
  - **Form Submission:** The borrower fills in the form provided in the ON_SEARCH response and submits it to the buyer app.
  - **Process Form Data:** The buyer app processes the form data, extracts the relevant information, and prepares the refined SEARCH request.
  - **Peer-to-Peer Request:** The buyer app sends the refined SEARCH request directly to the BPP of the FI selected by the borrower.
  - **FI Response (Refined Offers):** The FI's BPP evaluates the borrower's information and returns personalized loan offers in the ON_SEARCH response.


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
        "transaction_id": "a9aaecca-10b7-4d19-b640-b047a7c62196",
        "message_id": "bb579fb8-cb82-4824-be12-fcbc405b6608",
        "action": "select",
        "timestamp": "2023-05-25T05:23:03.443Z",
        "version": "2.0.0",
        "bap_uri": "https://bap.credit.becknprotocol.io/",
        "bap_id": "bap.credit.becknprotocol.io",
        "ttl": "PT10M",
        "bpp_id": "bpp.credit.becknprotocol.org",
        "bpp_uri": "https://bpp.credit.becknprotocol.org"
    },
    "message": {
        "order": {
            "provider": {
                "id": "PROVIDER_ID"
            },
            "items": [
                {
                    "id": "ITEM_ID_WORKING_CAPITAL_LOAN",
                    "xinput": {
                        "form": {
                            "id": "F03"
                        },
                        "form_response": {
                            "status": "SUCCESS",
                            "submission_id": "F03_SUBMISSION_ID"
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

[← Back to Previous File](on_search_1.md) | [Next File →](on_search_2.md)

</p>
