---
title: Reference
tags:
keywords:
last_updated:
summary:
sidebar: mydoc_sidebar
permalink: reference.html
folder: mydoc
---

### Resource description
Wallets store your private keys and contain additional details. You can only view wallets that you know the wallet ID for.

### Endpoint
<div class="alert alert-success"><span class="label label-info">GET</span> /{coin}/wallet/{walletId}</div>

### Parameters

#### Path
<table>
<colgroup>
<col width="15%" />
<col width="15%" />
<col width="15%" />
<col width="20%" />
<col width="70%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Required?</th>
<th>Schema</th>
<th>Data type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>coin</code></td>
<td>Yes</td>
<td>Path</td>
<td>String</td>
<td>Cryptocurrency or token ticker symbol.</td>
</tr>
<tr>
<td><code>walletID</code></td>
<td>Yes</td>
<td>Path</td>
<td>String<br><code>^[0-9a-f]{32}$</code></td>
<td>ID of the wallet.</td>
</tr>
</tbody>
</table>

#### Query

<table>
<colgroup>
<col width="15%" />
<col width="15%" />
<col width="15%" />
<col width="20%" />
<col width="70%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Required?</th>
<th>Schema</th>
<th>Data type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>allTokens</code></td>
<td>Yes</td>
<td>Query</td>
<td>Boolean</td>
<td>If true, includes data for all subtokens.</td>
</tr>
</tbody>
</table>

### Responses

#### Successful (200)
The following table lists the JSON name/value pairs returned in the response body. The body doesn't include empty value pairs.

<table>
<colgroup>
<col width="15%" />
<col width="15%" />
<col width="35%" />
<col width="70%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Required?</th>
<th>Data type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>approvalsRequired</code></td>
<td>Yes</td>
<td>Integer<br><code>>=1</code></td>
<td>Number of approvals required.</td>
</tr>
<tr>
<td><code>coin</code></td>
<td>Yes</td>
<td>String</td>
<td>Cryptocurrency or token ticker symbol.<br><i>Example: btc</i></td>
</tr>
<tr>
<td><code>deleted</code></td>
<td>Yes</td>
<td>Boolean</td>
<td>If true, the wallet was deleted.</td>
</tr>
<tr>
<td><code>disableTransactionNotifications</code></td>
<td>Yes</td>
<td>Boolean</td>
<td>If true, transaction notifications are disabled.</td>
</tr>
<tr>
<td><code>id</code></td>
<td>Yes</td>
<td>String<br><code>^[0-9a-f]{32}$</code></td>
<td>If true, transaction notifications are disabled.<br><i>Example: 59cd72485007a239fb00282ed480da1f</i></td>
</tr>
<tr>
<td><code>label</code></td>
<td>Yes</td>
<td>String</td>
<td>The label or name of the wallet.<br><i>Example: My Wallet</i></td>
</tr>
</tbody>
</table>

### Success sample

#### Request
```json
GET /btc/wallet/59cd72485007a239fb00282ed480da1f?allTokens=false
```

#### Response
This response returns details for a Bitcoin wallet, called My Wallet, that requires two approvals:
```json
{
  "approvalsRequired": 2,
  "coin": "btc",
  "deleted": false,
  "disableTransactionNotifications": false,
  "id": "59cd72485007a239fb00282ed480da1f",
  "label": "My Wallet"
}
```
