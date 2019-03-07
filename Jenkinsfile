node {
    stage('Checkout') {
        checkout([$class: 'GitSCM', branches: [[name: 'master']], 
            doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], 
            userRemoteConfigs: [[credentialsId:'552163361b9ed5cd57139d0126b2095d69b11adb' , url: 'https://github.com/sandy99/TimeTable.git']]])
    }
    stage('Environment/Bundles Setup') {
        sh "Scripts/change_server.sh $server"
        sh "pod install --repo-update"
    }
    stage('Clean') {
        sh 'fastlane clean_xcode'
    }
    stage('Code Sign') {
        sh 'fastlane codesign method:"adhoc"'
    }
    stage('Create Build') {   
        sh 'fastlane create_build'
    }
}