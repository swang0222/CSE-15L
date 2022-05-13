
# Lab Report 3

## SSH Configuration

### .ssh/config file

![ssh/config file](screenshots-lab3/ssh-config.png)
Here, in the ~/.ssh folder, I created a config file

### File editor

![Edit file](screenshots-lab3/sublime.png)
I used sublime text 3 to edit the config file and set the alias to be ieng6

- Now ```ieng6``` is same as ```cs15lsp22alo@ieng6.ucsd.edu```

### Simplified ssh login

![ssh login](screenshots-lab3/login.png)
Now, I only need to type ```ssh ieng6``` to log in to the remote server

### scp command

![scp](screenshots-lab3/scp.png)
Same here, I just used the alias to do the scp command

---

## Setup Github Access

### Public key in Github

![public key](screenshots-lab3/public-key.png)
I have created a new public ssh key in my Github settings

### Public & Private key in Users

![Users](screenshots-lab3/users-keys.png)
The private key is still located in my ~/.ssh folder

### Git push

![Git push](screenshots-lab3/git-push.png)

1. ```git add <file>``` to add a changed file to be commited

2. ```git commit -m <message>``` to commit the change with a message

3. ```git push origin main``` to push the commit to the main branch

### [Link to the commit](https://github.com/swang0222/markdown-parser/commit/7b8fb0312e9203a17c9cc63caac585a2421cdc48)

---

## Copy whole directory

### scp -r command to copy the whole directory

![scp -r](screenshots-lab3/scp-r.png)
As shown, now the whole markdown-parser folder is copied to the remote server

### Running tests on ieng6

![run tests](screenshots-lab3/running.png)
```cd markdown-parser``` to change the working directory to markdown-parser to access the files inside it

```java
javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java
java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest
```

These are the two java commands used to run the junit tests

### Combine all commands in one line

![All in one line](screenshots-lab3/all-in-one.png)

The format ```ssh ieng6 "<commands>"``` allows us to run commands on server in one line and then quit the server

```java
/software/CSE/oracle-java-17/jdk-17.0.1/bin/javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java
/software/CSE/oracle-java-17/jdk-17.0.1/bin/java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest
```

Here I added a few words, ```/software/CSE/oracle-java-17/jdk-17.0.1/bin/``` because the java version in the remote server is not the same as what I have in my laptop, so I need to compile the java version on the remote server.
