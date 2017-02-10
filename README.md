# groovy-gradle-project

## Groovy based project running on AWS Lightsail instance running Fedora

### Environment Setup (root)

1. yum upgrade to latest JDK (min. 1.7 but 1.8 preferred)
2. mkdir /opt/gradle && cd /opt/gradle
3. wget https://services.gradle.org/distributions/gradle-3.3-bin.zip (or latest)
4. unzip /opt/gradle gradle-3.3-bin.zip
5. ls /opt/gradle/gradle-3.3
6. export PATH=$PATH:/opt/gradle/gradle-3.3/bin (i.e., add to .bashrc)

### Commands

* gradle -v (version)
* gradle help
* gradle init --type groovy-library (gradle help --task init show other targets)

### Integrating into Jenkins

The gradle repositories and any branches/forks are integrated into Jenkins 
through the Multibranch Pipeline projects. The Jenkinsfile, defined in a separate
'jenkinsfile' repo, is added as a Git submodule symlinked to the root directory 
(the symlinks are preserved in Git). The project configuration is able to handle 
the gradle repo and submodule jenkinsfile repo clone.

#### Submodule Integration

* git clone gradle-repo gradle-dir
* cd gradle-dir
* git submodule add jenkinsfile-repo
* git add \*; git commit; git push origin branch

To clone the submodule repo

* git clone --recurse-submodules gradle-repo
* cd gradle-dir/jenkinfile && git pull origin master (if Jenkinsfile updated)

See _git submodule help_ for full commands 


### References

https://docs.gradle.org/current/userguide/installation.html
