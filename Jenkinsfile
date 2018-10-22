pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''pwd
sed \'s/\\.2/\\.\'${BUILD_NUMBER}\'/g\' ./debian/changelog > ./debian/x.txt
cp ./debian/x.txt ./debian/changelog
echo "#!/bin/bash
cd /root; apt-get install -y npm ;git-buildpackage --git-ignore-new --git-ignore-branch; cp ../*.deb ." > install.sh'''
      }
    }
  }
}