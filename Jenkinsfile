pipeline{
    agent{
        label{
            label 'built-in'
            customWorkspace '/mnt/copmposeplaybook'
        }
    }
    stages{
        stage('clean'){
            steps{
                echo "clean"
            }
        }
        stage('build'){
            steps{
                echo "build"
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
