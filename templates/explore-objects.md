## Explore objects in buckets & containers

Quickly explore objects to understand the structure of how the data is landing in the bucket/container:

AWS S3 Object Store:

```
SELECT location(CHAR(100)), ObjectLength FROM READ_NOS (
  USING
    LOCATION ('/s3/,bucket url>')
    ACCESS_ID ('access_id')
    ACCESS_KEY ('access_key')
    RETURNTYPE ('NOSREAD_KEYS')
  )
AS d ORDER BY 1;
```

Azure Blob Object Store:

```
SELECT location(CHAR(100)), ObjectLength FROM READ_NOS (
  USING
    LOCATION ('/az/,bucket url>')
    ACCESS_ID ('access_id')
    ACCESS_KEY ('access_key')
    RETURNTYPE ('NOSREAD_KEYS')
  )
AS d ORDER BY 1;
```

MinIO Object Store:

```
SELECT location(CHAR(100)), ObjectLength FROM READ_NOS (
  USING
    LOCATION ('/s3/,bucket url>')
    ACCESS_ID ('access_id')
    ACCESS_KEY ('access_key')
    RETURNTYPE ('NOSREAD_KEYS')
  )
AS d ORDER BY 1;
```

As well as understand how much data might have landed to date:

```
SELECT count/jira/images/icons/emoticons/star_yellow.png FROM READ_NOS (
  USING
    LOCATION ('/s3/,bucket url>')
    ACCESS_ID ('access_id')
    ACCESS_KEY ('access_key')
    RETURNTYPE ('NOSREAD_KEYS')
  )
AS d;
```

More importantly, you can explore the content of one of these objects/blobs and by previewing a sample of the data:

```
SELECT payload FROM READ_NOS (
  USING
    LOCATION ('/s3/,bucket url>')
    ACCESS_ID ('access_id')
    ACCESS_KEY ('access_key')
    RETURNTYPE ('NOSREAD_RECORD')
  )
AS d;
```