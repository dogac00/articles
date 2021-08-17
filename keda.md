# AutoScaling Kafka Consumers with KEDA

In purchase order and supply chain team, we have two Kubernetes namespaces and we have about 20-30 consumers per each namespace. And all of these consumers are most of the time waiting in an idle situation. Therefore, idle consumer pods are unnecessarily using cluster's resources.

For example in this image, we can see that application is using about 180 MBs of memory in idle situation.

<img width="834" alt="Screen Shot 2021-08-17 at 23 45 38" src="https://user-images.githubusercontent.com/26314896/129798115-e8d78ca7-8f8a-4981-a4f4-22d8a3c79f59.png">

This can affect other pods in terms of performance.


