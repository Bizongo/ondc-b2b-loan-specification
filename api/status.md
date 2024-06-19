## STATUS

**Purpose:** Retrieves the status of invoice disbursements or repayments for a specific working capital line.

**Endpoint:** /status

**Method:** POST

**Description:** The buyer app uses this endpoint to check the status of either invoice disbursements or loan repayments for a working capital line.

**Steps:**
  - **Request Status:** The buyer app sends a STATUS request, specifying the LINE_ID and the STATUS_TYPE (DISBURSEMENT or REPAYMENT)
  - **Retrieve Status:** The FI retrieves the requested status information.
  - **Response (ACK):** The FI sends an ACK response.


### Request Body

``` json
{
  "context": {
    "domain": "ONDC:FIS12",
    "version": "2.1.0",
    "action": "status",
    "bap_id": "buyer-app-abc.becknprotocol.io",
    "bap_uri": "https://buyer-app-abc.becknprotocol.io/",
    "transaction_id": "uuid-90215d70-c146-48a9-8c11-680123456789",
    "message_id": "uuid-abcdef012-3456-7890-abcd-ef0123456789",
    "timestamp": "2024-05-21T11:00:00Z",
    "bpp_id": "bpp.credit.becknprotocol.org",
    "bpp_uri": "https://bpp.credit.becknprotocol.org"
  },
  "message": {
    "order_id": "WCL-1234567890" // Working Capital Line ID 
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

[← Back to Previous File](on_update.md) | [Next File →](on_status.md)

</p>

