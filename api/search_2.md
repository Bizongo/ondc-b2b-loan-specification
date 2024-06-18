## SEARCH


**Purpose:** Initiates a search for working capital loan offers.

**Endpoint:** /search

**Method:** POST

**Description:** The buyer app sends this request directly to the BPP of the selected FI after the borrower submits the loan application form.

**Steps:**
  - **Form Submission:** The borrower fills in the form provided in the ON_SEARCH response and submits it to the buyer app.
  - **Process Form Data:** The buyer app processes the form data, extracts the relevant information, and prepares the refined SEARCH request.
  - **Peer-to-Peer Request:** The buyer app sends the refined SEARCH request directly to the BPP of the FI selected by the borrower.
  - **FI Response (Refined Offers):** The FI's BPP evaluates the borrower's information and returns personalized loan offers in the ON_SEARCH response.


### Request Body

``` json
{
  "context": {
    "domain": "ONDC:FIS12",
    "version": "2.1.0",
    "action": "search",
    "bap_id": "buyer-app-abc.becknprotocol.io",
    "bap_uri": "https://buyer-app-abc.becknprotocol.io/",
    "transaction_id": "uuid-90215d70-c146-48a9-8c11-680123456789", 
    "message_id": "uuid-456def7890abc-1234-5678-90ab-cdef12345678", 
    "timestamp": "2024-05-21T10:12:00Z",
    "bpp_id": "PROVIDER_ID_ICICI",
    "bpp_uri": "https://icicibank.becknprotocol.org"
  },
  "message": {
    "intent": {
      "item": {
        "descriptor": {
          "code": "WORKING_CAPITAL_LOAN"
        }
      },
      "tags": [
        {
          "descriptor": {
            "code": "FORM_SUBMISSION_ID" 
          },
          "value": "submission-id-xyz123"
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

[← Back to Previous File](on_search_1.md) | [Next File →](on_search_2.md)

</p>
