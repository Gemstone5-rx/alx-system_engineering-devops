# Web infrastructure design

## 0. Simple Web Stack

### Specifics About This Infrastructure:
---
- **Server:** A server is a powerful computer designed to store and manage data, run services, and respond to requests from other computers over a network.

- **Domain Name:** A domain name, like "www.foobar.com," is a human-readable label used to identify resources on the internet. It provides an easy-to-remember way to access websites and other services.

- **DNS Record:** The DNS (Domain Name System) is responsible for translating human-readable domain names into IP addresses that computers understand. The "www" in "www.foobar.com" is a subdomain, and the DNS record "www" is usually a CNAME (Canonical Name) record pointing to the main domain or another DNS record.

- **Web Server (Nginx):** The web server handles incoming HTTP requests from users' browsers and serves web pages and assets in response. It also manages SSL/TLS encryption for secure connections.

- **Application Server:** The application server hosts the actual codebase of the website. It processes dynamic content, performs business logic, and interacts with the database. It's often connected to the web server through an internal network.

- **Application Files (Code Base):** These are the files containing the website's source code, including HTML, CSS, JavaScript, and any server-side code (e.g., PHP, Python, Ruby).

- **Database (MySQL):** The database stores and manages structured data, such as user information, content, and configurations. MySQL is a relational database management system that allows efficient data storage and retrieval.

- **User Communication:** The server communicates with the user's computer using the HTTP protocol. When a user types "www.foobar.com" in their browser, their computer sends an HTTP request to the server at IP address 8.8.8.8.

---
#### Issues with this Infrastructure:
---
- **Single Point of Failure (SPOF):** Since all components are hosted on a single server, if the server fails, the entire website goes down. To mitigate this, redundancy measures like backup servers and load balancers should be considered.

- **Downtime during Maintenance:** When updates or maintenance are needed, the web server might need to be restarted, resulting in downtime for users. Load balancers and multiple servers in a cluster can help achieve zero-downtime deployments.

- **Limited Scalability:** This infrastructure might struggle to handle high traffic loads because all services are hosted on a single server. Scaling would require adding more servers, load balancing, and optimizing the architecture.
