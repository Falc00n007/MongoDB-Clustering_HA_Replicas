<p align="center">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=mongodb,linux, " />
  </a>
</p>


# To install MongoDB on Ubuntu Server 20.04, you can follow these steps:

Step 1: Import the MongoDB GPG Key
```
wget -qO - https://www.mongodb.org/static/pgp/server-5.0.asc | sudo apt-key add -
```

Step 2: Create a source list file for MongoDB
```
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/5.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-5.0.list
```

Step 3: Refresh the package database
```
sudo apt update
```

Step 4: Install MongoDB
```
sudo apt install mongodb-org
```

This command will install the MongoDB server and related packages.

Step 5: Start and Enable MongoDB
```
sudo systemctl start mongod
sudo systemctl enable mongod
```

This will start the MongoDB service and configure it to start automatically on system boot.

Step 6: Verify the MongoDB Installation
```
mongo --version
```

Running this command should display the installed version of MongoDB.

That's it! MongoDB is now installed on your Ubuntu Server 20.04. You can proceed with further configuration or connecting to MongoDB as needed.


# Here's a MongoDB clustering and replication command cheat sheet:

1. **Replica Set Operations:**
   - `rs.initiate()`: Initialize a new replica set.
   - `rs.add(<hostname>)`: Add a member to the replica set.
   - `rs.remove(<hostname>)`: Remove a member from the replica set.
   - `rs.status()`: Get the status of the replica set.
   - `rs.stepDown()`: Force the current primary to step down and trigger an election.
   - `rs.reconfig(<config>)`: Reconfigure the replica set with a new configuration.

2. **Sharding Operations:**
   - `sh.enableSharding(<database>)`: Enable sharding for a specific database.
   - `sh.shardCollection("<namespace>", <key>)`: Shard a collection based on a specified key.
   - `sh.addShard("<hostname>")`: Add a shard to the cluster.
   - `sh.removeShard("<shard_name>")`: Remove a shard from the cluster.
   - `sh.status()`: Get the status of the sharded cluster.
   - `sh.getBalancerState()`: Check the state of the balancer process.
   - `sh.stopBalancer()`: Stop the balancer process temporarily.
   - `sh.startBalancer()`: Start the balancer process.

3. **General Cluster Operations:**
   - `mongos`: Start the mongos process (router) for sharded clusters.
   - `mongo --host <hostname> --port <port>`: Connect to a specific MongoDB instance.
   - `db.isMaster()`: Check if the current instance is a primary or secondary node.
   - `db.printSlaveReplicationInfo()`: Get information about the replication status of a secondary node.
   - `db.runCommand({ replSetGetStatus: 1 })`: Get the status of the replica set from a primary node.

Remember that these commands are just examples, and they should be adjusted based on your specific MongoDB deployment, version, and configuration. It is recommended to consult the official MongoDB documentation for more detailed information on clustering, replication, and sharding.


# Here's a MongoDB command cheat sheet with some commonly used commands:

1. **Database Operations:**
   - `use <database_name>`: Switch to a specific database.
   - `show dbs`: List all databases.
   - `db.dropDatabase()`: Delete the current database.

2. **Collection Operations:**
   - `db.createCollection(<collection_name>)`: Create a new collection.
   - `db.<collection_name>.drop()`: Delete a collection.
   - `db.<collection_name>.insertOne(<document>)`: Insert a single document into a collection.
   - `db.<collection_name>.insertMany([<doc1>, <doc2>, ...])`: Insert multiple documents into a collection.
   - `db.<collection_name>.find()`: Retrieve all documents from a collection.
   - `db.<collection_name>.findOne(<query>)`: Retrieve a single document matching the query.
   - `db.<collection_name>.updateOne(<filter>, <update>)`: Update a single document that matches the filter.
   - `db.<collection_name>.updateMany(<filter>, <update>)`: Update multiple documents that match the filter.
   - `db.<collection_name>.deleteOne(<filter>)`: Delete a single document that matches the filter.
   - `db.<collection_name>.deleteMany(<filter>)`: Delete multiple documents that match the filter.

3. **Querying and Filtering:**
   - `db.<collection_name>.find(<query>)`: Retrieve documents based on the specified query.
   - `db.<collection_name>.find().sort(<field>)`: Sort documents based on a field in ascending order.
   - `db.<collection_name>.find().sort({ <field>: -1 })`: Sort documents based on a field in descending order.
   - `db.<collection_name>.find().limit(<num>)`: Limit the number of documents returned.
   - `db.<collection_name>.find().skip(<num>)`: Skip a specified number of documents.

4. **Indexing:**
   - `db.<collection_name>.createIndex({ <field>: 1 })`: Create an index on a field in ascending order.
   - `db.<collection_name>.createIndex({ <field>: -1 })`: Create an index on a field in descending order.
   - `db.<collection_name>.getIndexes()`: Get a list of indexes in a collection.
   - `db.<collection_name>.dropIndex({ <field>: 1 })`: Drop an index from a collection.

These are just a few examples of MongoDB commands. The MongoDB documentation provides more detailed information on each command and its options.
