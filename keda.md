# AutoScaling Kafka Consumers with KEDA

In purchase order and supply chain team, we have two Kubernetes namespaces for each domain and we have about 20-30 consumers per each namespace. 

When one event is under load the consumer cannot automatically scale based on the lag value. 
Because CPU and Memory metrics cannot reflect the event load on the application using traditional HPA (Horizontal Pod Autoscaler) of k8s will not work here.


These consumers are most of the time waiting in an idle situation. Therefore, idle consumer pods are unnecessarily using cluster's resources.

For example, in this image, as we can see, the application is using about 180 MBs of memory in idle situation.

<img width="834" alt="Screen Shot 2021-08-17 at 23 45 38" src="https://user-images.githubusercontent.com/26314896/129798115-e8d78ca7-8f8a-4981-a4f4-22d8a3c79f59.png">


