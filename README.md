Spring Cloud Config Server Demo
===============================

Showcase with Spring cloud config server bug:
[https://github.com/spring-cloud/spring-cloud-config/issues/1254](https://github.com/spring-cloud/spring-cloud-config/issues/1254)

Should be sure have this directory and files
**file:///D:/code/demo/config-server/target/config-repo**

open the project **resources/application.yml** file change the config directory path with your

    
    spring:
      profiles: native,dev
      cloud:
        config:
          server:
            fail-fast: true
            native:
              #should be sure have this directory and files
              search-locations: file:///D:/code/demo/config-server/target/config-repo
              #search-locations: file:///data/config/demo/config-server/config-repo
              #search-locations: classpath:config-repo/
              addLabelLocations: true
              default-label: @profile.env@
     

visit url: http://127.0.0.1:8888/dev/abvc-user-service.properties