# maven-first
the first maven project
# I refered the website: https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html

# How to run/dev your respository using github codespace?
1. **Create a new repository on GitHub:**
- Click on the '+' icon on the top-right corner of GitHub, and select "New repository".
- Give your repository a name, description and initialize it with a README file.
- Click on "Create repository".

2. **Open this repository in GitHub Codespaces:**  
https://github.com/features/codespaces

- Navigate to your newly created repository.
- Click on the green "Code" button.
- In the dropdown, under "Open with", click "Open with Codespaces".
- Then, click on the "+ New codespace" button.

# got the following error while executing the mvn package command:
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-compiler-plugin:3.8.0:compile (default-compile) on project my-app: Compilation failure: Compilation failure: 
[ERROR] Source option 7 is no longer supported. Use 8 or later.
[ERROR] Target option 7 is no longer supported. Use 8 or later.

Bing的回答。您在执行mvn package命令时遇到了一个编译错误，提示您使用的源代码和目标代码的版本过低，不再被支持。这个问题的原因是您的pom.xml文件中没有指定maven-compiler-plugin的配置，导致它使用了默认的版本，即1.7，而您的Java环境可能是更高的版本，比如1.8或以上。为了解决这个问题，您需要在您的pom.xml文件中添加以下的代码，指定您想要使用的源代码和目标代码的版本，比如1.812：
```
XML
<properties>
    <maven.compiler.source>1.8</maven.compiler.source>
    <maven.compiler.target>1.8</maven.compiler.target>
</properties>
```


添加完这段代码后，您可以再次尝试执行mvn package
