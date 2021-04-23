pipeline {
  agent any
  stages {
    stage('download') {
      steps {
        echo 'download'
        sh '''curl -s --insecure sftp://sftp_flash:3VVeE0vL5eH3ZMykGm5h@192.168.10.15/data/frontend-h5/${date}/ | \\
        grep -e \'^-\' | awk \'{ print $9 }\' | \\
        while read f; do \\
        curl --insecure sftp://sftp_flash:3VVeE0vL5eH3ZMykGm5h@192.168.10.15/data/frontend-h5/${date}/$f --output /var/jenkins_home/workspace/Gamerule/$f \\
        done'''
      }
    }

  }
}