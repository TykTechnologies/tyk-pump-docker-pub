Official Tyk Pump Docker Build
==============================

This container only contains the Tyk Pump, an application that facilitates moving data between Tyk and Tyk Dashboard

Tyk Pump will run with a default configuration unless it has been overridden with the -v flag. A sample configurations have been provided to run Tyk Pump with the assumed linked containers under `mongo` and `redis`

Quickstart
----------

1. Get a redis container (required - or use an external redis server): 

	`docker pull redis`

2. Get Tyk Gateway

	`docker pull tykio/tyk-pump`
    
3. Run redis:
	
	`docker run -d --name tyk_redis redis`

4. Run a MongoDB container

5. Run Tyk Pump:

	`docker run -d --name tyk_pump --link tyk_redis:redis --link tyk_mongo:mongo tykio/tyk-pump`



