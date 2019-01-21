# Complaint

The complaint extension is used to provide structured data on complaints to 
tender conditions and their resolutions.

## Overview
Complaint can be represented using an array of complaint blocks in the 
complaints field of the tender or award section of an OCDS release.

The current status of the complaint can be represented using the 
complaints/status field using values from the complaint status codelist.

The date of the tenderer action should be provided as string using the 
complaints/tendererActionDate field.

The indicator whether the complaint was satisfied should be represented as 
boolean value of complaints/satisfied field.

The action of tenderer should be provided as string using the the 
complaints/tendererAction field.

The date when claim was submitted can be represented using the 
complaints/dateSubmitted field.

The place of reviewing the complaint should be provided using the 
complains/reviewPlace field.

All documents and attachments related to the complaint can be represented using 
the complaints/documents field. The value of it can be array of unique documents.

The title of the complaint should be provided using the complaints/title field.

The decision of a reviewer on the complaint can be represented using the 
complaints/decision field.

The indicator whether the complaint was accepted should be represented as 
boolean value of complaints/acceptance field.

The date of claim to complaint escalation can be provided as string using the
complaints/dateEscalated field.

The description of reject reason should be represented using the 
complaints/rejectReasonDescription field.

The reason for cancelling the complaint can be provided using the 
complaints/cancellationReason field. 

The date when Procuring entity answered the claim should be represented using 
the  complaints/dateAnswered field. 

The type of the complaint can be represented using the 
complaints/type field using values from the complaint type codelist.

An identifier of the related lot should be provided using the 
complaints/relatedLot field.

The description of the issue can be represented using the complaints/description.

The date of cancelling the complaint should be provided using the 
complaints/dateCancelled field.

The date of posting the complaint can be represented using the 
complaints/date field.

The date when a decision on the complaint was made should be represented using 
the complaints/dateDecision field.

The organization filing a complaint can be provided using the complaints/author 
field. It is required.

The reasons of rejecting the complaint should be represented using the 
complaints/rejectReason field using values from the complaint reject reason 
codelist.

The type of resolution can be provided using the complaints/resolutionType 
field using values from the complaint resolution type codelist.

The resolution of Procuring entity should be represented using the 
complaints/resolution field.

The date of reviewing the complaint can be provided using the 
complaint/reviewDate field.

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