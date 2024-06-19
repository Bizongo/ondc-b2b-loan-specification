## ON_UPDATE

**Purpose:** Provides the status of invoice acceptance/rejection, repayment schedule, and repayment account details.

**Endpoint:** /on_update

**Method:** POST

**Description:** The FI uses this endpoint to send updates about the financing request to the buyer app.

**Steps:**
  - **Invoice Evaluation:** The FI evaluates the invoices submitted for financing.
  - **Repayment Schedule Calculation:** The FI calculates the repayment schedule, including due dates, amounts, and interest.
  - **Send Update:** The FI sends the ON_UPDATE response to the buyer app, including the status of each invoice (accepted or rejected with a reason), the calculated repayment schedule, repayment account details, and disbursement details (payment mode and UTR number if applicable).
  - **Display Update:** The buyer app displays the update to the borrower.


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
                                    "code": "TOTAL_LINE_AMOUNT",
                                    "name": "Working Capital Line Amount"
                                },
                                "value": "1000000"
                            },
                            {
                                "descriptor": {
                                    "code": "AVAILABLE_LINE_AMOUNT",
                                    "name": "Working Capital Line Amount"
                                },
                                "value": "950000"
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
                            },
                            {
                                "descriptor": {
                                    "code": "DISBURSEMENT_HISTORY",
                                    "name": "Disbursement History"
                                },
                                "value": [
                                    {
                                        "invoice_id": "invoice_submission_id_1",
                                        "invoice_state": "DISBURSED",
                                        "disbursement_amount": "50000",
                                        "disbursement_date": "2023-06-20",
                                        "utr": "UTR-123456789",
                                        "description": "Invalid Accepted"
                                    },
                                    {
                                        "invoice_id": "invoice_submission_id_2",
                                        "invoice_state": "REPAID",
                                        "disbursement_amount": "75000",
                                        "disbursement_date": "2023-07-05",
                                        "disbursement_utr": "UTR-456789012",
                                        "repayment_amount": "75000",
                                        "repayment_date": "2023-08-10",
                                        "repayment_utr": "UTR-789012345",
                                        "description": "Invalid Accepted"
                                    },
                                    {
                                        "invoice_id": "invoice_submission_id_3",
                                        "invoice_state": "REJECTED",
                                        "disbursement_amount": "20000",
                                        "description": "Invalid invoice"
                                    }
                                ]
                            }
                        ]
                    },
                    "xinput": {
                        "head": {
                            "descriptor": {
                                "name": "Invoice Upload"
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

[← Back to Previous File](update.md) | [Next File →](status.md)

</p>

