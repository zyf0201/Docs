
## Install Java11 one macos

- Download jdk from this [link](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)

- install Java11

## Switching java version

- List all available version
```bash
/usr/libexec/java_home -V
```

output:
```text
Matching Java Virtual Machines (3):
    11.0.12 (x86_64) "Oracle Corporation" - "Java SE 11.0.12" /Library/Java/JavaVirtualMachines/jdk-11.0.12.jdk/Contents/Home
    1.8.151.12 (x86_64) "Oracle Corporation" - "Java" /Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home
    1.8.0_151 (x86_64) "Oracle Corporation" - "Java SE 8" /Library/Java/JavaVirtualMachines/jdk1.8.0_151.jdk/Contents/Home
/Library/Java/JavaVirtualMachines/jdk-11.0.12.jdk/Contents/Home
```

- Specify java version

for java8:

```bash
/usr/libexec/java_home -v1.8.0_151
```
output:
```text
/Library/Java/JavaVirtualMachines/jdk1.8.0_151.jdk/Contents/Home
```
--- 
for java11:
```
/usr/libexec/java_home -v11
```

output:
```text
/Library/Java/JavaVirtualMachines/jdk-11.0.12.jdk/Contents/Home
```

- Adding following aliases to .bash_profile

```bash
export JAVA_8_HOME=$(/usr/libexec/java_home -v1.8)
export JAVA_11_HOME=$(/usr/libexec/java_home -v11)

alias java8='export JAVA_HOME=$JAVA_8_HOME'
alias java11='export JAVA_HOME=$JAVA_11_HOME'
```

- Defaule to java11

```bash
java11
java -version
```

- Switching to java8
```bash
java8
java -version
```



