# Portfolio Web - Automated CI/CD Deployment

A static web portfolio automated with Continuous Integration and Continuous Deployment (CI/CD) using **Jenkins** and **Nginx**.

Every change pushed to this repository triggers an automated Jenkins pipeline that fetches the latest code and deploys the web content directly to the target Nginx web server.

---

## 📁 Repository Structure

```text
portfolio-web/
├── index.html       # Main HTML website file
├── jenkinsfile      # Declarative CI/CD pipeline script
└── README.md        # Project documentation

🚀 CI/CD Workflow
Push: Developer pushes code changes (index.html) to the main branch on GitHub.

Pull: Jenkins detects the update and pulls the repository via SCM.

Deploy: The pipeline automatically copies index.html to the Nginx web root directory (/var/www/html/).

Serve: Nginx serves the updated website instantly.

⚙️ Prerequisites
Before configuring the pipeline in Jenkins, ensure the target server has:

Nginx installed and running:

Bash
sudo apt update
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
Directory Permissions: Ensure the jenkins user has write access to the web directory:

Bash
sudo chown -R jenkins:jenkins /var/www/html
sudo chmod -R 755 /var/www/html

🛠️ Jenkins Pipeline Setup
Open Jenkins Dashboard and click New Item.

Enter a project name (e.g., portfolio-deploy) and select Pipeline.

Scroll down to the Pipeline section:

Definition: Select Pipeline script from SCM

SCM: Select Git

Repository URL: https://github.com/Abhichaman/portfolio-web.git

Branch Specifier: */main

Script Path: Jenkinsfile

Click Save and select Build Now to run the deployment.
