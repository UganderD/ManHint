node {
  stage('SCM CheckOut') {
git 'https://github.com/UganderD/ManHint.git'
    

}
stage('Compile-Package'){
//Get maven home path
def mvnHOME = tool name: 'M2_HOME', type: 'maven'

sh "${mvnHOME}/bin/mvn package"
}
  stage('Deploy-Tomcat'){
       sshagent(['Deploy-Tomcat']) {
       sh  'scp -o StrictHostKeyChecking=no  target/*.war ec2-user@54.254.205.101:/opt/apache-tomcat-9.0.16/webapps/'
}
       }
        }
		
		
