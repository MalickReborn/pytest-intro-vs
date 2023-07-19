pipeline{
  agent any
  stages{
      stage("Build"){
        steps {
          sh 'python3 ops.py'
              }
        }
      stage("Test"){
        steps {
          sh 'python3 -m pytest'
              }
        }
    }
}
