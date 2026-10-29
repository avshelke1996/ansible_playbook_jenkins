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
				sh '''
    sudo -u avi -- ansible-playbook \
      /home/avi/giiit/usingcompose.yaml \
      -i /etc/ansible/hosts
'''
                sh 'chmod 777 usingcompose.yaml'
                sh 'sudo docker stop s1_container || true'
				sh 'sudo docker rm s1_container || true'
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
