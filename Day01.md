
# 📒 Linux & DevOps Notes

## **Day-01 (Basic)**

---

### 🌍 1. How does the Internet work?

* **Definition**: The Internet is a global network of connected computers that communicate using the **TCP/IP protocol**.
* **How it works (step-by-step):**

  1. You type `www.google.com` in a browser.
  2. The **DNS (Domain Name System)** converts this domain into an IP address (e.g., 142.250.183.14).
  3. Your request travels via your ISP → Internet backbone → Google’s server.
  4. The server processes your request and sends back a **response (HTML, CSS, JS, data)**.
  5. Your browser renders the response into a webpage.

⚡ **Key Concepts**:

* **Client-Server Model**: Client (browser) sends request → Server responds.
* **Protocols**: HTTP/HTTPS, FTP, SMTP, DNS.
* **Packets**: Data is broken into small pieces for transfer.

---

### 🖥 2. What is a Server?

* A **server** is a computer that provides services to other machines (clients).
* It runs continuously and handles requests.
* Examples:

  * **Web Server** → Serves websites (Nginx, Apache).
  * **Database Server** → Stores and manages data (MySQL, PostgreSQL).
  * **File Server** → Stores & shares files.
  * **Mail Server** → Handles emails.

👉 In DevOps, servers are often hosted in **cloud (AWS, Azure, GCP)** or **containers (Docker, Kubernetes)**.

---

### 🌐 3. Difference Between Web Server and Application Server

| Feature     | Web Server                                          | Application Server                                                                     |
| ----------- | --------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Purpose     | Delivers **static content** (HTML, CSS, JS, images) | Runs **business logic** (process requests, interact with DB, generate dynamic content) |
| Examples    | Apache, Nginx, IIS                                  | Tomcat, JBoss, WebLogic                                                                |
| Handles     | HTTP requests/responses                             | Application execution + integrations                                                   |
| DevOps Role | Reverse proxy, load balancer, serving frontend      | Running APIs, backend apps                                                             |

👉 Often both work together: **Web server (Nginx)** in front → **App server (Tomcat/Node.js)** behind.

---

### 📱 4. Types of Applications

1. **Standalone Applications**

   * Installed locally on a system.
   * Doesn’t require internet.
   * Example: MS Word, Photoshop, VLC.

2. **Web Applications**

   * Run on web browsers.
   * Require internet & a server.
   * Example: Gmail, Facebook, LinkedIn.

3. **Mobile Applications**

   * Run on smartphones (iOS/Android).
   * Example: WhatsApp, Instagram.

4. **Enterprise Applications**

   * Large-scale, used in businesses.
   * Example: ERP, CRM systems.

---

### 💻 5. What are Standalone Apps?

* Apps that run **independently on a machine** without internet or external servers.
* Installed using setup files (`.exe`, `.msi`, `.rpm`, `.deb`).
* Example: Calculator, Notepad, Photoshop.

---

### 🌎 6. What are Web Applications?

* Applications that run **via web browsers**.
* Require internet & server connection.
* Advantages: Accessible anywhere, easy updates.
* Example: YouTube, Gmail, Trello, GitHub.

---

### 🛠 7. What is Application Support?

* **Definition**: Ongoing **monitoring, troubleshooting, and user assistance** for an application after deployment.
* Tasks include:

  * Monitoring logs & performance.
  * Debugging issues/errors.
  * Ensuring uptime & availability.
  * Handling user queries.

👉 Example in DevOps: An engineer checks logs (`journalctl`, `grep`, `tail -f`) when users report an application crash.

---

### 🔧 8. What is Application Maintenance?

* **Definition**: Continuous **updating, upgrading, and improving** an application to keep it secure and efficient.
* Types of maintenance:

  1. **Corrective** → Fixing bugs.
  2. **Adaptive** → Updating for new OS/tech.
  3. **Perfective** → Improving performance/features.
  4. **Preventive** → Avoiding future issues.

👉 Example: Updating a web app for **security patches**, moving to a new database version, or improving API response time.

---
