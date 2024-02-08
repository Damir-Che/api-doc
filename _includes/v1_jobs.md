## Message delivery Jobs

### Get Job details

```shell
curl "https://api.pact.im/p1/companies/COMPANY_ID/channels/<CHANNEL_ID>/jobs/<ID>"
  -H "X-Private-Api-Token: YOUR_API_TOKEN"
```

```php
<?php

/**
 * This method return info about message delivery job
 * @link https://pact-im.github.io/api-doc/?shell#message-delivery-jobs
 *
 * @param int id of the company
 * @param int id of the channel
 * @param int id of the job
 * @return Json|null
 */

$client->jobs->getJob(
  $companyId,
  $channelId,
  $jobId
);
```

> The above command returns JSON structured like this:

```json
{
   "status":"ok",
   "data":{
      "id":1,
      "company_id":1,
      "channel":{
         "id":1,
         "type":"whatsapp"
      },
      "conversation_id":1,
      "state":"delivered",
      "message_id":1,
      "details":{
         "result":"DELIVERED"
      },
      "created_at":1510393147
   }
}
```

This endpoint returns information about message delivery job

#### HTTP Request

`GET https://api.pact.im/p1/companies/<COMPANY_ID>/channels/<CHANNEL_ID>/jobs/<ID>`

#### URL Parameters

Parameter | Description
--------- | -----------
COMPANY_ID | ID of the company
CHANNEL_ID | ID of the channel
ID | ID of the job

Message may be `DELIVERED` of `NOT DELIVERED`.

Message will be `NOT DELIVERED` if case when:

 - Integration doesn't work
 - Contact is not present
 - Message was rejected by external system
