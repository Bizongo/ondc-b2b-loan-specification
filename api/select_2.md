## SELECT

**Purpose:** Allows the buyer app to select a specific loan offer from an FI.

**Endpoint:** /select

**Method:** POST

**Description:** The buyer app uses this endpoint to inform the ONDC network and the selected FI that the borrower has chosen a particular loan offer.

**Steps:**
  - **Offer Selection:** The borrower, through the buyer app, selects a loan offer from the list of available offers.
  - **Send Selection:** The buyer app sends a SELECT request to the network, specifying the FI ID and catalog ID of the selected offer.
  - **Confirmation (ACK):** The network sends an ACK response to the buyer app.
  - **Network Broadcast:** The ONDC network broadcasts the SEARCH request to registered FIs.


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
                            "id": "F02"
                        },
                        "form_response": {
                            "status": "SUCCESS",
                            "submission_id": "F02_SUBMISSION_ID"
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

[← Back to Previous File](on_search.md) | [Next File →](on_select.md)

</p>

