# Before
## TestAuxServices

```
[INFO] Scanning for projects...
[INFO]                                                                         
[INFO] ------------------------------------------------------------------------
[INFO] Building Apache Hadoop YARN NodeManager 3.3.0-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO] 
[INFO] --- maven-antrun-plugin:1.7:run (create-testdirs) @ hadoop-yarn-server-nodemanager ---
[INFO] Executing tasks

main:
[INFO] Executed tasks
[INFO] 
[INFO] --- hadoop-maven-plugins:3.3.0-SNAPSHOT:protoc (compile-protoc) @ hadoop-yarn-server-nodemanager ---
[INFO] No changes detected in protoc files, skipping generation.
[INFO] 
[INFO] --- maven-remote-resources-plugin:1.5:process (default) @ hadoop-yarn-server-nodemanager ---
[INFO] 
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ hadoop-yarn-server-nodemanager ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 26 resources
[INFO] Copying 2 resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:compile (default-compile) @ hadoop-yarn-server-nodemanager ---
[INFO] Compiling 8 source files to /home/joakim/hadoop/hadoop-yarn-project/hadoop-yarn/hadoop-yarn-server/hadoop-yarn-server-nodemanager/target/classes
[INFO] 
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ hadoop-yarn-server-nodemanager ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 8 resources
[INFO] Copying 2 resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:testCompile (default-testCompile) @ hadoop-yarn-server-nodemanager ---
[INFO] Compiling 1 source file to /home/joakim/hadoop/hadoop-yarn-project/hadoop-yarn/hadoop-yarn-server/hadoop-yarn-server-nodemanager/target/test-classes
[INFO] 
[INFO] --- maven-surefire-plugin:3.0.0-M1:test (default-test) @ hadoop-yarn-server-nodemanager ---
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running org.apache.hadoop.yarn.server.nodemanager.containermanager.TestAuxServices
[ERROR] Tests run: 26, Failures: 1, Errors: 0, Skipped: 3, Time elapsed: 2.301 s <<< FAILURE! - in org.apache.hadoop.yarn.server.nodemanager.containermanager.TestAuxServices
[ERROR] testRemoteAuxServiceClassPath[0](org.apache.hadoop.yarn.server.nodemanager.containermanager.TestAuxServices)  Time elapsed: 0.479 s  <<< FAILURE!
java.lang.AssertionError
	at org.junit.Assert.fail(Assert.java:86)
	at org.junit.Assert.assertTrue(Assert.java:41)
	at org.junit.Assert.assertTrue(Assert.java:52)
	at org.apache.hadoop.yarn.server.nodemanager.containermanager.TestAuxServices.testRemoteAuxServiceClassPath(TestAuxServices.java:345)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.junit.runners.model.FrameworkMethod$1.runReflectiveCall(FrameworkMethod.java:50)
	at org.junit.internal.runners.model.ReflectiveCallable.run(ReflectiveCallable.java:12)
	at org.junit.runners.model.FrameworkMethod.invokeExplosively(FrameworkMethod.java:47)
	at org.junit.internal.runners.statements.InvokeMethod.evaluate(InvokeMethod.java:17)
	at org.junit.internal.runners.statements.RunBefores.evaluate(RunBefores.java:26)
	at org.junit.internal.runners.statements.RunAfters.evaluate(RunAfters.java:27)
	at org.junit.runners.ParentRunner.runLeaf(ParentRunner.java:325)
	at org.junit.runners.BlockJUnit4ClassRunner.runChild(BlockJUnit4ClassRunner.java:78)
	at org.junit.runners.BlockJUnit4ClassRunner.runChild(BlockJUnit4ClassRunner.java:57)
	at org.junit.runners.ParentRunner$3.run(ParentRunner.java:290)
	at org.junit.runners.ParentRunner$1.schedule(ParentRunner.java:71)
	at org.junit.runners.ParentRunner.runChildren(ParentRunner.java:288)
	at org.junit.runners.ParentRunner.access$000(ParentRunner.java:58)
	at org.junit.runners.ParentRunner$2.evaluate(ParentRunner.java:268)
	at org.junit.runners.ParentRunner.run(ParentRunner.java:363)
	at org.junit.runners.Suite.runChild(Suite.java:128)
	at org.junit.runners.Suite.runChild(Suite.java:27)
	at org.junit.runners.ParentRunner$3.run(ParentRunner.java:290)
	at org.junit.runners.ParentRunner$1.schedule(ParentRunner.java:71)
	at org.junit.runners.ParentRunner.runChildren(ParentRunner.java:288)
	at org.junit.runners.ParentRunner.access$000(ParentRunner.java:58)
	at org.junit.runners.ParentRunner$2.evaluate(ParentRunner.java:268)
	at org.junit.runners.ParentRunner.run(ParentRunner.java:363)
	at org.apache.maven.surefire.junit4.JUnit4Provider.execute(JUnit4Provider.java:365)
	at org.apache.maven.surefire.junit4.JUnit4Provider.executeWithRerun(JUnit4Provider.java:273)
	at org.apache.maven.surefire.junit4.JUnit4Provider.executeTestSet(JUnit4Provider.java:238)
	at org.apache.maven.surefire.junit4.JUnit4Provider.invoke(JUnit4Provider.java:159)
	at org.apache.maven.surefire.booter.ForkedBooter.invokeProviderInSameClassLoader(ForkedBooter.java:384)
	at org.apache.maven.surefire.booter.ForkedBooter.runSuitesInProcess(ForkedBooter.java:345)
	at org.apache.maven.surefire.booter.ForkedBooter.execute(ForkedBooter.java:126)
	at org.apache.maven.surefire.booter.ForkedBooter.main(ForkedBooter.java:418)

[INFO] 
[INFO] Results:
[INFO] 
[ERROR] Failures: 
[ERROR]   TestAuxServices.testRemoteAuxServiceClassPath:345
[INFO] 
[ERROR] Tests run: 26, Failures: 1, Errors: 0, Skipped: 3
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 9.147 s
[INFO] Finished at: 2019-02-23T11:17:31+00:00
[INFO] Final Memory: 45M/646M
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-surefire-plugin:3.0.0-M1:test (default-test) on project hadoop-yarn-server-nodemanager: There are test failures.
[ERROR] 
[ERROR] Please refer to /home/joakim/hadoop/hadoop-yarn-project/hadoop-yarn/hadoop-yarn-server/hadoop-yarn-server-nodemanager/target/surefire-reports for the individual test results.
[ERROR] Please refer to dump files (if any exist) [date].dump, [date]-jvmRun[N].dump and [date].dumpstream.
[ERROR] -> [Help 1]
[ERROR] 
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR] 
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoFailureException
```

