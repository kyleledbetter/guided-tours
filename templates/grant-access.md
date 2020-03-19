## Grant access permissions

You have the ability to filter the list of managed objects by name, title, description, members/users, or available privileges to help focus your current management task.

Once you have selected an 'object', you have the ability to view a list of current members/users with their respective access privileges.

You then have the ability to add/remove/update any member/user access privileges based on internal security practices.

/* granting a new user select access to an object */

```
GRANT SELECT ON <table name/view name> TO <user>
```


/* granting a new group select access to an object */

```
GRANT SELECT ON <table name/view name> TO ALL <group of users>
```
