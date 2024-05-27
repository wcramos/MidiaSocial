# Mídia Social - Modelo de Dados

## Collection: users

**Description:** Stores information about registered users.

### Fields:

| Field Name | Type      | Description                        | Constraints        | Example Value         |
| ----------- | --------- | ---------------------------------- | ------------------- | --------------------- |
| \_id        | String    | Unique user identifier (auto-generated) | Required, Unique  | "5f1234567890abcdef" |
| email       | String    | User's email address               | Required, Unique  | "john.doe@example.com"  |
| name        | String    | User's full name                   | Required          | "John Doe"            |
| avatar      | String    | User photo/avatar URI              | Required          |             |
| createdAt   | Datetime | Timestamp of user creation          | Required          | "2023-12-25T12:34:56Z" |

## Collection: posts

**Description:** Stores posts data (Photos and Videos URIs)

### Fields:

| Field Name | Type      | Description                        | Constraints        | Example Value         |
| ----------- | --------- | ---------------------------------- | ------------------- | --------------------- |
| \_id        | String    | Unique post identifier (auto-generated) | Required, Unique  | "5f1234567890abcdef" |
| user       | Reference    | User's author reference                | Required  | "5f1234567890abcdef"  |
| post_text  | String    | Post Text              | Optional          |             |
| post_photos  | Array of String    | Post Photo(s) URI              | Optional          |             |
| post_video  | String    | Post Video URI              | Optional          |             |
| reactions   | Sub-collection | Sub-collection with reaction for this post (Like, Unlike) | Optional | |
| comments    | Sub-collection | Sub-collection with comments for this post (text, reactions) | Optional | |
| createdAt   | Datetime | Timestamp of user creation        | Required          | "2023-12-25T12:34:56Z" |

