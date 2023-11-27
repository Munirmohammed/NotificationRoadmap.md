Controller:
AccountManagementStateChangeMessage Controller (Endpoints related to account state changes):

Endpoints:
GET /api/user/get-details/{userId} - Retrieves user details for a given user ID.
POST /api/user/get-details/{userId} - Adds user details for a given user ID.
DELETE /api/user/get-details/{userId} - Deletes user details for a given user ID.
Description: Manages user account state change messages.
PostSystemStateChangeMessage Controller (Endpoints related to post state changes):

Endpoints:
POST /api/post/add-notification - Adds a notification for a new post.
GET /api/post/view-notification/{postId} - Views notification for a specific post.
DELETE /api/post/delete-notification/{postId} - Deletes notification for a specific post.
Description: Handles notifications for post state changes.
Service:
PostSystemStateChangeService:
Methods:
addPostNotification(PostSystemStateChangeModel postSystemStateChangeModel)
viewPostNotification(PostSystemStateChangeModel postSystemStateChangeModel, String postId)
deletePostTypeNotification(PostSystemStateChangeModel postSystemStateChangeModel, String postId)
addPostTypeNotification(PostSystemStateChangeModel postSystemStateChangeModel, String typeId)
getPostTypeNotify(PostSystemStateChangeModel postSystemStateChangeModel, String typeId)
deletePostType_Notification(PostSystemStateChangeModel postSystemStateChangeModel, String typeId)
getPostTypeNotify(String typeId)
Description: Manages notifications related to post state changes, interacts with external services, and handles communication with the repository for data storage.
Account Management Endpoints:
Update User Details:

Endpoint: PUT /api/user/update-details/{userId}
Description: Allows users to update their details. This could trigger a notification for account details modification.
Get User Notifications:

Endpoint: GET /api/user/{userId}/notifications
Description: Retrieves all notifications specific to a user, filtering by their user ID.
Post System Endpoints:
Get User Posts Notifications:
Endpoint: GET /api/post/user/{userId}/notifications
Description: Retrieves all notifications related to posts for a specific user.
General Endpoints:
Delete All Notifications for a User:

Endpoint: DELETE /api/user/{userId}/notifications
Description: Deletes all notifications for a specific user.
Batch Delete Notifications:

Endpoint: DELETE /api/notifications/batch
Description: Deletes multiple notifications at once based on a list of notification IDs.
Filter Notifications by Date Range:

Endpoint: GET /api/notifications/filter/by-date
Description: Retrieves notifications within a specified date range.
