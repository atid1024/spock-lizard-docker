pipeline {
  agent any
  stages {
    stage('Log Tool Version /Shell Script') {
      parallel {
        stage('Log Tool Version /Shell Script') {
          steps {
            sh '''mvn --version
git --version
java --version'''
          }
        }

        stage('Check the POM') {
          steps {
            fileExists 'pom.xml'
          }
        }

      }
    }

    stage('Build with Maven') {
      steps {
        sh 'mvn compile test package'
      }
    }

    stage('Post Build Steps') {
      steps {
        writeFile(file: 'atid.txt', text: 'Hey it worked!!!')
      }
    }

  }
}