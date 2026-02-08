pipeline {
    agent{
        node 'slave1'
    }
    environment{
        REGION='us-east-1'
        PROJECT='roboshop'
    }
    parameters: {
        string(name: 'image_tag')
        string(name: 'deploy_to', choices: ['dev', 'test', 'prod'], description: 'Environment')
    }
    stages{
        stage('Print Parmateres'){
            steps{
                script{
                    sh """
                        echo "Deploying version: ${params.image_tag}"
                        echo "Target environment: ${params.deploy_to}"
                    """
                }
            }
        }
        // stage('Deploy'){
        //     steps{
        //         script{
        //             withAWS(credentials: 'aws-creds', region: 'us-east-1') {
        //                 sh """
        //                     aws eks update-kubeconfig --name ${PROJECT} --region ${REGION}       
        //                     echo "Deploy"

        //                     kubectly apply -f manifest.yaml
        //                     helm install releasename chartname
        //                     helm upgrade --install catalogue catalogue 


        //                 """
        //             }

        //         }
        //     }
        // }
    }
}                    

