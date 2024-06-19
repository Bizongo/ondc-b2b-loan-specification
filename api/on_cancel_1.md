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
        "action": "on_cancel",
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
            "code": "CANCELLATION_DETAILS",
            "name": "Cancellation Details",
            "tags": [
                {
                    "descriptor": {
                        "code": "PENDING_AMOUNT",
                        "name": "Pending Amount"
                    },
                    "value": "15000"
                },
                {
                    "descriptor": {
                        "code": "EXTRA_FEES",
                        "name": "Extra Fees"
                    },
                    "value": "500"
                },
                {
                    "descriptor": {
                        "code": "FEE_BREAKDOWN",
                        "name": "Fee Breakdown",
                        "tags": [
                            {
                                "descriptor": {
                                    "code": "PROCESSING_FEE",
                                    "name": "Processing Fee"
                                },
                                "value": "200"
                            },
                            {
                                "descriptor": {
                                    "code": "CANCELLATION_CHARGE",
                                    "name": "Cancellation Charge"
                                },
                                "value": "300"
                            }
                        ]
                    }
                },
                {
                    "descriptor": {
                        "code": "TOTAL_AMOUNT_DUE",
                        "name": "Total Amount Due"
                    },
                    "value": "15500"
                }
            ]
        },
        "xinput": {
            "head": {
                "descriptor": {
                    "name": "Payment Confirmation"
                },
                "index": {
                    "min": 0,
                    "cur": 0,
                    "max": 0
                },
                "headings": [
                    "Payment Confirmation"
                ]
            },
            "form": {
                "id": "payment_confirmation_form",
                "mime_type": "text/html",
                "url": "https://bpp.credit.becknprotocol.org/loans-kyc/xinput/form/payment_confirmation_form"
            },
            "required": true
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



