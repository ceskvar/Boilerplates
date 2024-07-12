# Docker-compose boilerplates

run jenkins:
```
docker-compose -f jenkins-docker-compose.yml up -d
```
Now point a web browser at port 8080 on your host system. You’ll see the unlock page.
The page tells you to find the initial password in a log file, but Jenkins prints the initial password to standard output too. 
So, you can retrieve it from the Docker log.

```
docker logs jenkins | less
```

Look for a block enclosed with six lines of asterisks like this:

```
*************************************************************
*************************************************************
*************************************************************
 
Jenkins initial setup is required. An admin user has been created and a password generated.
Please use the following password to proceed to installation:
 
c061b679107a4893b5383617729b5c6a
 
This may also be found at: /var/jenkins_home/secrets/initialAdminPassword
 
*************************************************************
*************************************************************
*************************************************************
```