pipeline {
  agent any
  stages {
    stage('download') {
      steps {
        echo 'download'
        sh 'curl --insecure sftp://sftp_flash:3VVeE0vL5eH3ZMykGm5h@192.168.10.15/'
        sh 'def dir = new File("/data/game_rule/")'
        sh 'dir.eachFileRecurse (FileType.FILES) { file ->list << file}'
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