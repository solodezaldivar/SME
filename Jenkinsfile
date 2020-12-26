node {
    def remote = [:]
    remote.name = "ubuntu"
    remote.host = "160.85.252.170"
    remote.allowAnyHosts = true
    remote.user = user
    remote.passphrase = "Mocolococo1!"
    remote.identityFile = 'C:/Users/Solo de Zaldivar/.ssh/id_rsa'

    stage("SSH"){
        sshCommand remote: remote, command: "ls"
    }
    // withCredentials([sshUserPrivateKey(credentialsId: 'solod', keyFileVariable: 'identity', passphraseVariable: 'pass', usernameVariable: 'user')]){
    //     remote.user = user
    //     remote.identityFile = identity
    //     remote.passphrase = pass
    //     stage("SSH"){
    //         sshCommand remote: remote, command: "ls"

    //         // sshCommand remote: remote, command: 'source Documents/FuegoGroup/cps/CPS-SORTER/venv/bin/activate\ncps_sorter run-model-eval -i ~/Documents/FuegoGroup/cps/test_scenarios/remoteTests/solodezaldivar -o ~/Documents/FuegoGroup/cps/test_scenarios/remoteTests/solodezaldivar/output'
    //         // sshCommand remote: remote, command: 'scp -r ubuntu@160.85.252.170:/Documents/FuegoGroup/cps/test_scenarios/remoteTests/solodezaldivar/output Desktop/test/t1'
    //         // sshGet remote: remote, from: 'Documents/FuegoGroup/cps/test_scenarios/remoteTests/solodezaldivar/output', into: 'C:/Users/Solo de Zaldivar/Desktop/test/t1', override:true
    //         // sshCommand remote: remote, command: 'scp -r ubuntu@160.85.252.170:~/Documents/FuegoGroup/cps/test_scenarios/remoteTests/solodezaldivar/output "C:/Users/Solo de Zaldivar/Desktop/test/t1"'
    //     }

        // stage("Transfer Results"){
        //     // if find remoteTest/user
        //     // put scenarios
        //     // else create remoteTest/user
        //     when{sshCommand remote: remote, command: "-d '~/Documents/FuegoGroup/cps/test_scenarios/remoteTests/{solodezaldivar}'"}
        //     steps{
        //         echo "Directory exists." 
        //     }
            
        // }
    // }
}