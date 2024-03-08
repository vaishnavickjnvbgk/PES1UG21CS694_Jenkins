pipeline {
    // This line defines the agent where the pipeline will run. In this case, it will run on any available agent.
    agent any

    // This block defines the stages of the pipeline. A pipeline can have multiple stages, and each stage can have multiple steps.
    stages {
        // This stage is named "Clone repository". It has one step that checks out the code from a Git repository.
        //stage('Clone repository') {
            //steps {
                // This step uses the checkout() method to clone the code from the Git repository.
                // The following arguments are provided to the checkout() method:
                // * $class: 'GitSCM' - This specifies that the Git plugin will be used to clone the code.
                // * branches: [[name: '*/main']] - This tells the plugin to checkout the 'main' branch of the repository.
                // * userRemoteConfigs: [[url: 'https://github.com/Jatinsharma159/Jenkins.git']] - This specifies the URL of the Git repository.
                //checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/Jatinsharma159/Jenkins.git']]])
           // }
       // }

        // This stage is named "Build". It has two steps:
        // 1. build 'PES2UG19CS694-1' - This step is likely calling another Jenkins job or pipeline named 'PES2UG19CS694-1'.
        // 2. sh 'g++ main.cpp -o output' - This step builds the code using the g++ compiler. The 'main.cpp' file is compiled into an executable named 'output'.
        stage('Build') {
            steps {
                build 'PES1UG21CS694-1'
                sh 'g++ main.cpp -o output'
            }
        }

        // This stage is named "Test". It has one step that executes the compiled program named 'output'.
        stage('Test') {
            steps {
                sh './output'
            }
        }

        // This stage is named "Deploy". It has one step that prints the message "deploy" to the console.
        stage('Deploy') {
            steps {
                echo 'deplo'
            }
        }
    }

    // This block defines the post-conditions of the pipeline. The post block will be executed after all the stages have finished.
    post {
        // This block defines what to do if the pipeline fails.
        failure {
            // This step will print the message "Pipeline failed" to the console if the pipeline fails.
            error 'Pipeline failed'
        }
    }
}
