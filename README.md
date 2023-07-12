* To install MongoDB on Ubuntu Server 20.04, you can follow these steps:

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
