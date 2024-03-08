# Chicago Business Intelligence (CBI) for Strategic Planning Project

## Front-End Dashboard hosted on Google Cloud Platform (GCP) 

Based on Requirements 2, 3, 5, and 6

### 1. Create SQL Queries to complete each requirement

Developed SQL queries that pulls the records for the CBI Dashboard. Review the cbi-dashboard.sql file to review each query.

### 2. Build Tableau Worksheets and Dashboard

Tableau accesses the PostgreSQL cloud database after providing login information. 

- Create new Data Source: Custom SQL Query for every requirement
- Add SQL query
- Create new  Worksheets for each requirement
- Create new Dashboard
- Add Containers to organize the worksheets within the dashboard
- Upload dashboard to Tableau Server
- Capture the embed link

### 3. Create HTML Index file

Develop index.html file that includes title, headers, and div container with the embed documentation to publish the dashboard.

### 4. Create GitHub Repository

The remote repository will store the index.html file.

### 5. Create Compute Engine VM instance

In GCP, create a new VM instance.

- Select E2 machine configuration
- Under Bootdisk, click on change
- Select Debian/Linux 11 (Bullseye) and click Create
- Under VPC network / Firewall, click on create Firewal Rule
- Under Targets, select All instances in the network
- Under Source IPv4 ranges, enter 0.0.0.0/0
- Under Protocols and ports, select TCP and add 80 (this opens HTTP)
- Click Create
- Capture external IP address
- Click SSH to prepare the web server

### 6. Add Apache to VM 

Run the following commands in the SSH window to prepare the VM by adding Apache web server software to host the dashboard website. 

```
sudo -i

apt-get update

sudo apt-get install apache2

sudo apt-get install git
```

- Open web browser, paste external IP address in address bar. Web server's default index.html will display
- In the SSH window, clone the repository 
- From the root directory overwrite the default index.html file with the file from the repository

```

sudo cp /root/{name-of-repository}/index.html /var/www/html/index.html


```

- Refresh web browser

The dashboard will display.