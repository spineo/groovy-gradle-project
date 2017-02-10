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

### References

https://docs.gradle.org/current/userguide/installation.html
