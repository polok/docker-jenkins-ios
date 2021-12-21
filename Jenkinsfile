pipeline {
  agent {
    dockerfile true
    
    node {
      label 'macmini'
    }
  }
  stages {
    stage('Build') {
      steps {
        sh 'xcodebuild -project bob.xcodeproj -scheme bob -sdk iphoneos archive -archivePath bob/build/bob.xcarchive -allowProvisioningUpdates | /usr/local/bin/xcpretty'
      }
    }
  }
  post {
    always {
      sh 'echo "Destroy"'
    }
  }
}
