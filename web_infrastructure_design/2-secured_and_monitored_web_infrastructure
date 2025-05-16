![Diagram of secure and monitored](images/secure.png)

Secured and Monitored Web Infrastructure

This infrastructure is designed to host the website www.foobar.com in a secure and monitored environment, while maintaining availability and scalability.

Elements Added
3 Firewalls: One between users and load balancer, and one before each server. Purpose: To restrict unauthorized access and block malicious traffic.

1 SSL Certificate: Installed on the load balancer to serve traffic over HTTPS, ensuring encrypted and secure communication between clients and the server.

3 Monitoring Clients (e.g., SumoLogic Agent): Installed on each server to collect logs and metrics like CPU usage, traffic, and server health for monitoring and alerting purposes.

Purpose of Each Element
Firewalls: Act as security checkpoints that control incoming and outgoing traffic based on rules, helping prevent unauthorized access and cyberattacks.

HTTPS/SSL: Encrypts the communication between users and servers, protecting data integrity and user privacy.

Monitoring Clients: Continuously collect system and application-level data. Helps in detecting performance issues, downtime, and unusual activity.

Monitoring QPS (Queries Per Second) on Web Server
To monitor QPS, configure the web server (e.g., Nginx) to expose metrics, and have the monitoring client collect them. For example, enable Nginx status module and use the monitoring tool to track requests per second.

Issues with This Infrastructure
SSL Termination at Load Balancer: If SSL ends at the load balancer, internal communication between load balancer and web servers is unencrypted, exposing a potential security risk. Solution: Use end-to-end encryption or re-encrypt traffic after the load balancer.

Single MySQL Primary Server: Only one server can handle write operations, which is a Single Point of Failure (SPOF). If it goes down, no data can be written. A possible solution is to implement a failover mechanism or use multiple writable nodes with conflict resolution.

Identical Servers (Web + App + DB): Increases risk of resource contention and security vulnerabilities. Best practice is to separate concerns by using different servers or containers for each role (web, app, DB).
