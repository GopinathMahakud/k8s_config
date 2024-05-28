1) MySQL Deployment as a StatefulSet

    a) Configuration and Deployment:
         Created and deployed mysql-statefulset.yaml with one replica named mysql-0.
         This setup was tested via the CLI with input data.
     b) Data Persistence:
         Deleted and restarted the pod, and confirmed that the data persisted.
   c) Testing in the Cluster:
         Used the following commands to test MySQL within the cluster:
              kubectl exec -it mysql-0 -- /bin/bash
              mysql -h mysql-0.mysql -u root -p

2) Spring Boot Application for DB Testing

        Created a Spring Boot application to test the MySQL database using an API.
        Built a Docker image for the Spring Boot application.
                mvn install -DskipTests
                docker build -t gopinathmahakud/gopimkd:nagp7 .
                docker push gopinathmahakud/gopimkd:nagp7
    
                 docker file link: https://github.com/GopinathMahakud/k8s/blob/master/dockerfile
                 docker image link: https://hub.docker.com/layers/gopinathmahakud/gopimkd/nagp7/images/sha256:261eb013d823d72fae64c819f6cc476b75d678b3b1f3a96ccc7346dce41ebcb9?uuid=5270E824-7E53-4EAE-925E-A59149E5B950
       deployed the yaml config deployment-spring.yaml.
       3 replicas created for the same.
 4) HorizontalPodAutoscaler created using config yaml

