## SEARCH


**Purpose:** The buyer app (Bizongo Next) uses this endpoint to send a loan request to the ONDC network.

**Endpoint:** /search

**Method:** POST

**Description:** The buyer app (Bizongo Next) uses this endpoint to send a loan request to the ONDC network.

**Steps:**
  - **Request Loan Offers:** The buyer app sends a SEARCH request to the ONDC network, specifying the borrower's intent (loan type).
  - **Network Broadcast:** The ONDC network broadcasts the SEARCH request to all registered FIs.
  - **Response (ACK):** The network sends an acknowledgment (ACK) response to the buyer app, indicating that the request has been received


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
        "action": "search",
        "timestamp": "2023-05-25T05:23:03.443Z",
        "version": "2.0.0",
        "bap_uri": "https://bap.credit.becknprotocol.io/",
        "bap_id": "bap.credit.becknprotocol.io",
        "ttl": "PT10M"
    },
    "message": {
        "intent": {
            "category": {
                "descriptor": {
                    "code": "WORKING_CAPITAL_LOAN"
                }
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


---

<p align="center">

[Next File →](on_search_1.md)

</p>
