node{
    stage('Checkout/Build') {
        
        // Checkout files.
        checkout([
            $class: 'GitSCM',
            branches: [[name: 'master']],
            doGenerateSubmoduleConfigurations: false,
            extensions: [], submoduleCfg: [],
            userRemoteConfigs: [[
                name: 'github',
                url: 'https://github.com/sandy99/TimeTable.git'
                ]]
            ])
        
        // clean project
       sh 'xcodebuild clean -project "TimeTable.xcodeproj" -scheme "TimeTable"'
       // build project
       sh 'xcodebuild -scheme "TimeTable" -configuration "Release"'
    }
}