## TestContainer

```
[INFO] Scanning for projects...
[INFO]                                                                         
[INFO] ------------------------------------------------------------------------
[INFO] Building Apache Hadoop YARN NodeManager 3.3.0-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO] 
[INFO] --- maven-antrun-plugin:1.7:run (create-testdirs) @ hadoop-yarn-server-nodemanager ---
[INFO] Executing tasks

main:
[INFO] Executed tasks
[INFO] 
[INFO] --- hadoop-maven-plugins:3.3.0-SNAPSHOT:protoc (compile-protoc) @ hadoop-yarn-server-nodemanager ---
[INFO] No changes detected in protoc files, skipping generation.
[INFO] 
[INFO] --- maven-remote-resources-plugin:1.5:process (default) @ hadoop-yarn-server-nodemanager ---
[INFO] 
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ hadoop-yarn-server-nodemanager ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 26 resources
[INFO] Copying 2 resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:compile (default-compile) @ hadoop-yarn-server-nodemanager ---
[INFO] Compiling 8 source files to /home/joakim/hadoop/hadoop-yarn-project/hadoop-yarn/hadoop-yarn-server/hadoop-yarn-server-nodemanager/target/classes
[INFO] 
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ hadoop-yarn-server-nodemanager ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 8 resources
[INFO] Copying 2 resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:testCompile (default-testCompile) @ hadoop-yarn-server-nodemanager ---
[INFO] Nothing to compile - all classes are up to date
[INFO] 
[INFO] --- maven-surefire-plugin:3.0.0-M1:test (default-test) @ hadoop-yarn-server-nodemanager ---
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running org.apache.hadoop.yarn.server.nodemanager.containermanager.application.TestApplication
[INFO] Tests run: 10, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 5.191 s - in org.apache.hadoop.yarn.server.nodemanager.containermanager.application.TestApplication
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 10, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 11.521 s
[INFO] Finished at: 2019-02-23T11:18:47+00:00
[INFO] Final Memory: 41M/664M
[INFO] ------------------------------------------------------------------------
joakim@d8d4fbbe9b4c:~/hadoop/hadoop-yarn-project/hadoop-yarn/hadoop-yarn-server/hadoop-yarn-server-nodemanager$ mvn -Dtest=TestApplication test
[INFO] Scanning for projects...
[INFO]                                                                         
[INFO] ------------------------------------------------------------------------
[INFO] Building Apache Hadoop YARN NodeManager 3.3.0-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO] 
[INFO] --- maven-antrun-plugin:1.7:run (create-testdirs) @ hadoop-yarn-server-nodemanager ---
[INFO] Executing tasks

main:
[INFO] Executed tasks
[INFO] 
[INFO] --- hadoop-maven-plugins:3.3.0-SNAPSHOT:protoc (compile-protoc) @ hadoop-yarn-server-nodemanager ---
[INFO] No changes detected in protoc files, skipping generation.
[INFO] 
[INFO] --- maven-remote-resources-plugin:1.5:process (default) @ hadoop-yarn-server-nodemanager ---
[INFO] 
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ hadoop-yarn-server-nodemanager ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 26 resources
[INFO] Copying 2 resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:compile (default-compile) @ hadoop-yarn-server-nodemanager ---
[INFO] Compiling 8 source files to /home/joakim/hadoop/hadoop-yarn-project/hadoop-yarn/hadoop-yarn-server/hadoop-yarn-server-nodemanager/target/classes
[INFO] 
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ hadoop-yarn-server-nodemanager ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 8 resources
[INFO] Copying 2 resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:testCompile (default-testCompile) @ hadoop-yarn-server-nodemanager ---
[INFO] Nothing to compile - all classes are up to date
[INFO] 
[INFO] --- maven-surefire-plugin:3.0.0-M1:test (default-test) @ hadoop-yarn-server-nodemanager ---
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running org.apache.hadoop.yarn.server.nodemanager.containermanager.application.TestApplication
[INFO] Tests run: 10, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 5.385 s - in org.apache.hadoop.yarn.server.nodemanager.containermanager.application.TestApplication
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 10, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 11.778 s
[INFO] Finished at: 2019-02-23T11:19:08+00:00
[INFO] Final Memory: 41M/662M
[INFO] ------------------------------------------------------------------------
```

