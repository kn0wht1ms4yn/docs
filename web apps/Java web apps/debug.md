### Tools
- JD-GUI - JAR decompiler
- Fernflower - JAR decompiler
- Gradle - build tool for JAVA (and other) applications

### Commands
| | |
| --- | --- |
| javac myFile.java | compile java code to .jar |
| remote debugging	| java -Xdebug -Xrunjdwp:transport=dt_socket,address=8000,server=y,suspend=y -jar myFIle.jar |
| | java -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 myFile.jar         |
| sudo update-java-alternatives --list | list installed java versions on this system |
| sup update-java-alternatives --set <path from command above> | tell system to use specific java version |

# Remote Debugging with VScode
- configure vs code to connect to the debugger

```
.vscode/
    launch.json
        {
            "version": "0.2.0",
            "configurations": [
                {
                    "type": "java",
                    "name": "Remote Debugging",
                    "request": "attach",
                    "hostName": "127.0.0.1", # ip address the debugger is running on from java debug command
                    "port": 8000 # port the debugger is running on from java debug command
                }
            ]
        }
```         
            
- start java with a debugger listening on port *address*

    `java -Xdebug -Xrunjdwp:transport=dt_socket,address=8000,server=y,suspend=y -jar myFIle.jar`