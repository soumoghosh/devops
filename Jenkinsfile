pipeline {
  agent any
  stages {
    stage('code collection') {
      steps {
        git(url: 'https://github.com/soumoghosh/student.git', changelog: true, poll: true, branch: 'master')
      }
    }

    stage('compile') {
      steps {
        sh '''mvn clean
mvn compile'''
      }
    }

    stage('test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('package') {
      steps {
        sh 'mvn package'
      }
    }

  }
}