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
    
}