## TestApplication

```
[INFO] Scanning for projects...
[INFO]                                                                         
[INFO] ------------------------------------------------------------------------
[INFO] Building Apache Hadoop YARN NodeManager 3.3.0-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO] 
[INFO] --- maven-antrun-plugin:1.7:run (create-testdirs) @ hadoop-yarn-server-nodemanager ---
[INFO] Executing tasks

main:
[INFO] Executed tasks
[INFO] 
[INFO] --- hadoop-maven-plugins:3.3.0-SNAPSHOT:protoc (compile-protoc) @ hadoop-yarn-server-nodemanager ---
[INFO] No changes detected in protoc files, skipping generation.
[INFO] 
[INFO] --- maven-remote-resources-plugin:1.5:process (default) @ hadoop-yarn-server-nodemanager ---
[INFO] 
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ hadoop-yarn-server-nodemanager ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 26 resources
[INFO] Copying 2 resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:compile (default-compile) @ hadoop-yarn-server-nodemanager ---
[INFO] Compiling 8 source files to /home/joakim/hadoop/hadoop-yarn-project/hadoop-yarn/hadoop-yarn-server/hadoop-yarn-server-nodemanager/target/classes
[INFO] 
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ hadoop-yarn-server-nodemanager ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 8 resources
[INFO] Copying 2 resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:testCompile (default-testCompile) @ hadoop-yarn-server-nodemanager ---
[INFO] Nothing to compile - all classes are up to date
[INFO] 
[INFO] --- maven-surefire-plugin:3.0.0-M1:test (default-test) @ hadoop-yarn-server-nodemanager ---
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running org.apache.hadoop.yarn.server.nodemanager.containermanager.application.TestApplication
[INFO] Tests run: 10, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 5.35 s - in org.apache.hadoop.yarn.server.nodemanager.containermanager.application.TestApplication
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 10, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 11.708 s
[INFO] Finished at: 2019-02-25T11:15:45+00:00
[INFO] Final Memory: 41M/635M
[INFO] ------------------------------------------------------------------------
```

