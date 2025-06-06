![Scale up](images/Scale-1.png)
Scale Up
This infrastructure is an evolution of the previous one, designed to enhance scalability, availability, and maintainability by splitting responsibilities and adding redundancy.

Infrastructure Overview
This infrastructure hosts the website www.foobar.com with the following components:

2 Load Balancers (HAProxy) in cluster mode to provide redundancy and distribute traffic.

1 Web Server (Nginx) to handle static content and forward dynamic requests.

1 Application Server to execute dynamic code and handle business logic.

1 Database Server (MySQL) to store persistent data.

1 Additional Server added to scale up the infrastructure.

Added Elements and Justification
1 Additional Server: This server helps distribute workload and reduce the risk of a single point of failure. It can host a specific service (e.g., additional app server or DB replica).

1 HAProxy Load Balancer in Cluster Mode: Clustering provides high availability — if one load balancer fails, the other takes over. It prevents downtime and ensures uninterrupted access to the website.

Component Split:

Web Server: Dedicated server for Nginx to handle static files and reverse proxy dynamic requests.

Application Server: Dedicated server to run dynamic application logic (e.g., PHP, Python, Node.js).

Database Server: Dedicated MySQL server to handle data operations.

This separation improves scalability (each layer can scale independently), security (limits attack surface per server), and performance (no resource contention).

Web Server vs Application Server
Component	Web Server	Application Server
Purpose	Handles HTTP requests, serves static content	Executes dynamic content (scripts, backend logic)
Examples	Nginx, Apache	PHP-FPM, uWSGI, Gunicorn
Communicates With	Clients (browsers), App Server	Web Server, Database
Typical Content	HTML, CSS, JS, images	Python, PHP, Ruby, Node.js code execution
