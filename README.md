# oracle-password-never-expire
Setting the database oracle password: never expire

```
SQL> connect sys/your_password as sysdba;

SQL> alter profile DEFAULT limit PASSWORD_REUSE_TIME unlimited;
SQL> alter profile DEFAULT limit PASSWORD_LIFE_TIME  unlimited;
```

Check the password expiry date for the ```USER_TEST``` user (We assume already have the ```USER_TEST``` user):

``` 
SQL> select username, account_status, EXPIRY_DATE from dba_users where username='USER_TEST';
 
USERNAME                       ACCOUNT_STATUS               EXPIRY_DATE
------------------------------ ---------------------------- ---------
USER_TEST                      OPEN                         UNLIMITED
```

Done.
