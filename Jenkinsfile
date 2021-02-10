#!/groovy
@Library('cx-jenkins-pipeline-kit') _


pipeline {
    agent { node { label 'install02' } }
    parameters {
       
        choice(name: 'pool', choices: ['IAST-CI', 'IAST-Devlopers'], description: 'choose reource pool')

       
    }
    options {
        skipDefaultCheckout true
        timeout(time: 1, unit: 'HOURS') 
    }
   //
    stages {
        stage('Build') {
            steps {

                sh "ls -la"
                 echo "hello"
                 echo " resource pool is: ${pool}"

                // script{
                //     kit.Create_Vm_Terraform("adi-test3","SAST-IAST","4000","2","VMWARE","5 minutes","Auto","IAST-Developers","Lab","1000","1")
                // }
            } 
        }   
    } 
}


