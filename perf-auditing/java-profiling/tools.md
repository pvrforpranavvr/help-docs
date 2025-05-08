## Open source profiling tools


### JDK Mission Control (JMC)

https://jdk.java.net/jmc/

### Java Flight Recorder (JFR)

https://docs.oracle.com/javacomponents/jmc-5-4/jfr-runtime-guide/run.htm

```
java -XX:StartFlightRecording=duration=60s,filename=recording.jfr -jar yourapp.jar

```

Using processId for already running app
```
jcmd <pid> JFR.start name=profile duration=1m filename=recording.jfr

```

To view recorded details use JMC

### Visual VM

https://visualvm.github.io/
