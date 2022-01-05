pipeline {

  agent any

  environment {
    PATH = "/usr/local/bin:$PATH"
  }

  stages {
    stage("Vagrant VM init") {
      sh 'vagrant up'
    }
    stage('Build') {
      steps {
        sh 'vagrant ssh -c "xcodebuild -project bob.xcodeproj -scheme bob -sdk iphoneos archive -archivePath bob/build/bob.xcarchive -allowProvisioningUpdates | /usr/local/bin/xcpretty"'
      }
    }
  }
  post {
    always {
      sh 'vagrant halt'
      sh 'echo "Destroy"'
    }
  }
}
