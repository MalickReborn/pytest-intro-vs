the Project is about showing a basic pipeline process using Jenkins CI/CD
first we forked the project 
Our plan was to use a docker container as our host for the jenkins server

these are the following steps of our test 
- build the container with a jenkins docker image hosted on dockerhub as:
docker run -p 8081:8080 -p 50000:50000 jenkins/jenkins 
(We opted for localhost port 8081 rather than 8080 for convenience as we have our own localhost jenkins set up ont this sport.)
- use the password given following installation to made the different steps of accessing , signing up, and adding plugins to the jenkins workspace

- enter in the container and install python3 and other modules (pip , pytest...)
- chose a nae for the pipeline
-  a description, chose the project as a github project add the github repo address.
-  pick scm as the way and pick up the jenkinsfile as reference since it's the common practice and we can avoid some steps as checkout ang gitbranch.
-  after recordind the settings , get back to the repo branch you want to work on. add a file called "Jenkinsfile" and write the script into the file and save it
- you can then run the build
- jenkins will make an automatic checkout, build and test of the app.
  
