# maven-lambda-layer

An AWS Lambda layer that includes: git, java, maven.

Layer ARN:

arn:aws:lambda:us-east-1:833477537704:layer:mavengitjava:4




zip -yr ../layer.zip .

aws s3 cp ../layer3.zip s3://mavenlambdalayer

Examples:

* execSync('export GIT_EXEC_PATH=/opt/lib/git-core && cd /tmp && /opt/lib/git clone ' + repo)

* execSync('export JAVA_HOME=/opt/lib/jvm/java-1.8.0-openjdk-1.8.0.265.b01-1.lambda2.0.1.x86_64 && export PATH=${PATH}:/opt/lib/jvm/java-1.8.0-openjdk-1.8.0.265.b01-1.lambda2.0.1.x86_64/bin && export M2_HOME=/opt/lib/apache-maven-3.0.5 && export PATH=${M2_HOME}/bin:${PATH} && ' + 'cd ' + path + ' && mvn -v', { stdio: 'ignore' })


