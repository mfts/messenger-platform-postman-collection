# Postman Collection for Messenger Platform

This is a [Postman](https://getpostman.com) collection that covers pretty much every API request available for the Messenger Platform. This collection should be useful for getting started working with your bot to try out features and send all the different message types. You can also use it once you are in production to send messages!

## Environment Variables

This collection makes liberal use of [Postman environment variables](https://www.getpostman.com/docs/postman/environments_and_globals/manage_environments) to automate API requests to the greatest extent possible. Anytime you see `{{SOME_VAR_NAME}}` in a request body or URI, that's a Postman env var.

### Required Environment Variables

**At a minimum** you should set these environment variables, since they are needed for almost all Messenger Platform API requests, especially message sends.

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `PSID` | String | A page-scoped ID | Specifies the user to target. This will be used as the default user for all requests. To get this, send a message to your bots and extract the `id` property from the `messages` webhook event. |
| `PAGE_TOKEN` | String | Your Page access token  | Almost all API requests. Available in the 'Token Generation' section of your app's Messenger settings. |
| `SET_ENV`| Boolean | Sets whether other env vars will be automatically set from API responses when you use Postman's collection runner. | This is a convenience so that you don't have to manually set a bunch of IDs for all the different API requests. |

### Optional Environment Variables

Many of the optional vars will be set for you if you set the `SET_ENV` env var to `TRUE` and run Postman's collection runner. You can also set these manually if you want.

#### Reusable Assets

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `IMAGE_ATTACHMENT_ID` | String | An `attachment_id` of an uploaded image | The `attachment_id` to use for message sends with an image. |
| `VIDEO_ATTACHMENT_ID` | String | An `attachment_id` of an uploaded video | The `attachment_id` to use for message sends with a video. |

#### Handover Protocol

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `APP_ID_PRIMARY` | String | An app ID | The app ID for the Facebook app you want to use as the Primary Receiver for your bot. |
| `APP_ID_SECONDARY` | String | An app ID | The app ID for the Facebook app you want to use as the Secondary Primary Receiver for your bot. |

#### Broadcast API

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `MESSAGE_CREATIVE_ID_ALL` | String | A `message_creative_id` | The `message_creative_id` of a message creative to broadcast to all open conversations. |
| `MESSAGE_CREATIVE_ID_TARGETED` | String | A `message_creative_id` | The `message_creative_id` of a message creative to broadcast to open conversations associated with a custom label. |
| `REACH_ESTIMATION_ID` | String | A `reach_estimation_id` | The `reach_estimation_id` to start a reach estimation for. |
| `CUSTOM_LABEL_ID` | String | A `custom_label_id` | The `custom_label_id` to associate with PSIDs or to target a broadcast to.  |

#### ID Matching

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `ASID`  | String | A user's app-scoped ID | The app-scoped ID to match with the ID Matching API. |
| `APP_TOKEN` | String | An app token | The app token to use with the ID Matching API. |
| `APP_SECRET` | String | An app secret | The app secret to use with the ID Matching API. |
| `APP_SECRET_PROOF` | String | An app secret proof | The [app secret proof](https://developers.facebook.com/docs/graph-api/securing-requests#appsecret_proof) to use with the ID Matching API. |

#### Built-in NLP

| **Env Var** | **Type** | **Description** | **What's it For?** |
| ----------- | -------- | --------------- | ------------------ |
| `WIT_TOKEN` | String | A Wit.ai server access token | Connects your Messenger bot to a Wit.ai custom model. Available in the settings for your [Wit.ai](https://wit.ai/) app. |
