## Syntax
Memcached replace command is used to replace the value of an existing key. If the key does not exist, then it gives the output NOT_STORED.

The basic syntax of Memcached replace command is as shown below
```
replace key flags exptime bytes [noreply]
value
```

The keywords in the syntax are as described below −

* key - It is the name of the unique key by which data is accessed.

* flags - It is the 32-bit unsigned integer that the server stores with the data provided by the user, and returns along with the data when the item is retrieved.

* exptime - It is the expiration time (seconds) of data stored in cache. A 0 value means "never expire", i.e. it should not be removed from the cache unless required. If the exptime is more than 30 days then Memcached interprets it as UNIX timestamp for expiration.

* bytes - This is the length of the data in bytes that needs to be stored in Memcached.

* noreply (optional) - This parameter informs the server not to send any reply.

* value - It is the data that needs to be stored. The data needs to be given on the new line after executing the command with the above options.

## Example
```
add mykey 0 900 10
data_value
STORED
get mykey
VALUE mykey 0 10
data_value
END
replace mykey 0 900 16
some_other_value
get key
VALUE mykey 0 16
some_other_value
END
```