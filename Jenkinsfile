pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        echo 'Checkout'
      }
    }

    stage('SonarQub Analysis') {
      steps {
        echo 'Static code analysis'
      }
    }

    stage('Build') {
      steps {
        echo 'Build the code'
      }
    }

    stage('Unit Test') {
      steps {
        echo 'Unit testing'
      }
    }

    stage('QA Deployment') {
      steps {
        echo 'QA deployment'
      }
    }

    stage('QA Test') {
      parallel {
        stage('QA Tests') {
          steps {
            echo 'Run tests'
          }
        }

        stage('Integration Test') {
          steps {
            echo 'Integration testing'
          }
        }

        stage('Functional Test') {
          steps {
            echo 'Functional testing'
          }
        }

      }
    }

    stage('UAT Deployment') {
      steps {
        echo 'UAT deployment'
      }
    }

    stage('UAT Test') {
      parallel {
        stage('UAT Test') {
          steps {
            echo 'UAT testing'
          }
        }

        stage('Integration Test') {
          steps {
            echo 'Integration testing'
          }
        }

        stage('Functional Test') {
          steps {
            echo 'Functional testing'
          }
        }

      }
    }

    stage('PP Deployment') {
      steps {
        input(message: 'Do you want to promote in Pre-prod?', ok: 'Yes')
      }
    }

    stage('PP Test') {
      parallel {
        stage('PP Test') {
          steps {
            echo 'Pre-prod testing'
          }
        }

        stage('Integration Test') {
          steps {
            echo 'Integration testing'
          }
        }

        stage('Smoke Test') {
          steps {
            echo 'Smoke testing'
          }
        }

      }
    }

    stage('Prod Deployment') {
      steps {
        input(message: 'Do you want to promote in Prod', ok: 'Yes')
      }
    }

    stage('Smoke Test') {
      steps {
        echo 'Smoke Test'
      }
    }

    stage('Notification') {
      steps {
        echo 'Send notification to the team'
      }
    }

  }
}