## Create foreign table

Register the desired object store bucket/container data (from the main URL provided or one of its partition or object) as one or several foreign table objects within the Advanced SQL Engine.

This will create a link to your bucket or container in your thid party object store:


```
CREATE MULTISET FOREIGN TABLE <table name> ,
  EXTERNAL SECURITY INVOKER TRUSTED <authorization object>
  (
    Location VARCHAR(2048) CHARACTER SET UNICODE CASESPECIFIC,
    PAYLOAD JSON(8388096) INLINE LENGTH 32000 CHARACTER SET UNICODE )
    USING
  (
    LOCATION ('/s3/<bucket name>')
  )
NO PRIMARY INDEX;
```