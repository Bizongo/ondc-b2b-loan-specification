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
    "version": "2.1.0",
    "action": "select",
    "bap_id": "buyer-app-abc.becknprotocol.io",
    "bap_uri": "https://buyer-app-abc.becknprotocol.io/",
    "transaction_id": "uuid-90215d70-c146-48a9-8c11-680123456789",
    "message_id": "uuid-789abcdef0-1234-5678-90ab-cdef12345678",
    "timestamp": "2024-05-21T10:10:00Z",
    "bpp_id": "bpp.credit.becknprotocol.org",
    "bpp_uri": "https://bpp.credit.becknprotocol.org"
  },
  "message": {
    "order": {
      "items": [
        "ITEM_ID_INVOICE_LOAN_ICICI"
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

