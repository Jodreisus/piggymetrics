pipeline {
  agent {
    docker {
      image 'maven:3-jdk-8'
      args '-v /root/.m2:/root/.m2'
    }

  }
  stages {
    stage('Build Stage') {
      steps {
        echo 'Starting build'
        sh 'mvn install -DskipTests=true -Dmaven.javadoc.skip=true -B -V'
        echo 'Build done'
      }
    }

    stage('Testing') {
      steps {
        echo 'Starting unit tests'
        sh 'mvn test -B'
        echo 'Unit tests done'
      }
    }

  }
}