# After
## TestAuxServices

```
[INFO] Scanning for projects...
[INFO]                                                                         
[INFO] ------------------------------------------------------------------------
[INFO] Building Apache Hadoop YARN NodeManager 3.3.0-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO] 
[INFO] --- maven-antrun-plugin:1.7:run (create-testdirs) @ hadoop-yarn-server-nodemanager ---
[INFO] Executing tasks

main:
[INFO] Executed tasks
[INFO] 
[INFO] --- hadoop-maven-plugins:3.3.0-SNAPSHOT:protoc (compile-protoc) @ hadoop-yarn-server-nodemanager ---
[INFO] No changes detected in protoc files, skipping generation.
[INFO] 
[INFO] --- maven-remote-resources-plugin:1.5:process (default) @ hadoop-yarn-server-nodemanager ---
[INFO] 
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ hadoop-yarn-server-nodemanager ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 26 resources
[INFO] Copying 2 resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:compile (default-compile) @ hadoop-yarn-server-nodemanager ---
[INFO] Compiling 8 source files to /home/joakim/hadoop/hadoop-yarn-project/hadoop-yarn/hadoop-yarn-server/hadoop-yarn-server-nodemanager/target/classes
[INFO] 
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ hadoop-yarn-server-nodemanager ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 8 resources
[INFO] Copying 2 resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:testCompile (default-testCompile) @ hadoop-yarn-server-nodemanager ---
[INFO] Compiling 3 source files to /home/joakim/hadoop/hadoop-yarn-project/hadoop-yarn/hadoop-yarn-server/hadoop-yarn-server-nodemanager/target/test-classes
[INFO] 
[INFO] --- maven-surefire-plugin:3.0.0-M1:test (default-test) @ hadoop-yarn-server-nodemanager ---
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running org.apache.hadoop.yarn.server.nodemanager.containermanager.TestAuxServices
[ERROR] Tests run: 26, Failures: 1, Errors: 0, Skipped: 3, Time elapsed: 2.561 s <<< FAILURE! - in org.apache.hadoop.yarn.server.nodemanager.containermanager.TestAuxServices
[ERROR] testRemoteAuxServiceClassPath[0](org.apache.hadoop.yarn.server.nodemanager.containermanager.TestAuxServices)  Time elapsed: 0.549 s  <<< FAILURE!
java.lang.AssertionError
	at org.junit.Assert.fail(Assert.java:86)
	at org.junit.Assert.assertTrue(Assert.java:41)
	at org.junit.Assert.assertTrue(Assert.java:52)
	at org.apache.hadoop.yarn.server.nodemanager.containermanager.TestAuxServices.testRemoteAuxServiceClassPath(TestAuxServices.java:345)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.junit.runners.model.FrameworkMethod$1.runReflectiveCall(FrameworkMethod.java:50)
	at org.junit.internal.runners.model.ReflectiveCallable.run(ReflectiveCallable.java:12)
	at org.junit.runners.model.FrameworkMethod.invokeExplosively(FrameworkMethod.java:47)
	at org.junit.internal.runners.statements.InvokeMethod.evaluate(InvokeMethod.java:17)
	at org.junit.internal.runners.statements.RunBefores.evaluate(RunBefores.java:26)
	at org.junit.internal.runners.statements.RunAfters.evaluate(RunAfters.java:27)
	at org.junit.runners.ParentRunner.runLeaf(ParentRunner.java:325)
	at org.junit.runners.BlockJUnit4ClassRunner.runChild(BlockJUnit4ClassRunner.java:78)
	at org.junit.runners.BlockJUnit4ClassRunner.runChild(BlockJUnit4ClassRunner.java:57)
	at org.junit.runners.ParentRunner$3.run(ParentRunner.java:290)
	at org.junit.runners.ParentRunner$1.schedule(ParentRunner.java:71)
	at org.junit.runners.ParentRunner.runChildren(ParentRunner.java:288)
	at org.junit.runners.ParentRunner.access$000(ParentRunner.java:58)
	at org.junit.runners.ParentRunner$2.evaluate(ParentRunner.java:268)
	at org.junit.runners.ParentRunner.run(ParentRunner.java:363)
	at org.junit.runners.Suite.runChild(Suite.java:128)
	at org.junit.runners.Suite.runChild(Suite.java:27)
	at org.junit.runners.ParentRunner$3.run(ParentRunner.java:290)
	at org.junit.runners.ParentRunner$1.schedule(ParentRunner.java:71)
	at org.junit.runners.ParentRunner.runChildren(ParentRunner.java:288)
	at org.junit.runners.ParentRunner.access$000(ParentRunner.java:58)
	at org.junit.runners.ParentRunner$2.evaluate(ParentRunner.java:268)
	at org.junit.runners.ParentRunner.run(ParentRunner.java:363)
	at org.apache.maven.surefire.junit4.JUnit4Provider.execute(JUnit4Provider.java:365)
	at org.apache.maven.surefire.junit4.JUnit4Provider.executeWithRerun(JUnit4Provider.java:273)
	at org.apache.maven.surefire.junit4.JUnit4Provider.executeTestSet(JUnit4Provider.java:238)
	at org.apache.maven.surefire.junit4.JUnit4Provider.invoke(JUnit4Provider.java:159)
	at org.apache.maven.surefire.booter.ForkedBooter.invokeProviderInSameClassLoader(ForkedBooter.java:384)
	at org.apache.maven.surefire.booter.ForkedBooter.runSuitesInProcess(ForkedBooter.java:345)
	at org.apache.maven.surefire.booter.ForkedBooter.execute(ForkedBooter.java:126)
	at org.apache.maven.surefire.booter.ForkedBooter.main(ForkedBooter.java:418)

[INFO] 
[INFO] Results:
[INFO] 
[ERROR] Failures: 
[ERROR]   TestAuxServices.testRemoteAuxServiceClassPath:345
[INFO] 
[ERROR] Tests run: 26, Failures: 1, Errors: 0, Skipped: 3
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 10.089 s
[INFO] Finished at: 2019-02-25T11:22:40+00:00
[INFO] Final Memory: 45M/671M
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-surefire-plugin:3.0.0-M1:test (default-test) on project hadoop-yarn-server-nodemanager: There are test failures.
[ERROR] 
[ERROR] Please refer to /home/joakim/hadoop/hadoop-yarn-project/hadoop-yarn/hadoop-yarn-server/hadoop-yarn-server-nodemanager/target/surefire-reports for the individual test results.
[ERROR] Please refer to dump files (if any exist) [date].dump, [date]-jvmRun[N].dump and [date].dumpstream.
[ERROR] -> [Help 1]
[ERROR] 
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR] 
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoFailureException
```

