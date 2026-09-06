pipeline
{
    agent any

    environment
    {
        DIRECTORY_PATH = "/var/lib/jenkins/workspace/7.1C-CI-Pipeline"
    }

    stages
    {
        stage("Build")
        {
            steps
            {
                echo "Build Section:"
                echo "Fetching source code from: ${DIRECTORY_PATH}"
                echo "Compiling and packaging source code with Maven"
            }
        }
        stage("Unit and Integration Tests")
        {
            steps
            {
                echo "Unit and Integration Tests Section:"
                echo "Running JUnit for unit tests and  Selenium for integration tests"
            }
        }
        stage("Code Analysis")
        {
            steps
            {
                echo "Code Analysis Section:"
                echo "Using SonarQube for static code analysis"
            }
        }
        stage("Security Scan")
        {
            steps
            {
                echo "Security Scan Section:"
                echo "Using the OWASP ZAP DAST tool to find vulnerabilities during runtime"
            }
        }
        stage("Deploy to Staging")
        {
            steps
            {
                echo "Deploy to Staging Section:"
                echo "Using AWS EC2 with Ansible for starting servers, databases, and deploying the application to the staging servers"
            }
        }
        stage("Integration Tests on Staging")
        {
            steps
            {
                echo "Integration Tests on Staging Section:"
                echo "Using Selenium to perform integration tests on the staging branch"
            }
        }
        stage("Deploy to Production")
        {
            steps
            {
                echo "Deploy to Production Section:"
                echo "Using AWS EC2 with Ansible to start servers, databases, and deploying the application to be accessible from the internet"
                echo "The application is complete and live!"
            }
        }
    }
}