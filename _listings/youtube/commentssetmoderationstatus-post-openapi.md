---
swagger: "2.0"
x-collection-name: YouTube
x-complete: 0
info:
  title: Youtube Add Comments Set Moderation Status
  description: Sets the moderation status of one or more comments. The API request
    must be authorized by the owner of the channel or video associated with the comments.
  termsOfService: https://developers.google.com/terms/
  contact:
    name: Google
    url: https://google.com
  version: 1.0.0
host: www.googleapis.com
basePath: /youtube/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /comments:
    delete:
      summary: Delete Comments
      description: Deletes a comment.
      operationId: deleteComments
      x-api-path-slug: comments-delete
      parameters:
      - in: query
        name: id
        description: The id parameter specifies the comment ID for the resource that
          is being deleted
      responses:
        200:
          description: OK
      tags:
      - Comments
    get:
      summary: Get Comments
      description: Returns a list of comments that match the API request parameters.
      operationId: getComments
      x-api-path-slug: comments-get
      parameters:
      - in: query
        name: id
        description: The id parameter specifies a comma-separated list of comment
          IDs for the resources that are being retrieved
      - in: query
        name: maxResults
        description: The maxResults parameter specifies the maximum number of items
          that should be returned in the result set
      - in: query
        name: pageToken
        description: The pageToken parameter identifies a specific page in the result
          set that should be returned
      - in: query
        name: parentId
        description: The parentId parameter specifies the ID of the comment for which
          replies should be retrieved
      - in: query
        name: part
        description: The part parameter specifies a comma-separated list of one or
          more comment resource properties that the API response will include
      - in: query
        name: textFormat
        description: This parameter indicates whether the API should return comments
          formatted as HTML or as plain text
      responses:
        200:
          description: OK
      tags:
      - Comments
    post:
      summary: Add Comments
      description: 'Creates a reply to an existing comment. Note: To create a top-level
        comment, use the commentThreads.insert method.'
      operationId: postComments
      x-api-path-slug: comments-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: part
        description: The part parameter identifies the properties that the API response
          will include
      responses:
        200:
          description: OK
      tags:
      - Comments
    put:
      summary: Put Comments
      description: Modifies a comment.
      operationId: putComments
      x-api-path-slug: comments-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: part
        description: The part parameter identifies the properties that the API response
          will include
      responses:
        200:
          description: OK
      tags:
      - Comments
  /comments/markAsSpam:
    post:
      summary: Add Comments Mark as SPAM
      description: Expresses the caller's opinion that one or more comments should
        be flagged as spam.
      operationId: postCommentsMarkasspam
      x-api-path-slug: commentsmarkasspam-post
      parameters:
      - in: query
        name: id
        description: The id parameter specifies a comma-separated list of IDs of comments
          that the caller believes should be classified as spam
      responses:
        200:
          description: OK
      tags:
      - Comments
      - Markasspam
  /comments/setModerationStatus:
    post:
      summary: Add Comments Set Moderation Status
      description: Sets the moderation status of one or more comments. The API request
        must be authorized by the owner of the channel or video associated with the
        comments.
      operationId: postCommentsSetmoderationstatus
      x-api-path-slug: commentssetmoderationstatus-post
      parameters:
      - in: query
        name: banAuthor
        description: The banAuthor parameter lets you indicate that you want to automatically
          reject any additional comments written by the comments author
      - in: query
        name: id
        description: The id parameter specifies a comma-separated list of IDs that
          identify the comments for which you are updating the moderation status
      - in: query
        name: moderationStatus
        description: Identifies the new moderation status of the specified comments
      responses:
        200:
          description: OK
      tags:
      - Comments
      - Setmoderationstatus
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---