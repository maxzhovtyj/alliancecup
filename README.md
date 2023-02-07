# AllianceCup project

---

### Run
```
docker-compose up --build client server
```

### Create images bucket (Minio)
```
docker-compose run createbuckets
```

### Apply migration files to database
* Step 1
```
cd ./migrator
```
* Step 2
```
docker build -t app-migrator .
```

* Step 3
```
docker run --network host app-migrator -path=/migrations -database "postgresql://postgres:30042003@localhost:5436/postgres sslmode=disable" up
```

---

### Clone submodules
```
git submodule update --init --recursive
```