node('node') {

    try {

       stage 'Checkout'
       stage('Checkout'){

            checkout scm
          checkout scm
       }

       stage 'Test'
       stage('Test'){

            env.NODE_ENV = "test"
         env.NODE_ENV = "test"

            print "Environment will be : ${env.NODE_ENV}"
         print "Environment will be : ${env.NODE_ENV}"

            sh 'node -v'
            sh 'npm prune'
            sh 'npm install'
            sh 'npm test'
         sh 'node -v'
         sh 'npm prune'
         sh 'npm install'
         sh 'npm test'

       stage 'Build Docker'
       }

       stage('Build Docker'){

            sh './dockerBuild.sh'
       }

       stage('Deploy'){

       stage 'Deploy'
         echo 'Push to Repo'
         sh './dockerPushToRepo.sh'

            echo 'Push to Repo'
            sh './dockerPushToRepo.sh'
         echo 'ssh to web server and tell it to pull new image'
         sh 'ssh deploy@xxxxx.xxxxx.com running/xxxxxxx/dockerRun.sh'

            echo 'ssh to web server and tell it to pull new image'
            sh 'ssh deploy@xxxxx.xxxxx.com running/xxxxxxx/dockerRun.sh'
       }

       stage 'Cleanup'
       stage('Cleanup'){

            echo 'prune and cleanup'
            sh 'npm prune'
            sh 'rm node_modules -rf'
         echo 'prune and cleanup'
         sh 'npm prune'
         sh 'rm node_modules -rf'

            mail body: 'project build successful',
                        from: 'xxxx@yyyyy.com',
                        replyTo: 'xxxx@yyyy.com',
                        subject: 'project build successful',
                        to: 'yyyyy@yyyy.com'
         mail body: 'project build successful',
                     from: 'xxxx@yyyyy.com',
                     replyTo: 'xxxx@yyyy.com',
                     subject: 'project build successful',
                     to: 'yyyyy@yyyy.com'
       }

        }


    }
    catch (err) {

        currentBuild.result = "FAILURE"
