## ON_SELECT

**Purpose:** Provides KYC details, operational limits, and document requirements for the selected loan offer.

**Endpoint:** /on_select

**Method:** POST

**Description:** The ONDC network (or the selected FI) uses this endpoint to send detailed information about the selected loan offer, including KYC requirements, working capital limits, and document submission details.

**Steps:**
  - **Prepare Offer Details:** The FI prepares details about the KYC process, operational limits, and document requirements.
  - **Send Details:** The network sends the ON_SELECT response to the buyer app, including the detailed information about the selected offer.
  - **Present Details:** The buyer app displays the details to the borrower.



### Request Body

``` json
{
    "context": {
        "domain": "ONDC:FIS",
        "version": "2.0.0",
        "action": "on_select",
        "bap_id": "bizongo-next.becknprotocol.io",
        "bap_uri": "https://bizongo-next.becknprotocol.io/",
        "bpp_id": "bpp.credit.becknprotocol.org",
        "bpp_uri": "https://bpp.credit.becknprotocol.org",
        "transaction_id": "a9aaecca-10b7-4d19-b640-b047a7c62195",
        "message_id": "c8e3968c-cd78-4e46-aa34-0d541e46bd73",
        "timestamp": "2023-05-25T05:23:03.443Z",
        "ttl": "P30M"
    },
    "message": {
        "order": {
            "provider": {
                "id": "PROVIDER_ID",
                "descriptor": {
                    "images": [
                        {
                            "url": "https://www.icicibank.com/content/dam/icicibank/india/assets/images/header/logo.png",
                            "size_type": "sm"
                        }
                    ],
                    "name": "ICICI Bank",
                    "short_desc": "ICICI Bank Ltd",
                    "long_desc": "ICICI Bank Ltd, India."
                }
            },
            "items": [
                {
                    "id": "ITEM_ID_PERSONAL_LOAN",
                    "descriptor": {
                        "code": "WORKING_CAPITAIL_LOAN",
                        "name": "Working Capital Loan"
                    },
                    "xinput": {
                        "head": {
                            "descriptor": {
                                "name": "Additional Documents"
                            },
                            "index": {
                                "min": 0,
                                "cur": 0,
                                "max": 1
                            },
                            "headings": [
                                "Additional Documents",
                                "Acceptance"
                            ]
                        },
                        "form": {
                            "id": "ADDITIONAL_DOCUMENTS_FORM",
                            "mime_type": "text/html",
                            "url": "https://bpp.credit.becknprotocol.org/loans-kyc/xinput/form/ADDITIONAL_DOCUMENTS_FORM"
                        },
                        "required": false
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

[← Back to Previous File](select_1.md) | [Go to Form →](form_additional_documents.md) | [Next File →](select_2.md)

</p>