## TestContainer
```
[INFO] Scanning for projects...
[INFO]                                                                         
[INFO] ------------------------------------------------------------------------
[INFO] Building Apache Hadoop YARN NodeManager 3.3.0-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO] 
[INFO] --- maven-antrun-plugin:1.7:run (create-testdirs) @ hadoop-yarn-server-nodemanager ---
[INFO] Executing tasks

main:
[INFO] Executed tasks
[INFO] 
[INFO] --- hadoop-maven-plugins:3.3.0-SNAPSHOT:protoc (compile-protoc) @ hadoop-yarn-server-nodemanager ---
[INFO] No changes detected in protoc files, skipping generation.
[INFO] 
[INFO] --- maven-remote-resources-plugin:1.5:process (default) @ hadoop-yarn-server-nodemanager ---
[INFO] 
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ hadoop-yarn-server-nodemanager ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 26 resources
[INFO] Copying 2 resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:compile (default-compile) @ hadoop-yarn-server-nodemanager ---
[INFO] Compiling 8 source files to /home/joakim/hadoop/hadoop-yarn-project/hadoop-yarn/hadoop-yarn-server/hadoop-yarn-server-nodemanager/target/classes
[INFO] 
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ hadoop-yarn-server-nodemanager ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 8 resources
[INFO] Copying 2 resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:testCompile (default-testCompile) @ hadoop-yarn-server-nodemanager ---
[INFO] Compiling 2 source files to /home/joakim/hadoop/hadoop-yarn-project/hadoop-yarn/hadoop-yarn-server/hadoop-yarn-server-nodemanager/target/test-classes
[INFO] 
[INFO] --- maven-surefire-plugin:3.0.0-M1:test (default-test) @ hadoop-yarn-server-nodemanager ---
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running org.apache.hadoop.yarn.server.nodemanager.containermanager.container.TestContainer
[INFO] Tests run: 34, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 1.724 s - in org.apache.hadoop.yarn.server.nodemanager.containermanager.container.TestContainer
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 34, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 7.225 s
[INFO] Finished at: 2019-02-25T11:24:29+00:00
[INFO] Final Memory: 44M/668M
[INFO] ------------------------------------------------------------------------
```

