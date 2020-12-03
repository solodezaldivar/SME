def remote = [:]
remote.name = "ubuntu"
remote.host = "160.85.252.170"
remote.allowAnyHosts = true
remote.passphrase = "Mocolococo1!"
node{
        withCredentials([sshUserPrivateKey(credentialsId: 'jenkins', keyFileVariable: 'identity', passphraseVariable:'', usernameVariable: 'ubuntu')]){
        remote.user = ubuntu
        remote.identityFile = identity
        stage('Remote SSH') {
            // sshCommand remote: remote, command: "'bash -s' < source Documents/FuegoGroup/cps/CPS-SORTER/venv/bin/activate\ncps_sorter run-model-eval -i Documents/FuegoGroup/cps/test_scenarios/Master-Thesis-CPS-SORTER/RQ1/Full\\ Road/BeamNG/BeamNG_RF_1_5/beamng_risk_1.5"
            sshCommand remote: remote, command: "source Documents/FuegoGroup/cps/CPS-SORTER/venv/bin/activate\ncps_sorter run-model-eval -i  < Documents/FuegoGroup/cps/test_scenarios/Master-Thesis-CPS-SORTER/RQ1/Full\\ Road/BeamNG/BeamNG_RF_1_5/beamng_risk_1.5"
                                                    // cat /output/file/location > /local/output/location"
        }
        // // activate virtual environment
        // sh '/venv/Scripts/activate'
        // // run cps on server with local machine scenarios
        // sh 'cps_sorter < run-model-eval -i Documents/FuegoGroup/cps/test_scenarios/Master-Thesis-CPS-SORTER/RQ1/Full\\ Road/BeamNG/BeamNG_RF_1_5/beamng_risk_1.5'
        // // copy output back to local

        // sh 'cat /output/file/location > /local/output/location'
    }
}