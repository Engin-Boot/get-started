# Gating

The pom.xml integrates junit, jacoco and treats warnings as errors

In addition, [Cerberus](https://github.com/philips-software/cerberus) is a gating mechanism.
Its use is [illustrated here](https://github.com/aravind666/cerberus-workflow)

Example commands using Cerberus:

To get the jar from GitHub releases:

```sh
wget  https://github.com/philips-software/cerberus/releases/download/4/cerberus-4.0.jar
```

To check for duplication:

```sh
java -jar cerberus-4.0.jar CPD --files=./src --format=text --language=java --minimum-tokens=30
```

To find programming mistakes:

```sh
java -jar cerberus-4.0.jar FPM --files=./src --java-version=8 --language=java --rulesets="category/java/bestpractices.xml"
```
