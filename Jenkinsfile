pipeline {

  environment {
    PATH = "/usr/local/bin:$PATH"
  }

  agent {
    dockerfile true
  }

  stages {
    stage('Build') {
      steps {
        sh 'echo $PATH'
        sh 'docker --version'
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
