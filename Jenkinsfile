node('master') 
{
    stage('ContinuousDownload') 
    {
       git 'https://github.com/JyothiM-DEV/multibranch_1.git'
    }
    stage('continous build')
    {
	sh label: '', script: 'mvn package'
    }
    stage('continous deploy')
    {
	sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/m1_master/webapp/target/webapp.war ubuntu@172.31.5.129:/var/lib/tomcat8/webapps/testapp.war'
    }
    stage('ContinuousTesting')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
	sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/m1_master/testing.jar'
    }	
    stage('ContinuousDelivery')
    {
       sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/m1_master/webapp/target/webapp.war ubuntu@172.31.12.25:/var/lib/tomcat8/webapps/masterprodapp.war'
    }
}
