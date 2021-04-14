pipeline {
  agent any
  stages {
    stage('download') {
      steps {
        echo 'download'
        sh 'curl --insecure sftp://sftp_flash:3VVeE0vL5eH3ZMykGm5h@192.168.10.15/data/abgintegration/20181113/multi_wallet_20181113.zip --output /var/jenkins_home/workspace/demo_master/multi_wallet_20181113.zip'
      }
    }

    stage('unzip') {
      steps {
        echo 'unzip'
        sh 'unzip zipFile:\'http://192.168.170.163:8080/var/jenkins_home/workspace/demo_master/multi_wallet_20181113.zip\''
      }
    }

  }
}