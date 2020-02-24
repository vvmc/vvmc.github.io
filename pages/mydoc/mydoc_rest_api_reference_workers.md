---
title: "Reference: Workers"
tags:
keywords:
last_updated:
summary:
sidebar: mydoc_sidebar
permalink: mydoc_rest_api_reference_workers.html
folder: mydoc
---

### Resource Description
Workers represent employees and contingent workers in your tenant. You can only view the workers and worker data that your security profile permits.

### Endpoints
Collection of workers:
<div class="alert alert-success"><span class="label label-info">GET</span> /workers</div>
Individual worker:
<div class="alert alert-success"><span class="label label-info">GET</span> /workers/{id}</div>

### Parameters
<table>
<colgroup>
<col width="10%" />
<col width="10%" />
<col width="10%" />
<col width="70%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Type</th>
<th>Data Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>id</td>
<td>Path</td>
<td>String</td>
<td>A worker's reference ID. In place of a reference ID, you can use the word me for the current user.</td>
</tr>
<tr>
<td>limit</td>
<td>Query</td>
<td>Integer</td>
<td>Limit of object data entries included in a single response. The default is 20, and the maximum is 100.</td>
</tr>
<tr>
<td>offset</td>
<td>Query</td>
<td>Integer</td>
<td>Offset to the first object in a collection to include in the response. The default is zero.</td>
</tr>
<tr>
<td>search</td>
<td>Query</td>
<td>String</td>
<td>Search for workers by name only. Use at least 3 consecutive characters in the search text. The search is case-insensitive, and the search text only matches names that start with the search text.</td>
</tr>
<tr>
<td>view</td>
<td>Query</td>
<td>String</td>
<td>View different data in the response body. You can use one of the following:<ul><li>workerSummary </li><li>workerProfile </li><li>timeOffSummary</li></ul></td>
</tr>
</tbody>
</table>

#### View
* workerSummary is the default view for <span class="label label-info">GET</span> ```/workers```. This view displays limited information about a worker.
* workerProfile is the default view for <span class="label label-info">GET</span> ```/workers/{id}```. This view displays additional information about a worker.
* timeOffSummary displays the total hourly balance for hourly plans for a worker.

#### Search
The search query parameter searches worker names for matches. The search is case-insensitive and only matches names that start with that text. Example: These searches return Jackie Chan:
```json
/workers?search=jac

/workers?search=chan

/workers?search=Cha
```
But this search doesn’t:
```json
/workers?search=ckie
```
You can also include multiple search texts. This search result includes Bruce Lee and Jackie Chan:
```json
/workers?search=jackie lee
```

### Schema
The following table lists the JSON name/value pairs returned in the response body for the workerSummary and workerProfile views. Unless specified, the values are strings. The body doesn't include empty value pairs. Additionally, pair orders can change, and we might introduce new pairs in patches between releases. Your application must respond to these changes.

| Name | workerSummary | workerProfile | Notes |
|-------|--------|---------|---------|
| descriptor | X | X | 	Display name of the object.<br/><br/>Depending on your configurations on the **Edit Tenant** task, the descriptor returns the worker's legal name, preferred name, or a concatenation of the legal and preferred. |
| id | X | X | Reference ID. |
| href | X | X | URL that represents the object. |
| businessTitle | X | X | |
| dateOfBirth | | X | |
| isManager | X | X | Boolean. |
| location | | X | Location object. |
| primarySupervisoryOrganization | X | X | Supervisory organization object. |
| primaryWorkAddressText | | X | |
| primaryWorkEmail | X | X | |
| primaryWorkPhone | X | X | |
| supervisoryOrganizationsManaged | | X | Supervisory organizations managed by the worker. |
| yearsOfService | | X | |

The timeOffSummary  view returns fewer JSON name/value pairs in the response body than the workerSummary view. However, the timeOffSummary view returns a worker's totalHourlyBalance.

