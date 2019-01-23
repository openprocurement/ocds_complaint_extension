# Complaint

The **complaint extension** of the Open Contracting Data Standard is used to provide structured data for claims and complaints regarding tender conditions or violations.

Note that **complaint** is an official appeal to the Complaint Review body with a demand to eliminate violations that, presumably (according to the Complainant), had been made by Procuring entity. A **claim** is a formal appeal to a Procuring entity to eliminate violations that, presumably (according to the Complainant), had been made by the Procuring entity.

Complaint is represented by the **`tender/complaints`** and/or **`award/complaints`** blocks of an OCDS release where each `complaint` object contains twenty six fields.

## Additional fields

The fields introduced by this extension are:

* **`complaints/id`** - The id of the complaint.

* **`complaints/title`** - The title of the complaint.

* **`complaints/status`** - The current status of the complaint. This field's codelist values are: `draft`, `claim`, `answered`, `pending`, `invalid`, `declined`, `resolved`, `cancelled`, `accepted`, `stopped`.

* **`complaints/date`** - The date when the complaint was posted.

* **`complaints/dateSubmitted`** - The date when claim/complaint was submitted.

* **`complaints/documents`** - All documents and attachments related to the complaint. The field's value can be an array of unique documents.

* **`complaints/type`** - The type of the complaint. Possible values are: `claim`, `complaint`.

* **`complaints/relatedLot`** - An identifier of the related lot.

* **`complaints/description`** - The description of the issue or violation. 

* **`complaints/author`** - The organization filing a complaint.  

* **`complaints/tendererActionDate`** - The date of the tenderer action. Should be provided as a string.

* **`complaints/tendererAction`** - The action of the tenderer. Should be provided as a string.

* **`complaints/satisfied`** - The indicator whether the claim/complaint was satisfied. Should be represented as 
a boolean value.

* **`complains/reviewPlace`** - The place of the Complaint review (is arbitrary filled in by the user).

* **`complaint/reviewDate`** - The date when the complaint was reviewed.

* **`complaints/acceptance`** - The indicator whether the complaint was accepted. Should be represented as a
boolean value.

* **`complaints/dateEscalated`** - The date of escalation from claim to complaint .

* **`complaints/cancellationReason`** - The reason for cancelling the complaint. At any time before the publication of the Complaint Review body’s decision, the Complainant can withdraw his complaint.

* **`complaints/dateCancelled`** - The date when the complaint was cancelled.
 
* **`complaints/dateAnswered`** - The date when Procuring entity answered the claim. 

* **`complaints/decision`** - The decision of a reviewer on the complaint.

* **`complaints/dateDecision`** - The date when a decision on the complaint was made.

* **`complaints/rejectReason`** - The reasons of rejecting the complaint, i.e. the complaint does not meet the requirements of the Law, fee was not received, the procuring entity eliminated violations.

* **`complaints/rejectReasonDescription`** - The description of the reject reason (in arbitrary form).

* **`complaints/resolutionType`** - The type of resolution made by the Procuring entity. Possible values are: `invalid`, `declined`, `resolved`.

* **`complaints/resolution`** - The resolution made by the Procuring entity.

* **`tender/complaintPeriod`** and **`awards/complaintPeriod`** - The timeframe when complaints can be submitted.

## Examples
The example below shows a complaint in tender.
```
{
  "tender": {
    "id": "ocds-213czf-000-00001",
    "complaintPeriod": {
      "startDate": "2016-04-19T12:09:04.284659+03:00",
      "endDate": "2016-04-19T12:29:00+03:00"
    },
    "complaints": [
      {
        "status": "pending",
        "description": "Test description",
        "title": "Title",
        "author": {
          "contactPoint": {
            "telephone": "+7878000001",
            "name": "John Smith",
            "email": "testjohn@i.ua"
          },
          "identifier": {
            "scheme": "UA-EDR",
            "id": "000000293",
            "legalName": "thingthing"
          },
          "name": "thing"
        },
        "dateSubmitted": "2016-04-20T13:01:42.839422+03:00",
        "complaintID": "UA-2016-04-19-000014-1.11",
        "date": "2016-04-20T13:01:40.168291+03:00",
        "type": "complaint",
        "id": "7679d1b2cd7a4d30b13ba4acff31010d"
      }
    ]
  }
}
```
The example below shows a complaint in award.
```
{
  "awards": [
    {
      "id": "GEO150000648-award",
      "complaintPeriod": {
        "startDate": "2016-04-19T14:23:39.996362+03:00",
        "endDate": "2016-04-20T13:03:46.918912+03:00"
      },
      "complaints": [
        {
          "status": "pending",
          "description": "Test description",
          "title": "Title",
          "author": {
            "contactPoint": {
              "telephone": "+7878000001",
              "name": "Tom Smith",
              "email": "testtest@i.ua"
            },
            "identifier": {
              "scheme": "UA-EDR",
              "id": "000000292",
              "legalName": "thing"
            },
            "name": "thing"
          },
          "dateSubmitted": "2016-04-20T13:01:42.839422+03:00",
          "complaintID": "UA-2016-04-19-000014-1.11",
          "date": "2016-04-20T13:01:40.168291+03:00",
          "type": "complaint",
          "id": "7679d1b2cd7a4d30b13ba4acff31010d"
        }
      ]
    }
  ]
}
```
