## UPDATE

**Purpose:** Signals the borrower's intent to proceed with the loan and provides fulfillment details for sanction requirements.

**Endpoint:** /init

**Method:** POST

**Description:** The buyer app uses this endpoint to inform the FI that the borrower intends to proceed with the loan and to provide details about the fulfillment of pre-sanction requirements, including KYC, document submission, and acceptance of operational limits.


### Request Body

``` json
{
  "context": {
    "domain": "ONDC:FIS12",
    "version": "2.1.0",
    "action": "init",
    "bap_id": "bap.credit.becknprotocol.io",
    "bap_uri": "https://bap.credit.becknprotocol.io/",
    "transaction_id": "a9aaecca-10b7-4d19-b640-b047a7d62196",
    "message_id": "bb579fb8-cb82-4824-be12-fcbc405b6608",
    "ttl": "PT30M",
    "timestamp": "2023-05-25T05:23:03.443Z",
    "bpp_id": "bpp.credit.becknprotocol.org",
    "bpp_uri": "https://bpp.credit.becknprotocol.org"
  },
  "message": {
    "update_target": "payments",
    "order": {
      "id": "CHILD_ITEM_ID_WORKING_CAPITAL_LOAN",
      "payments": [
        {
          "time": {
            "label": "FORECLOSURE"
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

[← Back to Previous File](on_confirm.md) | [Next File →](on_update_1.md)

</p>
