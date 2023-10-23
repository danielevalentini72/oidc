# oidc sample test 

### Start Keycloack on local machine with docker on port 8081

>  docker run -d -p 8081:8080 -e KEYCLOAK_ADMIN=keycloack -e KEYCLOAK_ADMIN_PASSWORD=keycloack quay.io/keycloak/keycloak:22.0.4 start-dev

* username: **keycloack** 
* password: **keycloack**

#### Create images on localhost:5000 local registry of docker with follow command :

``docker build -t [**user**]/[**name-image**] .``

* user: **danidepp** 
* name-image: **apache-oidc**

#### Your list image after the creation :

``REPOSITORY          TAG      IMAGE ID       CREATED         SIZE`` <br>
``apache2-oicd        latest   5a631910fafc   2 days ago      212MB``<br>
``my-apache2          latest   62298395ddcd   2 days ago      168MB``<br>

> CAUTE ATTENTION
>
>> Remember ever that file conf must be present in the same directory like this.
>>
>> auth_openidc.conf

#### Find the adddress Keycloack started on local machine with network inspect :

> docker network ls
>>   docker network inspect [(id)]
>> dd
>>
>>  d "ConfigOnly": false,<br>
>>        "Containers": {<br>
>>            "77d55d0e5b04e4956786772d79614c38d2a9b09b6352e669161e26a9c561c0c6": {<br>
>>                "Name": "sleepy_montalcini",<br>
>>                "EndpointID": "281b915a902a3e5b3075e6fd3001a6b392fc2401477256ec79f1cebcc851126b",<br>
>>                "MacAddress": "02:42:ac:11:00:02",<br>
>>                "IPv4Address": "**172.17.0.2**/16",<br>
>>                "IPv6Address": ""<br>
>>            }<br>
>>        },<br>
>>        "Options": {<br>
>>            "com.docker.network.bridge.default_bridge": "true",<br>
>>            "com.docker.network.bridge.enable_icc": "true",<br>
>>            "com.docker.network.bridge.enable_ip_masquerade": "true",<br>
>>            "com.docker.network.bridge.host_binding_ipv4": "0.0.0.0",<br>
>>            "com.docker.network.bridge.name": "docker0",<br>
>>            "com.docker.network.driver.mtu": "1500"<br>
>>        },<br>
>> 


#### Open console keycloack and configure your realm 

<https://localhost:8081>

![Console keycloack for create REALM!](/console.png)
