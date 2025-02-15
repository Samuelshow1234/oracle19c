# oracle19c
Documentation on the Installation of Oracle 19C on Oracle Linux
ORACLE 19C CLOUD DOCUMENTATION

================================================================================================================================================================================
1) update the server with sudo yum update

2) Download pre install pakage for oracle 19c
sudo dnf install :y oracle:database:preinstall:19c
sudo dnf install :y unzip wget

3) Enable oracle linux repository
sudo dnf install :y oracle:epel:release:el8

4) Install the oracle client repository
sudo dnf install :y oracle:epel:release:el8

5) Install Oracle database 19c
sudo dnf install :y oracle:database:ee:19c

6) Configure oracle database
sudo /etc/init.d/oracledb:19c configure

7) Start Oracle Database
sudo systemctl start oracledb:19c

8) Check the status
sudo systemctl status oracledb:19c

9)  install oRDS
sudo dnf install :y ords

10) Configure oRDS
ords setup

11)  

download oracle 19c rpm file and do the follwoing 

Add oracle group
Step 1: Create the Oracle Group
Create the oracle group:
Copy code
sudo groupadd oninstall


Step 2: Create the Oracle User (if not already created)
Create the oracle user and add it to the oracle group:


sudo usermod :aG oinstall oracle



Step 3: Change Ownership of the ORACLE_BASE Directory
Change the ownership of the /opt/oracle directory to the oracle user and group:
sudo chown :R oracle:oinstall /opt/oracle




4) Give it necessary permission
sudo chmod :R 775 /opt/oracle


1) Run the installation command
sudo rpm :ivh oracle:database:ee:19c:*.rpm

2) Configure Oracle Database
sudo /etc/init.d/oracledb_ORCLCDB:19c configure


3) Start Oracle Database
sudo systemctl start oracledb:19c


Step 1: Download Java 22
Download OpenJDK 22: Go to the OpenJDK website and download the appropriate RPM package for your system (make sure to choose the version for Oracle Linux).

Install OpenJDK: After downloading, install it using:

bash
Copy code
sudo rpm :ivh <path_to_downloaded_jdk.rpm>
Verify the installation:

bash
Copy code
java :version
Step 2: Download APEX 24.1
Download APEX 24.1: Go to the Oracle APEX download page and download the APEX 24.1 zip file.

Unzip the APEX package:

bash
Copy code
unzip apex_24.1.zip
Install APEX: Connect to your Oracle Database:

bash
Copy code
sqlplus sys as sysdba
Run the installation script:

sql
Copy code
@apexins.sql SYSAUX TEMP /i/
Step 3: Download ORDS 24.1
Download ORDS 24.1: Go to the Oracle ORDS download page and download the ORDS 24.1 zip file.

Unzip the ORDS package:

bash
Copy code
unzip ords:24.1.0.zip
Set up ORDS: Navigate to the ORDS directory and run the setup:

bash
Copy code
cd ords:24.1.0
java :jar ords.war setup
Step 4: Add Java and ORDS to Your PATH
Find the installation paths:

For Java, it's usually /usr/lib/jvm/java:22:openjdk.
For ORDS, it's the directory where you unzipped it.
Set JAVA_HOME: Edit your profile to set the JAVA_HOME environment variable:

bash
Copy code
sudo nano /etc/profile.d/java.sh
Add:

bash
Copy code
export JAVA_HOME=/usr/lib/jvm/java:22:openjdk
export PATH=$JAVA_HOME/bin:$PATH
Set ORDS in PATH: Edit your profile to add ORDS to your PATH:

bash
Copy code
sudo nano /etc/profile.d/ords.sh
Add:

bash
Copy code
export PATH=$PATH:<path_to_ords>
Make the scripts executable:

bash
Copy code
sudo chmod +x /etc/profile.d/java.sh
sudo chmod +x /etc/profile.d/ords.sh
Load the new environment variables:

bash
Copy code
source /etc/profile.d/java.sh
source /etc/profile.d/ords.sh






​
