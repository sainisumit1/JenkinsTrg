pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Test') {
      steps {
        sh 'sudo mvn test'
        sh 'sudo rm -fr ./target'
        sh '''echo "Line1..."
echo "Line2..."'''
      }
    }
    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests package'
      }
    }
    stage('Deploy') {
      steps {
        sh '''sudo cp -p ./target/SampleJava1.war /var/lib/tomcat8/webapps/abhi-bo1.war
'''
        sh 'sudo rm -fr *'
      }
    }
  }
}