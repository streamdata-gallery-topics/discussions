---
swagger: "2.0"
x-collection-name: Data.Gov
x-complete: 0
info:
  title: Data.gov API Add Discussions
  description: Add comment and optionnaly close a discussion given its ID
  version: "3"
host: catalog.data.gov
basePath: /api/3/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /discussions/:
    get:
      summary: Get Discussions
      description: List all Discussions
      operationId: getDiscussions
      x-api-path-slug: discussions-get
      parameters:
      - in: query
        name: closed
        description: Filters discussions on their closed status if specified
      - in: query
        name: for
        description: Filter discussions for a given subject
      - in: query
        name: page
        description: The page to fetch
      - in: query
        name: page_size
        description: The page size to fetch
      - in: query
        name: sort
        description: The sorting attribute
      responses:
        200:
          description: OK
      tags:
      - Discussions
    post:
      summary: Add Discussions
      description: Create a new Discussion
      operationId: postDiscussions
      x-api-path-slug: discussions-post
      parameters:
      - in: body
        name: payload
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Discussions
  /discussions/{id}/:
    delete:
      summary: Delete Discussions
      description: Delete a discussion given its ID
      operationId: deleteDiscussions
      x-api-path-slug: discussionsid-delete
      parameters:
      - in: path
        name: id
      responses:
        200:
          description: OK
      tags:
      - Discussions
    get:
      summary: Get Discussions
      description: Get a discussion given its ID
      operationId: getDiscussions
      x-api-path-slug: discussionsid-get
      parameters:
      - in: path
        name: id
      responses:
        200:
          description: OK
      tags:
      - Discussions
    post:
      summary: Add Discussions
      description: Add comment and optionnaly close a discussion given its ID
      operationId: postDiscussions
      x-api-path-slug: discussionsid-post
      parameters:
      - in: path
        name: id
      - in: body
        name: payload
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Discussions
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