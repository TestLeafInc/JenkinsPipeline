pipeline {
  agent any
  stages {
    stage('Dev') {
      steps {
        echo 'Dev Build'
      }
    }

    stage('QA') {
      steps {
        echo 'QA Build'
      }
    }

    stage('UI Automated Tests') {
      parallel {
        stage('UI Automated Tests') {
          steps {
            echo 'Selenium Executed'
          }
        }

        stage('API Tests') {
          steps {
            echo 'Rest Assured Tests'
          }
        }

        stage('Performance Tests') {
          steps {
            echo 'Gatling Tests'
          }
        }

      }
    }

    stage('Approval') {
      steps {
        input(message: 'Is All Tests Good?', id: '101')
      }
    }

  }
}