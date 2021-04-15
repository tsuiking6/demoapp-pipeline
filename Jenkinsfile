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
        unzip '/var/jenkins_home/workspace/demo_master/multi_wallet_20181113.zip'
      }
    }

    stage('DEV?') {
      steps {
        input 'Deploy DEV?'
      }
    }

    stage('LPT?') {
      steps {
        input 'Deploy LPT?'
      }
    }

    stage('FAT?') {
      steps {
        input 'Deploy FAT?'
      }
    }

  }
}