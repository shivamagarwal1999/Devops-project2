# Devops-project2

Problem Statement :

*Create a container image that has jenkins installed using Dockerfile. When we launch this image it should automatically start the jenkins service in the container.
*Create a chain of jobs which will help to fetch source code, start service, test service, notify the status and in case of failure it will have capability to launch new environment in less that a minute or may be in just 1 second.

Task Description :

To solve this problem we are going to build chain of jobs in the jenkins each job will have their particular task :

Job1 : This job will continuously monitor github and as soon as found any commit it will fetch all the content in that repository and will store in the work folder.

Job2 : This job will identify whether the uploaded files are of HTML or PHP and accordingly it will launch a container of corresponding language and also have the respective 
launguage interpreter. (eg. If code is of PHP, then jenkins should start the container that has PHP already installed and launch it and a have the interpreter of that language).

Job3 : We will use this job for testing our application.

Job4 : If job3 failed due to any reason it means that our website is failed so, we should notify our developer. So we will use jenkins plugin in this job to sent email to the developer.

Job5 : It is to monitor jobs which will see whether If container where app is running. fails due to any reason then this job should automatically start the container again.
