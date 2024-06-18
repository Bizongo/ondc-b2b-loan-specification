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
    "version": "2.1.0",
    "action": "search",
    "bap_id": "buyer-app-abc.becknprotocol.io",
    "bap_uri": "https://buyer-app-abc.becknprotocol.io/",
    "transaction_id": "uuid-90215d70-c146-48a9-8c11-680123456789",
    "message_id": "uuid-123e4567-e89b-12d3-a456-426614174000",
    "timestamp": "2024-05-21T10:00:00Z",
    "ttl": "PT5M",
    "location": {
      "city": {
        "code": "*"
      },
      "country": {
        "code": "IND"
      }
    }
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
