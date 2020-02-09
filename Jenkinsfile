node
{
    stage('one')
    {
        echo "stage one"
    }
    stage('CheckOut')
    {
     echo "env home:${env.JENKINS_HOME}"
     echo "job name:${env.JOB_NAME}"
   //  echo "Branch Selecd: ${Branch}"
     dir("/var/lib/jenkins/workspace/pull/master") {
            checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '2fcb29a1-6ef3-4f65-b46b-9966b1078bfa', url: 'https://github.com/reddysvvr/MyProject.git']]])
     }
     sh 'rm -r *@tmp'
    // sh "chmod 775 /var/lib/jenkins/workspace/test/${Branch}/file.sh"
     // sh "/var/lib/jenkins/workspace/test/${Branch}/file.sh"
     }
    stage('mail')
    {
        emailext body: 'build succeess', subject: 'hi', to: 'smallaiahhyd@gmail.com'
    }
}
