#!/groovy
@Library('cx-jenkins-pipeline-kit') _


pipeline {
    agent { node { label 'install02' } }
    parameters {
       
        choice(name: 'pool', choices: ['IAST-Devlopers','IAST-CI'], description: 'choose reource pool')

       
    }
    options {
        skipDefaultCheckout true
        timeout(time: 1, unit: 'HOURS') 
        timestamps()
    }
   //
    stages {
        stage('create IAST manager') {
            steps {
                script{
                    kit.Create_Vm_Terraform("adi-test-${BUILD_NUMBER}","SAST-IAST","4000","2","VMWARE","5 minutes","Auto","IAST-Developers","Lab","1000","1")
                }
            } 
        }   
    } 
    post { 
        always { 
            script{
            kit.Delete_Virtual_Machine_Terraform("adi-test-${BUILD_NUMBER}")
            }
            cleanWs()
        }
    }
}


