pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'pwd'
sh 'sed \'s/\\.2/\\.\'${BUILD_NUMBER}\'/g\' ./debian/changelog > ./debian/x.txt'
sh 'cp ./debian/x.txt ./debian/changelog'
sh 'echo "#!/bin/bash \
cd /root; apt-get install -y npm ;git-buildpackage --git-ignore-new --git-ignore-branch; cp ../*.deb ." > install.sh'
sh 'chmod 755 install.sh'
sh 'sudo /root/install.sh'
      }
    }
  }
}
