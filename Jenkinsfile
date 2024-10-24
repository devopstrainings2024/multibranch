pipeline
{
       agent any
       stages
       {
         stage("contdownload")
         { 
          steps
          {
          git branch: 'dev1', url: 'https://github.com/devopstrainings2024/multibranch.git'
          }
         }
        stage("contbuild")
        { 
        steps
        {
        sh 'mvn package'
        }
        }
        stage("contdepl")
        { 
         steps
         {
deploy adapters: [tomcat9(credentialsId: '8d43ff57-0e8c-48ad-992f-9dcea00a76b2', path: '', url: 'http://172.31.17.24:8080')], contextPath: 'testdev1', war: '**/*.war'
          }
        }
      }
}
