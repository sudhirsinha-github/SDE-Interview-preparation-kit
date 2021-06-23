

### Performance comparison for CRUD wih single node and distributed nodes 

```
1. The performance time of Couchbase is very similar with the performance time
of PostgreSQL for insert with same system configuration. CouchDB is exponentially faster

2. update :  PostgreSQL has the worst performance .MOngo and couchbase have better, couchdb is winner.

3. Delete : For the document oriented databases, again CouchDB has the lowest time
in both cases, followed by MongoDB and Couchbase. postgres is worse

4. Read/fetching - Mongodb is fastest with huge data. couchbase faster in read cmp to postgresDB

Conclusion :: Couchdb is good in performance for insert updates delete . Mongo is fasterst in read but  slower in insert .

Between the document oriented databases CouchDB has an
overall very good performance time for the INSERT, UPDATE
and DELETE operations, but it falls behind when it comes
to modeling the data. This database does not support nested
documents as in MongoDB / Couchbase , applications doing intensive write operations a good choice
would be CouchDB.

the performance of Couchbase and PostgreSQL are very similar. Couchbase main distributed
environment is based on a shared everything architecture and
every time a new node is added its resources are added to the
shared resource pool. This feature makes Couchbase a good
choice when it comes to intensive data processing applications.

```
