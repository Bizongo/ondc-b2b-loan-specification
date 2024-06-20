## CONFIRM

**Purpose:** Confirms the borrower's acceptance of the final sanction details and loan terms and provides confirmation of fulfillment for sanction requirements.

**Endpoint:** /confirm

**Method:** POST

**Description:** The buyer app uses this endpoint to send the borrower's final confirmation to the FI, including their acceptance of the sanction details, loan terms, and the fulfillment status of additional requirements.

**Steps:**
  - **Review and Acceptance:** The borrower reviews the final sanction details, loan terms, and any additional requirements.
  - **Fulfill Requirements:** The borrower completes any outstanding requirements (e.g., owner KYC, eNACH setup).
  - **Confirmation:** The buyer app sends the CONFIRM request, indicating the borrower's acceptance of the loan terms and the completion status of the additional requirements.
  - **Response (ACK):** The FI sends an ACK response.



### Request Body

``` json
{
    "confirm": {
        "context": {
            "domain": "ONDC:FIS12",
            "version": "2.1.0",
            "action": "confirm",
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
                "state": "PENDING",
                "items": [
                    {
                        "id": "offer-pqr-789",
                        "xinput": {
                            "form": {
                                "id": "accept_loan_terms_form",
                                "form_response": {
                                    "status": "SUCCESS",
                                    "submission_id": "79850933-4e41-4c76-bbe6-c5a392481226"
                                }
                            }
                        }
                    }
                ]
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

[← Back to Previous File](on_status_4.md) | [Next File →](on_confirm.md)

</p>

