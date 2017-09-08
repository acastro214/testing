node ('!master') {
    withEnv(["WORKSPACE=${pwd()}"]) {
        stage ('make_dir') {
            sh('''cd $WORKSPACE
                mkdir dir1 dir2 dir3 dir4
                pwd
                ls -d
                ''')
        }
        stage ('find_dir'){
            println "find dir*"
            def dirList = sh(returnStdout: true, script: 'cd $WORKSPACE && ls -d dir*').split("\\n")
          //def dirUnderStashRoot = sh(returnStdout: true, script: 'cd $WORKSPACE && ls -d stash*').trim().split("\\r?\\n")
            println "dirList is: " + dirList
        }
    }
    step([$class: 'WsCleanup'])
}
