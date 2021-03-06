---
swagger: "2.0"
x-collection-name: Meetup
x-complete: 0
info:
  title: Meetup Comments
  description: API method for accessing meetup group comments
  version: 1.0.0
host: api.meetup.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /comments:
    get:
      summary: Comments
      description: API method for accessing meetup group comments
      operationId: groups
      x-api-path-slug: comments-get
      parameters:
      - in: query
        name: group_id
        description: Return comments in groups with these ID numbers [separated by
          commas]
        type: string
      - in: query
        name: group_urlname
        description: Return comments for the group with this custom URL path
        type: string
      - in: query
        name: topic, groupnum
        description: Return comments for the group with given topic and number
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - Comments
x-streamrank:
  polling_total_time_average: "0.1"
  polling_size_download_average: "1895.84"
  streaming_total_time_average: "0.06"
  streaming_size_download_average: "965.25"
  change_yes: "106"
  change_no: "1754"
  time_percentage: "41"
  size_percentage: "49"
  change_percentage: "6"
  last_run: "2018-05-12"
  days_run: "6"
  minute_run: "0"
---