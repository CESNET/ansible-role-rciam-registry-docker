RCIAM Federation registry docker
=========

The role, which deploys [RCIAM federation registry](https://github.com/rciam/rciam-federation-registry) in containers using Docker compose.
Components:
1. Frontend --- serves the JavaScript application to client, forwards requests to http://backend-api:5000.
2. Backend-api --- provides the API to the client frontend application, and to RabbitMQ agent.
3. RabbitMQ agent --- communicates to the backend-api, and places change requests on a RabbitMQ queue.
4. Deployer --- processes the change requests from RabbitMQ, and redirects it to CAS and Perun.
5. RabbitMQ --- connects RabbitMQ agent and deployer.

The user of this role is responsible for providing the configuration files. Samples are available in files/localhost, where localhost is deployment_id.
The role assumes the use of private container images.

Requirements
------------

Debian. The role has been tested with Debian 13.


Author Information
------------------

Bohdan Khomutskyi <Bohdan.Khomutskyi@cesnet.cz>