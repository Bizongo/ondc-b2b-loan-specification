## UPDATE

**Purpose:** Updates the loan status and provides details for invoice financing and disbursement.

**Endpoint:** /update

**Method:** POST

**Description:** The buyer app uses this endpoint to provide details about the invoices the borrower wants to finance against their working capital line.

**Steps:**
  - **Invoice Selection:** The borrower, using the buyer app, selects the invoices for financing.
  - **Send Invoice Details:** The buyer app sends the UPDATE request, including the WORKING_CAPITAL_LINE_ID, the selected invoices with their details and buyer acceptance status, and the borrower's bank account details for disbursement.
  - **Invoice Processing:** The FI starts processing the invoices.
  - **Response (ACK):** The FI sends an ACK response to the buyer app.


### Request Body

``` json
{
    "context": {
        "domain": "ONDC:FIS12",
        "version": "2.1.0",
        "action": "update",
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
        "order": {
            "id": "order-id-123",
            "state": "CONFIRMED",
            "items": [
                {
                    "id": "offer-pqr-789",
                    "xinput": {
                        "form": {
                            "id": "invoice_upload_form",
                            "form_response": {
                                "status": "SUCCESS",
                                "submission_id": "invoice_submission_id"
                            }
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

[← Back to Previous File](on_confirm.md) | [Next File →](on_update.md)

</p>

