node {

 stage('clone git repo'){

 git 'https://github.com/Kura2023/Jmeter_Script.git'
 }

 

 stage("configure") {

        bat "mkdir $WORKSPACE/$BUILD_NUMBER/"

    }

 

 stage('run test'){

 bat "mkdir /tmp/reports"

 bat "cd C:/Users/rkura/Documents/apache-jmeter-5.5/bin"

      bat "jmeter -Jjmeter.save.saveservice.output_format=xml

          -n -t app/C:/Users/rkura/Documents/Performance_Testing/Task2/Add_To_Cart.jmx

            -l C:/Users/rkura/Documents/Performance_Testing/Task2/Report/report.jtl"

 }

 

 stage('publish results'){

 bat "mv /tmp/reports/* $WORKSPACE/$BUILD_NUMBER/"

 archiveArtifacts artifacts: '$WORKSPACE/$BUILD_NUMBER/report.jtl, $WORKSPACE/$BUILD_NUMBER/HtmlReport/index.html'

    } 

  }

}
