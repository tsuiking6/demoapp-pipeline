pipeline {
  agent any
  stages {
    stage('Bulid') {
      steps {
        echo 'Build demo-app'
        sh 'sh run_build_script.sh'
      }
    }

    stage('Linux Tests Stage') {
      parallel {
        stage('Linux Tests Stage') {
          steps {
            echo 'Run Linux tests'
            sh 'sh run_linux_tests.sh'
          }
        }

        stage('Windows Tests Stage') {
          steps {
            echo 'Run Windows tests'
          }
        }

      }
    }

    stage('Deploy Staging') {
      steps {
        echo 'Deploy to staging environment '
        input 'Ok to deploy to production? '
      }
    }

    stage('Deploy a Production') {
      steps {
        echo 'Deploy to Prod '
      }
    }

  }
  post {
    always {
      archiveArtifacts(artifacts: 'target/demoapp.jar', fingerprint: true)
    }

    failure {
      mail(to: 'ci-team@example.com', subject: "Failed Pipeline ${currentBuild.fullDisplayName}", body: " For details about the failure, see ${env.BUILD_URL}")
    }

  }
}