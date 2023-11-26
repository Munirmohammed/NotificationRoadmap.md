### Controller:

1. **AccountManagementStateChangeMessage Controller (Endpoints related to account state changes):**
   - **Endpoints:**
     - GET `/api/user/get-details/{userId}` - Retrieves user details for a given user ID.
     - POST `/api/user/get-details/{userId}` - Adds user details for a given user ID.
     - DELETE `/api/user/get-details/{userId}` - Deletes user details for a given user ID.
   - **Description:** Manages user account state change messages.

2. **PostSystemStateChangeMessage Controller (Endpoints related to post state changes):**
   - **Endpoints:**
     - POST `/api/post/add-notification` - Adds a notification for a new post.
     - GET `/api/post/view-notification/{postId}` - Views notification for a specific post.
     - DELETE `/api/post/delete-notification/{postId}` - Deletes notification for a specific post.
   - **Description:** Handles notifications for post state changes.

### Service:

1. **PostSystemStateChangeService:**
   - **Methods:**
     - `addPostNotification(PostSystemStateChangeModel postSystemStateChangeModel)`
     - `viewPostNotification(PostSystemStateChangeModel postSystemStateChangeModel, String postId)`
     - `deletePostTypeNotification(PostSystemStateChangeModel postSystemStateChangeModel, String postId)`
     - `addPostTypeNotification(PostSystemStateChangeModel postSystemStateChangeModel, String typeId)`
     - `getPostTypeNotify(PostSystemStateChangeModel postSystemStateChangeModel, String typeId)`
     - `deletePostType_Notification(PostSystemStateChangeModel postSystemStateChangeModel, String typeId)`
     - `getPostTypeNotify(String typeId)`
   - **Description:** Manages notifications related to post state changes, interacts with external services, and handles communication with the repository for data storage.


### Account Management Endpoints:

1. **Update User Details:**
   - Endpoint: `PUT /api/user/update-details/{userId}`
   - Description: Allows users to update their details. This could trigger a notification for account details modification.

2. **Get User Notifications:**
   - Endpoint: `GET /api/user/{userId}/notifications`
   - Description: Retrieves all notifications specific to a user, filtering by their user ID.

3. **Mark Notifications as Read:**
   - Endpoint: `PUT /api/user/{userId}/notifications/read`
   - Description: Marks all unread notifications for a user as 'read'.

### Post System Endpoints:

4. **Edit Post Notification:**
   - Endpoint: `PUT /api/post/edit-notification/{postId}`
   - Description: Allows editing of a posted notification.

5. **Get User Posts Notifications:**
   - Endpoint: `GET /api/post/user/{userId}/notifications`
   - Description: Retrieves all notifications related to posts for a specific user.

6. **Search Notifications by Message Content:**
   - Endpoint: `GET /api/post/notifications/search`
   - Description: Searches notifications by message content.

### General Endpoints:

7. **Get Unread Notifications Count:**
   - Endpoint: `GET /api/notifications/unread/count`
   - Description: Returns the count of unread notifications across all users.

8. **Delete All Notifications for a User:**
   - Endpoint: `DELETE /api/user/{userId}/notifications`
   - Description: Deletes all notifications for a specific user.

9. **Batch Delete Notifications:**
   - Endpoint: `DELETE /api/notifications/batch`
   - Description: Deletes multiple notifications at once based on a list of notification IDs.

10. **Filter Notifications by Date Range:**
    - Endpoint: `GET /api/notifications/filter/by-date`
    - Description: Retrieves notifications within a specified date range.