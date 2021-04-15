pipeline {
  agent any
  stages {
    stage('download') {
      steps {
        echo 'download'
        sh 'curl -u sftp_flash:3VVeE0vL5eH3ZMykGm5h 192.168.10.15/ -O'
      }
    }

    stage('unzip') {
      steps {
        echo 'unzip'
        unzip '/var/jenkins_home/workspace/demo_master/multi_wallet_20181113.zip'
      }
    }

  }
}