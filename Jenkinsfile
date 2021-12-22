pipeline {

  agent {
    dockerfile true
  }

  environment {
    PATH = "/usr/local/bin:$PATH"
  }

  stages {
    stage('Build') {
      steps {
        sh 'echo $PATH'
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
