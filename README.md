# How to Run MongoDB as a Docker Container 

## Using mongorestore for Restoring MongoDB Backups
- Create a subdirectory, e.g. `blog` inside main project directory.
- Inside the subdirectory `blog`, add or move the MongoDB Backups collections.
- 

1. Create `Dockerfile` for build mongo image
- Make sure in `Dockerfile` the `blog` dir to container by add `COPY blog/ ./` or `COPY ./ ./`
- `docker version`

 ### Run MongoDB image as a container
- `docker run -d --name mongodb -p 27017:27017 mongo `
- `docker ps`
### Connect the MongoDB to the Docker Container
- `docker exec -it [container-Id] sh`
Validate the MongoDB Command is Running
- `db.runCommand({hello:1})`
This should yield the below output.
```
{
  isWritablePrimary: true,
  topologyVersion: {
    processId: ObjectId('67928b458749b8ed16b653e6'),
    counter: Long('0')
  },
  maxBsonObjectSize: 16777216,
  maxMessageSizeBytes: 48000000,
  maxWriteBatchSize: 100000,
  localTime: ISODate('2025-01-24T06:55:27.116Z'),
  logicalSessionTimeoutMinutes: 30,
  connectionId: 50,
  minWireVersion: 0,
  maxWireVersion: 25,
  readOnly: false,
  ok: 1
}
```

### Using MongoDB mongorestore
- `mongosh`
- create a new database by `use blog`
- Enter `exit`
- `mongorestore --host "127.0.0.1" --port 27017 ./blog`
- `mongosh`