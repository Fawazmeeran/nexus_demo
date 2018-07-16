pipeline {
  agent any
  stages {
    stage('Git Checkout') {
      steps {
        git(url: 'https://github.com/Fawazmeeran/nexus_demo.git', branch: 'master', poll: true)
        sh 'echo "checkout Done"'
      }
    }
    stage('Build') {
      steps {
        sh "'/Users/athena/Desktop/maven/apache-maven-3.5.3/bin/mvn' clean package"
      }
    }
    stage('Deploy') {
      steps {
        sh 'curl -u admin:admin -T /Users/athena/.jenkins/workspace/Nexuss_demo/target/artifactory-1.0-SNAPSHOT.jar "http://localhost:8081/artifactory/example-repo-local/artifactory-1.0-SNAPSHOT1.jar"'
      }
    }
  }
}
