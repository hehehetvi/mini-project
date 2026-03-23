PRAC 1 – Freestyle Project (GitHub)

Steps:
1. New Item → Freestyle Project
2. Source Code → Git → paste repo URL
3. Branch → */main
4. Build → Execute Windows batch

Command:
echo Build Successful
dir

PRAC 2 – Pipeline (Build + Test)

Steps:
1. New Item → Pipeline
2. Paste script

Code:
pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/your-repo.git'
            }
        }
        stage('Build') {
            steps {
                echo "Build running"
            }
        }
        stage('Test') {
            steps {
                echo "Tests PRAC 4A – Pipeline Scheduling

Steps:
1. Pipeline job
2. Build Triggers → Build periodically

Cron:
H/2 * * * *

Code:
pipeline {
    agent any
    stages {
        stage('Auto') {
            steps {
                echo "Running automatically"
            }
        }
    }
}




PRAC 4A – Pipeline Scheduling

Steps:
1. Pipeline job
2. Build Triggers → Build periodically

Cron:
H/2 * * * *

Code:
pipeline {
    agent any
    stages {
        stage('Auto') {
            steps {
                echo "Running automatically"
            }
        }
    }
}




PRAC 4B – Freestyle Scheduling

Steps:
1. Freestyle job
2. Build periodically

Cron:
H/2 * * * *

Command:
echo Running automatically
date /T
time /T





PRAC 4C – Parameterized Pipeline

Code:
pipeline {
    agent any

    parameters {
        string(name: 'USERNAME', defaultValue: 'Student')
    }

    triggers {
        cron('H/2 * * * *')
    }

    stages {
        stage('Greet') {
            steps {
                echo "Hello ${params.USERNAME}"
            }
        }
    }
}




PRAC 5A – Maven Project

Steps:
1. Freestyle job
2. Add Git repo
3. Build → Invoke Maven

Goal:
clean install

Post Build:
target/*.jar




PRAC 5B – Ant Project

Steps:
1. Freestyle job
2. Add Git repo
3. Build → Invoke Ant

Target:
clean jar

Archive:
dist/*.jar




PRAC 6 – Docker Basic Commands

Check:
docker --version

Pull:
docker pull hello-world

Run:
docker run hello-world

Apache:
docker run -d -p 8082:80 httpd

Nginx:
docker run -d -p 8083:80 nginx

Python:
docker run -it PRAC 6B – Static Website (Dockerfile)

index.html:
<h1>Hello from Docker!</h1>

Dockerfile:
FROM httpd:latest
COPY index.html /usr/local/apache2/htdocs/
EXPOSE 80

Commands:
docker build -t myimage .
docker run -d -p 8085:80 myimage

Open:
http://localhost:PRAC 6C – Dynamic Website (PHP Form)

index.html:
<!DOCTYPE html>
<html>
<body>
<form action="submit.php" method="post">
<input type="text" name="username">
<input type="submit">
</form>
</body>
</html>

submit.php:
<?php
$name = $_POST['username'];
echo "Hello $name";
?>

Dockerfile:
FROM php:8.2-apache
COPY . /var/www/html/
EXPOSE 80

Commands:
docker build -t form-website .
docker run -d -p 8085:80 form-website

Open:
http://localhost:LAST MINUTE FIX

If Jenkins fails:
echo Hello

If Docker fails:
docker run hello-world


