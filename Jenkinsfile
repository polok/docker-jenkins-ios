pipeline {

  agent any

  stages {
    stage('Build') {
      steps {
        xcodebuild -project bob/bob.xcodeproj -scheme bob -sdk iphoneos archive -archivePath bob/build/bob.xcarchive -allowProvisioningUpdates | /usr/local/bin/xcpretty
      }
    }
  }
  post {
    always {
      sh 'echo "Destroy"'
    }
  }
}
