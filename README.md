<h1>Party Parrot App</h1>

<img src='media/images/party-parrot.gif' alt='parrot' height="200" width="200">
<br>
<br>
<h3></h3>

Sample Python application on Django with PostgreSQL database.

<h3>Deployment</h3>

____

*Create a folder:
```shell
      mkdir data
      
```

* Сreate file .env:
```shell
      cp .env.example .env
```


* specify user:
```shell
      chown 1000:1000 data
```

* start:
```shell
      docker compose up
```
* You can check the work by writing in the search:
```shell
      localhost:8000
```