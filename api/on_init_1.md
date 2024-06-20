## ON_INIT

**Purpose:** Provides final sanction details, loan terms, and any additional requirements for loan disbursement.

**Endpoint:** /on_init

**Method:** POST

**Description:** The FI uses this endpoint to send the final loan sanction details and terms to the buyer app.

**Steps:**
  - **Loan Sanction:** The FI processes the INIT request, performs final checks, and sanctions the loan.
  - **Final Details and Terms:** The FI sends the ON_INIT response with the final sanction details (amount, interest rate, tenure, fees), detailed loan terms, and any additional requirements (e.g., owner KYC, eNACH setup, bank account verification).
  - **Present Details:** The buyer app displays the final sanction details and loan terms to the borrower.




### Request Body

``` json
{
    "context": {
        "domain": "ONDC:FIS12",
        "version": "2.1.0",
        "action": "on_init",
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
                        "head": {
                            "descriptor": {
                                "name": "KYC Links for Director 1"
                            },
                            "index": {
                                "min": 0,
                                "cur": 0,
                                "max": 4
                            },
                            "headings": [
                                "KYC Links for Director 1",
                                "KYC Links for Director 2",
                                "Addtional KYC",
                                "eNACH Setup",
                                "Borrower Bank Details"
                            ]
                        },
                        "form": {
                            "id": "KYC_LINK",
                            "mime_type": "application/html",
                            "url": "https://bpp.credit.becknprotocol.org/loans-kyc/xinput/form/kyc-link/director1"
                        },
                        "required": true
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

[← Back to Previous File](init_1.md) | [Go to Form →](link_kyc_1.md) | [Next File →](on_status_1.md)

</p>

