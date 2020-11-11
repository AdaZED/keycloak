# Installation and configuration of Keycloak on a ubuntu 18.04 VM in a production mode

**1. Installation of Java:**

Make sure java is installed via:
```
java -version
```

If not, install it:
```
sudo apt-get update
sudo apt-get install default-jre-headless -y
```

**2. Download and unzip Keycloak:**

Install the latest version in /opt, extract it and rename it to keycloak:
```
cd /opt
sudo wget https://downloads.jboss.org/keycloak/11.0.3/keycloak-11.0.3.tar.gz
sudo tar -xvzf keycloak-11.0.3.tar.gz
sudo mv keycloak-11.0.3 keycloak
```

**3. Create user and group for keycloak**

Keycloak should not be run as a root user. So create a group *keycloak* and add the new user *keycloak* to this group:
```
sudo groupadd keycloak
sudo useradd -r -g keycloak -d /opt/keycloak -s /sbin/nologin keycloak
```
