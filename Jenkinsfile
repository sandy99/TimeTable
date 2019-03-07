node('iOS Node') {
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
        
        // Build project
        sh 'xcodebuild -scheme "TimeTable" -configuration "Debug"'
    }
}