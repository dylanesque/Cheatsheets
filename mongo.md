# Commands

- `mongo`: starts the shell client

- `use DATABASE_NAME`: creates a db os specified name if one doesn't exist, or switches to that db if it already exists

- `db.help()`: displays options

- `db.createCollection(COLLECTION_NAME, OPTIONS)`: creates a collection

- `show collections`: shows all collections

- `db.COLLECTION_NAME.drop`: removes specified collection

- `db.COLLECTION_NAME.insert(JSON_DATA)`: inserts specified data into the collection

- `db.COLLECTION_NAME.findOne(QUERY)` or `db.COLLECTION_NAME.find(QUERY)`: queries specified collection

- `db.COLLECTION_NAME.update(SELECTION_CRITERIA, UPDATED_DATA)`: updates collection

- `db.collection_name.remove(query)`: removes collection

- `db.COLLECTION_NAME.createIndex({ FIELD_NAME: 1})`: creates an index on a field of a collection

# Replica Sets

- Replication is how Mongo spreads it's data out to avoid loss of data from one server
- 
