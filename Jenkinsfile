pipeline {
   agent any

   stages {
      stage('Verify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
      stage('Docker Build') {
         steps {
            pwsh(script: 'docker images -a')
            pwsh(script: """
               cd C:\Windows\System32\config\systemprofile\AppData\Local\Jenkins\.jenkins\workspace\CursoDevOps\Voting App Pipeline\azure-vote
               docker images -a
               docker build -t jenkins-pipeline .
               docker images -a
               cd ..
            """)
         }
      }
   }
}
