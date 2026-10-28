pipeline{
    agent{
        label{
            label 'built-in'
        }
    }
    stages{
        stage('clean'){
            steps{
                echo "clean"
                sh 'chmod 777 usingcompose.yaml'
                sh '''
				container=$(sudo docker ps -aq)
				if [ -n "${container}" ]
				then
				sudo docker stop ${container} && sudo docker rm ${container}
				fi
				sudo docker volume rm myvol || true
				'''
            }
        }
        stage('build'){
            steps{
            
                sh 'ansible-playbook usingcompose.yaml'
            }
        }
        stage('test'){
            steps{
                echo "test"
            } 
        }
        stage('deploy'){
            steps{
                echo "deploy"
            }
        }
    }
}
