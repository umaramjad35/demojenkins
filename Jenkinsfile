pipeline{
    agent{
        label "linux"
    }
    environment{
        name = 'umar'
    }
    parameters{
        string(name: 'person', defaultValue: 'umar amjad', description:'What is your name?')
        choice(name: 'gender', choices: ['Male','Female'], description:'')
        booleanParam(name: 'Pakistani', defaultValue: true, description:'')
    }
    stages{
        stage("executing linux commands"){
            steps{
                echo "======== executing linux commands ========"
                sh ''' ls
                pwd
                date
                cal 2023
                '''
            }
            
        }
        stage("executing enviorments"){
            environment{
                username = 'amjad'
            }
            steps{
                echo "======== executing linux environmnet variables ========"
                sh 'echo "${username}"'
                sh 'echo "Your full name is ${person} ${username}"'
            }
            
        }
        stage("executing Parameters"){
            steps{
                echo "======== executing linux parameters ========"
                sh 'echo "The gender of the user is ${gender}"'
                sh 'echo "The user is  pakistani ${Pakistani}"'

            }
            
        }
        stage("executing deployment to test server"){
            steps{
                echo "======== executing deployment on Test server ========"
            }
            
        }
        stage("executing user input"){
            input{
                message "Should we continue?"
                ok "yes we should"
            }
            steps{
                echo "======== executing user input ========"
                echo "proceding to deploy on production"
                
            }
            
        }
        stage("executing deploment on production server"){
            steps{
                echo "======== executing deployment on production server ========"
                sh 'bash script.sh'
                echo "code deployed to Production successfully"
            }            
        }
    }
    post{
        always{
            echo "======== Post Actions Triggered ========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