### Request and Response Examples
This is a request for all workers available to the current user:
```json
GET /workers
```
The response returns a collection of workers (only 2 workers in this response):
```json
{
   "total": 303,
   "data":    [
            {
         "descriptor": "Hank Hill",
         "id": "6dcb8106e8",
         "href": "https://{Work REST API Endpoint}/workers/6dcb8106e8",
         "primarySupervisoryOrganization":          {
            "descriptor": "Strickland Propane",
            "id": "dd2061e4fd",
            "href": "https://{Work REST API Endpoint}/supervisoryOrganizations/dd2061e4fd"
         },
         "businessTitle": "Senior Customer Services Representative",
         "primaryWorkEmail": "hank.hill@propane.com",
         "isManager": true,
         "primaryWorkPhone": "+1 (817) 721-9821"
      },
            {
         "descriptor": "Peggy Hill",
         "id": "1da8b42231",
         "href": "https://{work REST API Endpoint}/workers/1da8b42231",
         "primarySupervisoryOrganization":          {
            "descriptor": "Arlen High School",
            "id": "31fd8a267e",
            "href": "https://{work REST API Endpoint}/supervisoryOrganizations/31fd8a267e"
         },
         "businessTitle": "Substitute Teacher",
         "primaryWorkEmail": "peggy.hill@work.net",
         "isManager": false,
      },
     ...
 ]
}
```
This is a request for 5 workers, starting with the 100th worker, available to the current user:
```json
GET /workers?limit=5&offset=99
```
The response returns a collection of workers (only 1 worker in this response):
```json
{
      "total": 303,
      "data":
      [
          {
              "descriptor": "James Bond",
              "id": "19f7dabb79",
              "href": "https://{work REST API Endpoint}/workers/19f7dabb79",
              "primarySupervisoryOrganization":
              {
                  "descriptor": "MI6",
                  "id": "7159687c81c24f91b0769772c4a6ac90",
                  "href": "https://{work REST API Endpoint}/supervisoryOrganizations/7159687c81"
              },
              "businessTitle": "Secret Agent",
              "primaryWorkEmail": "james.bond@MI6.net",
              "isManager": false,
          },
        ...
      ]
   }
```
This is a request for workers whose names (first, last, or middle) start with carl, available to the current user:
```json
GET /workers?search=carl
```
The response returns a collection of 4 workers:
```json
{
       "total": 4,
       "data":
       [
           {
               "descriptor": "Carl Carlton",
               "id": "1da8b42231",
               "href": "https://{work REST API Endpoint}/workers/1da8b42231",
               "primarySupervisoryOrganization":
               {
                   "descriptor": "Accounting Department",
                   "id": "31fd8a267e",
                   "href": "https://{work REST API Endpoint}/supervisoryOrganizations/31fd8a267e"
               },
               "businessTitle": "Accounting Specialist",
               "primaryWorkEmail": "carl.carlton@work.net",
               "isManager": false,
           },
           {
               "descriptor": "Carlos Smith",
               "id": "18294789b9",
               "href": "https://{work REST API Endpoint}/workers/18294789b9",
               "primarySupervisoryOrganization":
               {
                   "descriptor": "Buyer",
                   "id": "50577df7ae",
                   "href": "https://{work REST API Endpoint}/supervisoryOrganizations/50577df7ae"
               },
               "businessTitle": "Director, Buyer",
               "primaryWorkEmail": "carlos@work.net",
               "isManager": true,
           },
           {
               "descriptor": "Bob Carlisle",
               "id": "c66430f9a4",
               "href": "https://{work REST API Endpoint}/workers/c66430f9a4",
               "primarySupervisoryOrganization":
               {
                   "descriptor": "Business Department",
                   "id": "64a64b71dc",
                   "href": "https://{work REST API Endpoint}/supervisoryOrganizations/64a64b71dc"
               },
               "businessTitle": "Business Manager",
               "primaryWorkEmail": "bob@work.net",
               "isManager": false,
               "primaryWorkPhone": "+44 (312) 7881-9844"
           },
           {
               "descriptor": "Juan-Carlos Mendez",
               "id": "8e1d0a3b6d",
               "href": "https://{work REST API Endpoint}/workers/8e1d0a3b6d",
               "primarySupervisoryOrganization":
               {
                   "descriptor": "IT",
                   "id": "97159ecbf62d49a4936f85c338e886d2",
                   "href": "https://{work REST API Endpoint}/supervisoryOrganizations/97159ecbf6"
               },
               "businessTitle": "IT consultant",
               "primaryWorkEmail": "juan-carlos@work.net",
               "isManager": true,
           }
       ]
    }
```
This is a request for information about Rodney Dangerfield (id=66faa65677).
```json
GET /workers/66faa65677
```
The response returns additional information, compared with the previous body that contained a collection of workers:
```json
{
   "descriptor": "Rodney Dangerfield",
   "id": "66faa65677",
   "href": "https://{work REST API Endpoint}/workers/66faa65677",
   "dateOfBirth": "1921-11-22",
   "businessTitle": "Funny Guy",
   "supervisoryOrganizationsManaged": "https://{work REST API Endpoint}/workers/66faa65677/supervisoryOrganizationsManaged",
   "isManager": true,
   "location":    {
      "descriptor": "New Yotk",
      "id": "6cb76d060e"
   },
   "primarySupervisoryOrganization":    {
      "descriptor": "Executive Funny Business",
      "id": "d79004d00f",
      "href": "https://{work REST API Endpoint}/supervisoryOrganizations/d79004d00f"
   },
   "primaryWorkAddressText": "1234 Big Street, New York, NY 10001",
   "yearsOfService": "82"
}
```
This request retrieves information about Becky Park (id=1da8b42231), but instead of the default view, it uses the workerSummary view:
```json
GET /workers/1da8b42231?view=workerSummary
```
The worker in this response body contains the same information returned by default for collections of workers:
```json
{
    "descriptor": "Becky Park",
    "id": "1da8b42231",
    "href": "https://{work REST API Endpoint}/workers/1da8b42231",
    "primarySupervisoryOrganization": {
        "descriptor": "Adventure Department",
        "id": "31fd8a267e",
        "href": "https://{work REST API Endpoint}/supervisoryOrganizations/31fd8a267e"
    },
    "businessTitle": "Adventure Specialist",
    "primaryWorkEmail": "becky@work.net",
    "isManager": false
}
```
This request retrieves information about Rodney Dangerfield's time-off balance (id=66faa65677), using the timeOffSummary view:
```json
GET /workers/66faa65677?view=timeOffSummary
```
The response returns Rodney Dangerfield and his time-off balance:
```js
{
   "descriptor": "Rodney Dangerfield",
   "id": "66faa65677",
   "href": "https://{work REST API Endpoint}/workers/66faa65677",
   "totalHourlyBalance": "184"
}
```
This request retrieves all the workers available to the current user and their time-off balances, using the timeOffSummary view:
```json
GET /workers/?view=timeOffSummary
```
The response returns a collection of workers with their time-off balances (only 2 workers in this response):
```json
{
   "total": 130,
   "data":    [
            {
         "descriptor": "Leslie Nielsen",
         "id": "6dcb8106e8",
         "href": "https://{work REST API Endpoint}/workers/6dcb8106e8",
         "totalHourlyBalance": "144"
      },
            {
         "descriptor": "Clover Fields",
         "id": "1da8b42231",
         "href": "https://{Wor REST API Endpoint}/workers/1da8b42231",
         "totalHourlyBalance": "184"
      },
     ...
 ]
}
```
