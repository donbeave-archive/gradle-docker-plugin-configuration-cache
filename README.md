# Cannot query the value of task ':dockerBuild' property 'dockerClientService' because it has no value available.

## Steps to reproduce

1. Clone the project
2. Run `gradle dockerBuild --info --stacktrace`

And will return the error:

```
Initialized native services in: /Users/donbeave/.gradle/native
Initialized jansi services in: /Users/donbeave/.gradle/native
The client will now receive all logging from the daemon (pid: 17525). The daemon log file: /Users/donbeave/.gradle/daemon/7.5.1/daemon-17525.out.log
Starting 7th build in daemon [uptime: 10 mins 15.694 secs, performance: 99%, non-heap usage: 51% of 256 MiB]
Using 10 worker leases.
Now considering [/Users/donbeave/Projects/gradle-docker-plugin-configuration-cache, /Users/donbeave/Downloads/demo] as hierarchies to watch
Watching the file system is configured to be enabled if available
File system watching is active
Starting Build
Settings evaluated using settings file '/Users/donbeave/Projects/gradle-docker-plugin-configuration-cache/settings.gradle.kts'.
Projects loaded. Root project using build file '/Users/donbeave/Projects/gradle-docker-plugin-configuration-cache/build.gradle.kts'.
Included projects: [root project 'demo']

> Configure project :
Evaluating root project 'demo' using build file '/Users/donbeave/Projects/gradle-docker-plugin-configuration-cache/build.gradle.kts'.
Default docker.url set to unix:///Users/donbeave/.docker/run/docker.sock
Creating docker tasks for image main
Caching disabled for Kotlin DSL accessors for root project 'demo' because:
  Build cache is disabled
Skipping Kotlin DSL accessors for root project 'demo' as it is up-to-date.
All projects evaluated.
Task name matched 'dockerBuild'
Selected primary task 'dockerBuild' from project :
Tasks to be executed: [task ':compileJava', task ':processResources', task ':classes', task ':runnerJar', task ':buildLayers', task ':dockerfile', task ':dockerBuild']
Tasks that were excluded: []
Resolve mutations for :compileJava (Thread[Execution worker,5,main]) started.
Resolve mutations for :compileJava (Thread[Execution worker,5,main]) completed. Took 0.0 secs.
:compileJava (Thread[included builds,5,main]) started.

> Task :compileJava
Watching 1 directory hierarchies to track changes
Caching disabled for task ':compileJava' because:
  Build cache is disabled
Task ':compileJava' is not up-to-date because:
  No history is available.
The input changes require a full rebuild for incremental task ':compileJava'.
Full recompilation is required because no incremental change information is available. This is usually caused by clean builds or changing compiler arguments.
Compiling with toolchain '/Users/donbeave/.asdf/installs/java/temurin-17.0.4+101'.
Compiling with JDK Java compiler API.
Class dependency analysis for incremental compilation took 0.0 secs.
Created classpath snapshot for incremental compilation in 0.004 secs.
:compileJava (Thread[included builds,5,main]) completed. Took 0.205 secs.
Resolve mutations for :processResources (Thread[Execution worker Thread 3,5,main]) started.
Resolve mutations for :processResources (Thread[Execution worker Thread 3,5,main]) completed. Took 0.0 secs.
:processResources (Thread[included builds,5,main]) started.

> Task :processResources
Caching disabled for task ':processResources' because:
  Build cache is disabled
Task ':processResources' is not up-to-date because:
  No history is available.
:processResources (Thread[included builds,5,main]) completed. Took 0.002 secs.
Resolve mutations for :classes (Thread[Execution worker Thread 3,5,main]) started.
Resolve mutations for :classes (Thread[Execution worker Thread 3,5,main]) completed. Took 0.0 secs.
:classes (Thread[Execution worker Thread 6,5,main]) started.

> Task :classes
Skipping task ':classes' as it has no actions.
:classes (Thread[Execution worker Thread 6,5,main]) completed. Took 0.0 secs.
Resolve mutations for :runnerJar (Thread[Execution worker Thread 3,5,main]) started.
Resolve mutations for :runnerJar (Thread[Execution worker Thread 3,5,main]) completed. Took 0.0 secs.
:runnerJar (Thread[Execution worker Thread 6,5,main]) started.

> Task :runnerJar
Caching disabled for task ':runnerJar' because:
  Build cache is disabled
Task ':runnerJar' is not up-to-date because:
  No history is available.
:runnerJar (Thread[Execution worker Thread 6,5,main]) completed. Took 0.011 secs.
Resolve mutations for :buildLayers (Thread[Execution worker Thread 3,5,main]) started.
Resolve mutations for :buildLayers (Thread[Execution worker Thread 3,5,main]) completed. Took 0.0 secs.
:buildLayers (Thread[Execution worker Thread 6,5,main]) started.

> Task :buildLayers
Caching disabled for task ':buildLayers' because:
  Build cache is disabled
Task ':buildLayers' is not up-to-date because:
  No history is available.
:buildLayers (Thread[Execution worker Thread 6,5,main]) completed. Took 0.067 secs.
Resolve mutations for :dockerfile (Thread[Execution worker Thread 3,5,main]) started.
Resolve mutations for :dockerfile (Thread[Execution worker Thread 3,5,main]) completed. Took 0.0 secs.
:dockerfile (Thread[Execution worker Thread 6,5,main]) started.

> Task :dockerfile
Caching disabled for task ':dockerfile' because:
  Build cache is disabled
Task ':dockerfile' is not up-to-date because:
  No history is available.
Dockerfile written to: /Users/donbeave/Projects/gradle-docker-plugin-configuration-cache/build/docker/main/Dockerfile
:dockerfile (Thread[Execution worker Thread 6,5,main]) completed. Took 0.002 secs.
Resolve mutations for :dockerBuild (Thread[Execution worker Thread 3,5,main]) started.
Resolve mutations for :dockerBuild (Thread[Execution worker Thread 3,5,main]) completed. Took 0.0 secs.
:dockerBuild (Thread[Execution worker Thread 6,5,main]) started.
producer locations for task group 0 (Thread[Execution worker,5,main]) started.
producer locations for task group 0 (Thread[Execution worker,5,main]) completed. Took 0.0 secs.

> Task :dockerBuild FAILED
Caching disabled for task ':dockerBuild' because:
  Build cache is disabled
Task ':dockerBuild' is not up-to-date because:
  Task.upToDateWhen is false.
Building image using context '/Users/donbeave/Projects/gradle-docker-plugin-configuration-cache/build/docker/main'.
Using Dockerfile '/Users/donbeave/Projects/gradle-docker-plugin-configuration-cache/build/docker/main/Dockerfile'
:dockerBuild (Thread[Execution worker Thread 6,5,main]) completed. Took 0.003 secs.

FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':dockerBuild'.
> Cannot query the value of task ':dockerBuild' property 'dockerClientService' because it has no value available.

* Try:
> Run with --debug option to get more log output.
> Run with --scan to get full insights.

* Exception is:
org.gradle.api.tasks.TaskExecutionException: Execution failed for task ':dockerBuild'.
        at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.lambda$executeIfValid$1(ExecuteActionsTaskExecuter.java:142)
        at org.gradle.internal.Try$Failure.ifSuccessfulOrElse(Try.java:282)
        at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.executeIfValid(ExecuteActionsTaskExecuter.java:140)
        at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.execute(ExecuteActionsTaskExecuter.java:128)
        at org.gradle.api.internal.tasks.execution.CleanupStaleOutputsExecuter.execute(CleanupStaleOutputsExecuter.java:77)
        at org.gradle.api.internal.tasks.execution.FinalizePropertiesTaskExecuter.execute(FinalizePropertiesTaskExecuter.java:46)
        at org.gradle.api.internal.tasks.execution.ResolveTaskExecutionModeExecuter.execute(ResolveTaskExecutionModeExecuter.java:51)
        at org.gradle.api.internal.tasks.execution.SkipTaskWithNoActionsExecuter.execute(SkipTaskWithNoActionsExecuter.java:57)
        at org.gradle.api.internal.tasks.execution.SkipOnlyIfTaskExecuter.execute(SkipOnlyIfTaskExecuter.java:56)
        at org.gradle.api.internal.tasks.execution.CatchExceptionTaskExecuter.execute(CatchExceptionTaskExecuter.java:36)
        at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter$1.executeTask(EventFiringTaskExecuter.java:77)
        at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter$1.call(EventFiringTaskExecuter.java:55)
        at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter$1.call(EventFiringTaskExecuter.java:52)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$CallableBuildOperationWorker.execute(DefaultBuildOperationRunner.java:204)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$CallableBuildOperationWorker.execute(DefaultBuildOperationRunner.java:199)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$2.execute(DefaultBuildOperationRunner.java:66)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$2.execute(DefaultBuildOperationRunner.java:59)
        at org.gradle.internal.operations.DefaultBuildOperationRunner.execute(DefaultBuildOperationRunner.java:157)
        at org.gradle.internal.operations.DefaultBuildOperationRunner.execute(DefaultBuildOperationRunner.java:59)
        at org.gradle.internal.operations.DefaultBuildOperationRunner.call(DefaultBuildOperationRunner.java:53)
        at org.gradle.internal.operations.DefaultBuildOperationExecutor.call(DefaultBuildOperationExecutor.java:73)
        at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter.execute(EventFiringTaskExecuter.java:52)
        at org.gradle.execution.plan.LocalTaskNodeExecutor.execute(LocalTaskNodeExecutor.java:69)
        at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$InvokeNodeExecutorsAction.execute(DefaultTaskExecutionGraph.java:327)
        at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$InvokeNodeExecutorsAction.execute(DefaultTaskExecutionGraph.java:314)
        at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$BuildOperationAwareExecutionAction.execute(DefaultTaskExecutionGraph.java:307)
        at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$BuildOperationAwareExecutionAction.execute(DefaultTaskExecutionGraph.java:293)
        at org.gradle.execution.plan.DefaultPlanExecutor$ExecutorWorker.execute(DefaultPlanExecutor.java:420)
        at org.gradle.execution.plan.DefaultPlanExecutor$ExecutorWorker.run(DefaultPlanExecutor.java:342)
        at org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:64)
        at org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:48)
Caused by: org.gradle.api.internal.provider.MissingValueException: Cannot query the value of task ':dockerBuild' property 'dockerClientService' because it has no value available.
        at org.gradle.api.internal.provider.AbstractMinimalProvider.get(AbstractMinimalProvider.java:85)
        at com.bmuschko.gradle.docker.tasks.AbstractDockerRemoteApiTask.getDockerClient(AbstractDockerRemoteApiTask.groovy:142)
        at com.bmuschko.gradle.docker.tasks.image.DockerBuildImage_Decorated.getDockerClient(Unknown Source)
        at com.bmuschko.gradle.docker.tasks.image.DockerBuildImage.runRemoteCommand(DockerBuildImage.groovy:270)
        at com.bmuschko.gradle.docker.tasks.AbstractDockerRemoteApiTask.start(AbstractDockerRemoteApiTask.groovy:70)
        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77)
        at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
        at org.gradle.internal.reflect.JavaMethod.invoke(JavaMethod.java:125)
        at org.gradle.api.internal.project.taskfactory.StandardTaskAction.doExecute(StandardTaskAction.java:58)
        at org.gradle.api.internal.project.taskfactory.StandardTaskAction.execute(StandardTaskAction.java:51)
        at org.gradle.api.internal.project.taskfactory.StandardTaskAction.execute(StandardTaskAction.java:29)
        at org.gradle.api.internal.tasks.execution.TaskExecution$3.run(TaskExecution.java:236)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$1.execute(DefaultBuildOperationRunner.java:29)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$1.execute(DefaultBuildOperationRunner.java:26)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$2.execute(DefaultBuildOperationRunner.java:66)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$2.execute(DefaultBuildOperationRunner.java:59)
        at org.gradle.internal.operations.DefaultBuildOperationRunner.execute(DefaultBuildOperationRunner.java:157)
        at org.gradle.internal.operations.DefaultBuildOperationRunner.execute(DefaultBuildOperationRunner.java:59)
        at org.gradle.internal.operations.DefaultBuildOperationRunner.run(DefaultBuildOperationRunner.java:47)
        at org.gradle.internal.operations.DefaultBuildOperationExecutor.run(DefaultBuildOperationExecutor.java:68)
        at org.gradle.api.internal.tasks.execution.TaskExecution.executeAction(TaskExecution.java:221)
        at org.gradle.api.internal.tasks.execution.TaskExecution.executeActions(TaskExecution.java:204)
        at org.gradle.api.internal.tasks.execution.TaskExecution.executeWithPreviousOutputFiles(TaskExecution.java:187)
        at org.gradle.api.internal.tasks.execution.TaskExecution.execute(TaskExecution.java:165)
        at org.gradle.internal.execution.steps.ExecuteStep.executeInternal(ExecuteStep.java:89)
        at org.gradle.internal.execution.steps.ExecuteStep.access$000(ExecuteStep.java:40)
        at org.gradle.internal.execution.steps.ExecuteStep$1.call(ExecuteStep.java:53)
        at org.gradle.internal.execution.steps.ExecuteStep$1.call(ExecuteStep.java:50)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$CallableBuildOperationWorker.execute(DefaultBuildOperationRunner.java:204)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$CallableBuildOperationWorker.execute(DefaultBuildOperationRunner.java:199)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$2.execute(DefaultBuildOperationRunner.java:66)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$2.execute(DefaultBuildOperationRunner.java:59)
        at org.gradle.internal.operations.DefaultBuildOperationRunner.execute(DefaultBuildOperationRunner.java:157)
        at org.gradle.internal.operations.DefaultBuildOperationRunner.execute(DefaultBuildOperationRunner.java:59)
        at org.gradle.internal.operations.DefaultBuildOperationRunner.call(DefaultBuildOperationRunner.java:53)
        at org.gradle.internal.operations.DefaultBuildOperationExecutor.call(DefaultBuildOperationExecutor.java:73)
        at org.gradle.internal.execution.steps.ExecuteStep.execute(ExecuteStep.java:50)
        at org.gradle.internal.execution.steps.ExecuteStep.execute(ExecuteStep.java:40)
        at org.gradle.internal.execution.steps.RemovePreviousOutputsStep.execute(RemovePreviousOutputsStep.java:68)
        at org.gradle.internal.execution.steps.RemovePreviousOutputsStep.execute(RemovePreviousOutputsStep.java:38)
        at org.gradle.internal.execution.steps.CancelExecutionStep.execute(CancelExecutionStep.java:41)
        at org.gradle.internal.execution.steps.TimeoutStep.executeWithoutTimeout(TimeoutStep.java:74)
        at org.gradle.internal.execution.steps.TimeoutStep.execute(TimeoutStep.java:55)
        at org.gradle.internal.execution.steps.CreateOutputsStep.execute(CreateOutputsStep.java:51)
        at org.gradle.internal.execution.steps.CreateOutputsStep.execute(CreateOutputsStep.java:29)
        at org.gradle.internal.execution.steps.CaptureStateAfterExecutionStep.executeDelegateBroadcastingChanges(CaptureStateAfterExecutionStep.java:124)
        at org.gradle.internal.execution.steps.CaptureStateAfterExecutionStep.execute(CaptureStateAfterExecutionStep.java:80)
        at org.gradle.internal.execution.steps.CaptureStateAfterExecutionStep.execute(CaptureStateAfterExecutionStep.java:58)
        at org.gradle.internal.execution.steps.ResolveInputChangesStep.execute(ResolveInputChangesStep.java:48)
        at org.gradle.internal.execution.steps.ResolveInputChangesStep.execute(ResolveInputChangesStep.java:36)
        at org.gradle.internal.execution.steps.BuildCacheStep.executeWithoutCache(BuildCacheStep.java:181)
        at org.gradle.internal.execution.steps.BuildCacheStep.lambda$execute$1(BuildCacheStep.java:71)
        at org.gradle.internal.Either$Right.fold(Either.java:175)
        at org.gradle.internal.execution.caching.CachingState.fold(CachingState.java:59)
        at org.gradle.internal.execution.steps.BuildCacheStep.execute(BuildCacheStep.java:69)
        at org.gradle.internal.execution.steps.BuildCacheStep.execute(BuildCacheStep.java:47)
        at org.gradle.internal.execution.steps.StoreExecutionStateStep.execute(StoreExecutionStateStep.java:36)
        at org.gradle.internal.execution.steps.StoreExecutionStateStep.execute(StoreExecutionStateStep.java:25)
        at org.gradle.internal.execution.steps.RecordOutputsStep.execute(RecordOutputsStep.java:36)
        at org.gradle.internal.execution.steps.RecordOutputsStep.execute(RecordOutputsStep.java:22)
        at org.gradle.internal.execution.steps.SkipUpToDateStep.executeBecause(SkipUpToDateStep.java:110)
        at org.gradle.internal.execution.steps.SkipUpToDateStep.lambda$execute$2(SkipUpToDateStep.java:56)
        at org.gradle.internal.execution.steps.SkipUpToDateStep.execute(SkipUpToDateStep.java:56)
        at org.gradle.internal.execution.steps.SkipUpToDateStep.execute(SkipUpToDateStep.java:38)
        at org.gradle.internal.execution.steps.ResolveChangesStep.execute(ResolveChangesStep.java:73)
        at org.gradle.internal.execution.steps.ResolveChangesStep.execute(ResolveChangesStep.java:44)
        at org.gradle.internal.execution.steps.legacy.MarkSnapshottingInputsFinishedStep.execute(MarkSnapshottingInputsFinishedStep.java:37)
        at org.gradle.internal.execution.steps.legacy.MarkSnapshottingInputsFinishedStep.execute(MarkSnapshottingInputsFinishedStep.java:27)
        at org.gradle.internal.execution.steps.ResolveCachingStateStep.execute(ResolveCachingStateStep.java:89)
        at org.gradle.internal.execution.steps.ResolveCachingStateStep.execute(ResolveCachingStateStep.java:50)
        at org.gradle.internal.execution.steps.ValidateStep.execute(ValidateStep.java:114)
        at org.gradle.internal.execution.steps.ValidateStep.execute(ValidateStep.java:57)
        at org.gradle.internal.execution.steps.CaptureStateBeforeExecutionStep.execute(CaptureStateBeforeExecutionStep.java:76)
        at org.gradle.internal.execution.steps.CaptureStateBeforeExecutionStep.execute(CaptureStateBeforeExecutionStep.java:50)
        at org.gradle.internal.execution.steps.SkipEmptyWorkStep.executeWithNoEmptySources(SkipEmptyWorkStep.java:254)
        at org.gradle.internal.execution.steps.SkipEmptyWorkStep.execute(SkipEmptyWorkStep.java:91)
        at org.gradle.internal.execution.steps.SkipEmptyWorkStep.execute(SkipEmptyWorkStep.java:56)
        at org.gradle.internal.execution.steps.RemoveUntrackedExecutionStateStep.execute(RemoveUntrackedExecutionStateStep.java:32)
        at org.gradle.internal.execution.steps.RemoveUntrackedExecutionStateStep.execute(RemoveUntrackedExecutionStateStep.java:21)
        at org.gradle.internal.execution.steps.legacy.MarkSnapshottingInputsStartedStep.execute(MarkSnapshottingInputsStartedStep.java:38)
        at org.gradle.internal.execution.steps.LoadPreviousExecutionStateStep.execute(LoadPreviousExecutionStateStep.java:43)
        at org.gradle.internal.execution.steps.LoadPreviousExecutionStateStep.execute(LoadPreviousExecutionStateStep.java:31)
        at org.gradle.internal.execution.steps.AssignWorkspaceStep.lambda$execute$0(AssignWorkspaceStep.java:40)
        at org.gradle.api.internal.tasks.execution.TaskExecution$4.withWorkspace(TaskExecution.java:281)
        at org.gradle.internal.execution.steps.AssignWorkspaceStep.execute(AssignWorkspaceStep.java:40)
        at org.gradle.internal.execution.steps.AssignWorkspaceStep.execute(AssignWorkspaceStep.java:30)
        at org.gradle.internal.execution.steps.IdentityCacheStep.execute(IdentityCacheStep.java:37)
        at org.gradle.internal.execution.steps.IdentityCacheStep.execute(IdentityCacheStep.java:27)
        at org.gradle.internal.execution.steps.IdentifyStep.execute(IdentifyStep.java:44)
        at org.gradle.internal.execution.steps.IdentifyStep.execute(IdentifyStep.java:33)
        at org.gradle.internal.execution.impl.DefaultExecutionEngine$1.execute(DefaultExecutionEngine.java:76)
        at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.executeIfValid(ExecuteActionsTaskExecuter.java:139)
        at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.execute(ExecuteActionsTaskExecuter.java:128)
        at org.gradle.api.internal.tasks.execution.CleanupStaleOutputsExecuter.execute(CleanupStaleOutputsExecuter.java:77)
        at org.gradle.api.internal.tasks.execution.FinalizePropertiesTaskExecuter.execute(FinalizePropertiesTaskExecuter.java:46)
        at org.gradle.api.internal.tasks.execution.ResolveTaskExecutionModeExecuter.execute(ResolveTaskExecutionModeExecuter.java:51)
        at org.gradle.api.internal.tasks.execution.SkipTaskWithNoActionsExecuter.execute(SkipTaskWithNoActionsExecuter.java:57)
        at org.gradle.api.internal.tasks.execution.SkipOnlyIfTaskExecuter.execute(SkipOnlyIfTaskExecuter.java:56)
        at org.gradle.api.internal.tasks.execution.CatchExceptionTaskExecuter.execute(CatchExceptionTaskExecuter.java:36)
        at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter$1.executeTask(EventFiringTaskExecuter.java:77)
        at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter$1.call(EventFiringTaskExecuter.java:55)
        at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter$1.call(EventFiringTaskExecuter.java:52)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$CallableBuildOperationWorker.execute(DefaultBuildOperationRunner.java:204)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$CallableBuildOperationWorker.execute(DefaultBuildOperationRunner.java:199)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$2.execute(DefaultBuildOperationRunner.java:66)
        at org.gradle.internal.operations.DefaultBuildOperationRunner$2.execute(DefaultBuildOperationRunner.java:59)
        at org.gradle.internal.operations.DefaultBuildOperationRunner.execute(DefaultBuildOperationRunner.java:157)
        at org.gradle.internal.operations.DefaultBuildOperationRunner.execute(DefaultBuildOperationRunner.java:59)
        at org.gradle.internal.operations.DefaultBuildOperationRunner.call(DefaultBuildOperationRunner.java:53)
        at org.gradle.internal.operations.DefaultBuildOperationExecutor.call(DefaultBuildOperationExecutor.java:73)
        at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter.execute(EventFiringTaskExecuter.java:52)
        at org.gradle.execution.plan.LocalTaskNodeExecutor.execute(LocalTaskNodeExecutor.java:69)
        at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$InvokeNodeExecutorsAction.execute(DefaultTaskExecutionGraph.java:327)
        at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$InvokeNodeExecutorsAction.execute(DefaultTaskExecutionGraph.java:314)
        at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$BuildOperationAwareExecutionAction.execute(DefaultTaskExecutionGraph.java:307)
        at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$BuildOperationAwareExecutionAction.execute(DefaultTaskExecutionGraph.java:293)
        at org.gradle.execution.plan.DefaultPlanExecutor$ExecutorWorker.execute(DefaultPlanExecutor.java:420)
        at org.gradle.execution.plan.DefaultPlanExecutor$ExecutorWorker.run(DefaultPlanExecutor.java:342)
        at org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:64)
        at org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:48)


* Get more help at https://help.gradle.org

BUILD FAILED in 623ms
6 actionable tasks: 6 executed
Watched directory hierarchies: [/Users/donbeave/Projects/gradle-docker-plugin-configuration-cache]
```

Reproducable on:

OpenJDK 17:

```
openjdk 17.0.4.1 2022-08-12
OpenJDK Runtime Environment Temurin-17.0.4.1+1 (build 17.0.4.1+1)
OpenJDK 64-Bit Server VM Temurin-17.0.4.1+1 (build 17.0.4.1+1, mixed mode)
```

macOS Ventura 13.0.1 (22A400)
