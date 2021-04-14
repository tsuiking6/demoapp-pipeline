pipeline {
  agent any
  stages {
    stage('download') {
      steps {
        echo 'download'
        sh 'curl --insecure sftp://sftp_flash:3VVeE0vL5eH3ZMykGm5h@192.168.10.15/data/abgintegration/20181113/multi_wallet_20181113.zip --output /var/jenkins_home/workspace/demo/multi_wallet_20181113.zip'
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