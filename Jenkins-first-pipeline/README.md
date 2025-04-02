#Jenkins Pipeline to verify the working of Docker Slave configuration is Successfully executed!!!

Started by user Samyog Ghimire

Obtained Jenkins-first-pipeline/JenkinsFile from git https://github.com/SamyogGhimire/Jenkins-Projects

[Pipeline] Start of Pipeline

[Pipeline] stage

[Pipeline] { (Build)

[Pipeline] node

Running on Jenkins in /var/lib/jenkins/workspace/

first-jenkins-job

[Pipeline] {

[Pipeline] checkout

Selected Git installation does not exist. Using Default

The recommended git tool is: NONE

No credentials specified

Cloning the remote Git repository

Cloning repository https://github.com/SamyogGhimire/Jenkins-Projects

 > git init /var/lib/jenkins/workspace/first-jenkins-job # timeout=10

Fetching upstream changes from https://github.com/SamyogGhimire/Jenkins-Projects

 > git --version # timeout=10

 > git --version # 'git version 2.43.0'

 > git fetch --tags --force --progress -- https://github.com/SamyogGhimire/Jenkins-Projects +refs/heads/*:refs/remotes/origin/* # timeout=10

 > git config remote.origin.url https://github.com/SamyogGhimire/Jenkins-Projects # timeout=10

 > git config --add remote.origin.fetch +refs/heads/*:refs/remotes/origin/* # timeout=10

Avoid second fetch

 > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
Checking out Revision 94ba5f1a60b5275cc324ff3ae277dc05d7755cc6 (refs/remotes/origin/main)

 > git config core.sparsecheckout # timeout=10

 > git checkout -f 94ba5f1a60b5275cc324ff3ae277dc05d7755cc6 # timeout=10

Commit message: "First Jenkins pipeline"

First time build. Skipping changelog.

[Pipeline] withEnv

[Pipeline] {

[Pipeline] isUnix

[Pipeline] withEnv

[Pipeline] {

[Pipeline] sh

+ docker inspect -f . node:16-alpine

Error: No such object: node:16-alpine

[Pipeline] isUnix

[Pipeline] withEnv

[Pipeline] {

[Pipeline] sh

+ docker pull node:16-alpine

16-alpine: Pulling from library/node

7264a8db6415: Pulling fs layer

eee371b9ce3f: Pulling fs layer

93b3025fe103: Pulling fs layer

d9059661ce70: Pulling fs layer

d9059661ce70: Waiting

7264a8db6415: Verifying Checksum

7264a8db6415: Download complete

93b3025fe103: Verifying Checksum

93b3025fe103: Download complete

7264a8db6415: Pull complete

d9059661ce70: Verifying Checksum

d9059661ce70: Download complete

eee371b9ce3f: Verifying Checksum

eee371b9ce3f: Download complete

eee371b9ce3f: Pull complete

93b3025fe103: Pull complete

d9059661ce70: Pull complete

Digest: sha256:a1f9d027912b58a7c75be7716c97cfbc6d3099f3a97ed84aa490be9dee20e787

Status: Downloaded newer image for node:16-alpine
docker.io/library/node:16-alpine

[Pipeline] }

[Pipeline] // withEnv

[Pipeline] }

[Pipeline] // withEnv

[Pipeline] withDockerContainer

Jenkins does not seem to be running inside a container
$ docker run -t -d -u 126:128 -w /var/lib/jenkins/workspace/first-jenkins-job -v /var/lib/jenkins/workspace/first-jenkins-job:/var/lib/jenkins/workspace/first-jenkins-job:rw,z -v /var/lib/jenkins/workspace/first-jenkins-job@tmp:/var/lib/jenkins/workspace/first-jenkins-job@tmp:rw,z -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** -e ******** node:16-alpine cat

$ docker top d20ef633e2bca540db661f6861226a00c9654fddfeb6dfa000a63414251e7792 -eo pid,comm

[Pipeline] {

[Pipeline] script

[Pipeline] {

[Pipeline] sh

+ node --version

v16.20.2

[Pipeline] }

[Pipeline] // script

[Pipeline] }

$ docker stop --time=1 d20ef633e2bca540db661f6861226a00c9654fddfeb6dfa000a63414251e7792

$ docker rm -f --volumes d20ef633e2bca540db661f6861226a00c9654fddfeb6dfa000a63414251e7792

[Pipeline] // withDockerContainer

[Pipeline] }

[Pipeline] // withEnv

[Pipeline] }

[Pipeline] // node

[Pipeline] }

[Pipeline] // stage

[Pipeline] End of Pipeline

Finished: SUCCESS
