## ON_CONFIRM

**Purpose:** Provides the working capital line ID and details.

**Endpoint:** /on_confirm

**Method:** POST

**Description:** The FI uses this endpoint to formally confirm the loan and provide the working capital line ID and its details.

**Steps:**
  - **Loan Finalization:** The FI processes the CONFIRM request and finalizes the loan details.
  - **Send Confirmation:** The FI sends the ON_CONFIRM response to the buyer app, including the LINE_ID and LINE_DETAILS (like credit limit, available limit, start/end dates).
  - **Display Confirmation:** The buyer app displays the confirmation to the borrower.


### Request Body

``` json
{
    "context": {
        "domain": "ONDC:FIS12",
        "version": "2.1.0",
        "action": "on_confirm",
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
                    "fulfillment": {
                        "type": "WORKING_CAPITAL_LINE",
                        "tags": [
                            {
                                "descriptor": {
                                    "code": "LINE_AMOUNT",
                                    "name": "Working Capital Line Amount"
                                },
                                "value": "1000000"
                            },
                            {
                                "descriptor": {
                                    "code": "INTEREST_RATE",
                                    "name": "Interest Rate"
                                },
                                "value": "9.5%"
                            },
                            {
                                "descriptor": {
                                    "code": "TENURE",
                                    "name": "Tenure"
                                },
                                "value": "12 Months"
                            },
                            {
                                "descriptor": {
                                    "code": "DRAWDOWN_PERIOD",
                                    "name": "Drawdown Period"
                                },
                                "value": "6 Months"
                            },
                            {
                                "descriptor": {
                                    "code": "REPAYMENT_FREQUENCY",
                                    "name": "Repayment Frequency"
                                },
                                "value": "Monthly"
                            }
                        ]
                    },
                    "xinput": {
                        "head": {
                            "descriptor": {
                                "name": "Invoice Upload"
                            },
                            "index": {
                                "min": 0,
                                "cur": 0,
                                "max": 0
                            },
                            "headings": [
                                "Invoice Upload"
                            ]
                        },
                        "form": {
                            "id": "invoice_upload_form",
                            "mime_type": "text/html",
                            "url": "https://bpp.credit.becknprotocol.org/loans-kyc/xinput/form/invoice_upload_form"
                        },
                        "required": true
                    }
                }
            ],
            "ack": {
                "status": "ACK"
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

[← Back to Previous File](confirm.md) | [Go to Form →](form_invoice_upload.md) | [Next File →](update.md)

</p>

