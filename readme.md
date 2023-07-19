the Project is about showing a basic pipeline process using Jenkins CI/CD
first we forked the project 
Our plan was to use a docker container as our host for the jenkins server

these are the following steps of our test 
- build the container with a jenkins docker image hosted on dockerhub as:

` docker run -p 8081:8080 -p 50000:50000 jenkins/jenkins `

[![Screenshot-from-2023-07-19-09-12-39.png](https://i.postimg.cc/Dy0VwcRj/Screenshot-from-2023-07-19-09-12-39.png)](https://postimg.cc/fkGqHYzm)
(We opted for localhost port 8081 rather than 8080 for convenience as we have our own localhost jenkins set up ont this sport.)
- use the password given following installation to made the different steps of accessing , signing up, and adding plugins to the jenkins workspace
[![Screenshot-from-2023-07-19-09-12-43.png](https://i.postimg.cc/sD7LX0wJ/Screenshot-from-2023-07-19-09-12-43.png)](https://postimg.cc/Whp8YSRD)
- enter in the container as a roo user and install python3 and other modules (pip , pytest...)
  docker exec -it -u 0 -cntainerid- bash
- configure yur jenkins pipline
          - chose a name for the pipeline
          -  a description, chose the project as a github project add the github repo address.
          -  pick scm as the way and pick up the jenkinsfile as reference since it's the common practice and we can avoid some steps as checkout ang gitbranch.
  [![Screenshot-from-2023-07-19-09-54-12.png](https://i.postimg.cc/5ywDZPrp/Screenshot-from-2023-07-19-09-54-12.png)](https://postimg.cc/D4wCGcnb)
  [![Screenshot-from-2023-07-19-09-54-18.png](https://i.postimg.cc/x8S4yvdm/Screenshot-from-2023-07-19-09-54-18.png)](https://postimg.cc/9RJbcqZX)
-  after recordind the settings , get back to the repo branch you want to work on. add a file called "Jenkinsfile" and write the script into the file and save it
  [![Screenshot-from-2023-07-19-09-54-36.png](https://i.postimg.cc/1tKp2wHw/Screenshot-from-2023-07-19-09-54-36.png)](https://postimg.cc/KkRkgKC8)
  [![Screenshot-from-2023-07-19-09-58-44.png](https://i.postimg.cc/YSKYSbDQ/Screenshot-from-2023-07-19-09-58-44.png)](https://postimg.cc/cvhr9MSJ)
  [![Screenshot-from-2023-07-19-09-58-51.png](https://i.postimg.cc/HxPLrLWF/Screenshot-from-2023-07-19-09-58-51.png)](https://postimg.cc/0MDv3PwC)
- you can then run the build and jenkins will make an automatic checkout, build and test of the app
  [![Screenshot-from-2023-07-19-10-07-04.png](https://i.postimg.cc/x8D1v4HP/Screenshot-from-2023-07-19-10-07-04.png)](https://postimg.cc/PpyHhKSL)

* We didn't set a wehook as it is not possible considering we worked on a localhost. but with a distant server it would have been the way , to guarantee every modification of the code will trigger the process.
  
