def remote = [:]
remote.name = "ubuntu"
remote.host = "160.85.252.170"
remote.allowAnyHosts = true
remote.passphrase = "Mocolococo1!"
def localFilePath = "C:Users/SOLODE~1/Documents/HS20/cps/test_scenarios/Master-Thesis-CPS-SORTER/RQ1/Full Road/BeamNG/BeamNG_RF_1_5/beamng_risk_1.5"
def groupName = "solodezaldivar"
node{
        withCredentials([sshUserPrivateKey(credentialsId: 'jenkins', keyFileVariable: 'identity', passphraseVariable:'', usernameVariable: 'ubuntu')]){
        remote.user = ubuntu
        remote.identityFile = identity
        stage('Remote SSH') {
            
            //create folder on remote for github account
            // sshCommand remote: remote, command: "mkdir Documents/FuegoGroup/cps/test_scenarios/remoteTests/${groupName}"
            // //create outputfolder
            // sshCommand remote: remote, command: "mkdir Documents/FuegoGroup/cps/test_scenarios/remoteTests/${groupName}/output"
            //copy over scenarios from local to remote
            sshCommand local: remote, command: "scp -r ${localFilePath} ubuntu@160.85.252.170:~/Documents/FuegoGroup/cps/test_scenarios/remoteTests/${groupName}"
            //activate venv and run cps sorter on scenarios
            sshCommand remote: remote, command: "source Documents/FuegoGroup/cps/CPS-SORTER/venv/bin/activate\ncps_sorter run-model-eval -i ~/Documents/FuegoGroup/cps/test_scenarios/remoteTests/${groupName} -o ~/Documents/FuegoGroup/cps/test_scenarios/remoteTests/${groupName}/output"
            //copy remote output to local
            sshCommand remote: remote, command: "scp -r ubuntu@160.85.252.170:~/Documents/FuegoGroup/cps/test_scenarios/remoteTests/${groupName}/output ${localFilePath}"
        }
        // // activate virtual environment
        // sh '/venv/Scripts/activate'
        // // run cps on server with local machine scenarios
        // sh 'cps_sorter < run-model-eval -i Documents/FuegoGroup/cps/test_scenarios/Master-Thesis-CPS-SORTER/RQ1/Full\\ Road/BeamNG/BeamNG_RF_1_5/beamng_risk_1.5'
        // // copy output back to local

        // sh 'cat /output/file/location > /local/output/location'
    }
}