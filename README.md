Official Tyk Pump Docker Build
==============================

This container only contains the Tyk Pump, an application that facilitates moving data between the Tyk Gateway and the Tyk Dashboard

Tyk Pump will run with a default configuration unless it has been overridden with the -v flag. A sample configurations have been provided to run Tyk Pump with the assumed linked containers under `mongo` and `redis`.

The following ports are required to be open:

For Redis: 6379
For MongoDB: 27017

Quickstart
----------

1. Get a Redis container (required - or use an external Redis server): 

	`docker pull redis`

2. Get Tyk Pump

	`docker pull tykio/tyk-pump-docker-pub`
    
3. Run Redis:
	
	`docker run -d --name tyk_redis redis`

4. Run a MongoDB container

5. Run Tyk Pump:

	`docker run -d --name tyk_pump --link tyk_redis:redis --link tyk_mongo:mongo tykio/tyk-pump-docker-pub`



