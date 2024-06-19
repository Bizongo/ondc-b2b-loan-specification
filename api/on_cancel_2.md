## ON_CANCEL

**Purpose:** Cancel the borrower's acceptance of the final sanction details and loan terms

**Endpoint:** /on_cancel

**Method:** POST

**Description:** To be added

**Steps:**
  - To be added



### Request Body

``` json
{
    "context": {
        "domain": "ONDC:FIS12",
        "version": "2.1.0",
        "action": "on_update",
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
        "order_id": "order-id-123",
        "cancellation_reason_id": "reason_1",
        "descriptor": {
            "code": "CANCELLATION_CONFIRMATION",
            "name": "Cancellation Confirmation",
            "tags": [
                {
                    "descriptor": {
                        "code": "CONFIRMATION",
                        "name": "Cancellation Confirmed"
                    },
                    "value": true
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

[← Back to Previous File](on_init.md) | [Next File →](on_confirm.md)

</p>