## TestApplication

```
[INFO] Scanning for projects...
[INFO]                                                                         
[INFO] ------------------------------------------------------------------------
[INFO] Building Apache Hadoop YARN NodeManager 3.3.0-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO] 
[INFO] --- maven-antrun-plugin:1.7:run (create-testdirs) @ hadoop-yarn-server-nodemanager ---
[INFO] Executing tasks

main:
[INFO] Executed tasks
[INFO] 
[INFO] --- hadoop-maven-plugins:3.3.0-SNAPSHOT:protoc (compile-protoc) @ hadoop-yarn-server-nodemanager ---
[INFO] No changes detected in protoc files, skipping generation.
[INFO] 
[INFO] --- maven-remote-resources-plugin:1.5:process (default) @ hadoop-yarn-server-nodemanager ---
[INFO] 
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ hadoop-yarn-server-nodemanager ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 26 resources
[INFO] Copying 2 resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:compile (default-compile) @ hadoop-yarn-server-nodemanager ---
[INFO] Compiling 8 source files to /home/joakim/hadoop/hadoop-yarn-project/hadoop-yarn/hadoop-yarn-server/hadoop-yarn-server-nodemanager/target/classes
[INFO] 
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ hadoop-yarn-server-nodemanager ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 8 resources
[INFO] Copying 2 resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.1:testCompile (default-testCompile) @ hadoop-yarn-server-nodemanager ---
[INFO] Compiling 2 source files to /home/joakim/hadoop/hadoop-yarn-project/hadoop-yarn/hadoop-yarn-server/hadoop-yarn-server-nodemanager/target/test-classes
[INFO] 
[INFO] --- maven-surefire-plugin:3.0.0-M1:test (default-test) @ hadoop-yarn-server-nodemanager ---
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running org.apache.hadoop.yarn.server.nodemanager.containermanager.application.TestApplication
[INFO] Tests run: 10, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 5.123 s - in org.apache.hadoop.yarn.server.nodemanager.containermanager.application.TestApplication
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 10, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 10.932 s
[INFO] Finished at: 2019-02-25T11:26:02+00:00
[INFO] Final Memory: 44M/666M
[INFO] ------------------------------------------------------------------------
```