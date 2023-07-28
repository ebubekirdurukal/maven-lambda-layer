# Git-Java-Maven Lambda Layer

This is an AWS Lambda layer that includes: git, java, maven. Convenient in case you want to be able to clone and compile java code in a nodejs function env.

### Layer ARN:

arn:aws:lambda:us-east-1:833477537704:layer:mavengitjava:4

### How to create your own layer

Download, compress and upload to your own bucket:

zip -yr ../layer.zip .

aws s3 cp ../layer.zip s3://yourownbucket

Then, select your bucket in aws lambda layers option

### Nodejs function examples:

```javascript
execSync('export GIT_EXEC_PATH=/opt/lib/git-core && cd /tmp && /opt/lib/git clone ' + repo)

execSync('export JAVA_HOME=/opt/lib/jvm/java-1.8.0-openjdk-1.8.0.265.b01-1.lambda2.0.1.x86_64 && export PATH=${PATH}:/opt/lib/jvm/java-1.8.0-openjdk-1.8.0.265.b01-1.lambda2.0.1.x86_64/bin && export M2_HOME=/opt/lib/apache-maven-3.0.5 && export PATH=${M2_HOME}/bin:${PATH} && ' + 'cd ' + path + ' && mvn -v', { stdio: 'ignore' })
```


