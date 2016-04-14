# AndroidGradleLibraryNewShrinkerIssue

Shows an issue with attempting to use the new shrinker on a library.  The following error will occur:
```
  :compileDebugJavaWithJavac UP-TO-DATE
  :transformClassesWithNewClassShrinkerForDebug
  :processDebugJavaRes UP-TO-DATE
  :transformResourcesWithMergeJavaResForDebug
  :transformClassesAndResourcesWithSyncLibJarsForDebug FAILED
  
  FAILURE: Build failed with an exception.
    
  * What went wrong:
  Execution failed for task ':transformClassesAndResourcesWithSyncLibJarsForDebug'.
  > Empty Main scope for syncLibJars
  
  * Try:
  Run with --info or --debug option to get more log output.
  
  * Exception is:
  org.gradle.api.tasks.TaskExecutionException: Execution failed for task ':transformClassesAndResourcesWithSyncLibJarsForDebug'.
  	at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.executeActions(ExecuteActionsTaskExecuter.java:69)
  	at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.execute(ExecuteActionsTaskExecuter.java:46)
  	at org.gradle.api.internal.tasks.execution.PostExecutionAnalysisTaskExecuter.execute(PostExecutionAnalysisTaskExecuter.java:35)
  	at org.gradle.api.internal.tasks.execution.SkipUpToDateTaskExecuter.execute(SkipUpToDateTaskExecuter.java:64)
  	at org.gradle.api.internal.tasks.execution.ValidatingTaskExecuter.execute(ValidatingTaskExecuter.java:58)
  	at org.gradle.api.internal.tasks.execution.SkipEmptySourceFilesTaskExecuter.execute(SkipEmptySourceFilesTaskExecuter.java:52)
  	at org.gradle.api.internal.tasks.execution.SkipTaskWithNoActionsExecuter.execute(SkipTaskWithNoActionsExecuter.java:52)
  	at org.gradle.api.internal.tasks.execution.SkipOnlyIfTaskExecuter.execute(SkipOnlyIfTaskExecuter.java:53)
  	at org.gradle.api.internal.tasks.execution.ExecuteAtMostOnceTaskExecuter.execute(ExecuteAtMostOnceTaskExecuter.java:43)
  	at org.gradle.execution.taskgraph.DefaultTaskGraphExecuter$EventFiringTaskWorker.execute(DefaultTaskGraphExecuter.java:203)
  	at org.gradle.execution.taskgraph.DefaultTaskGraphExecuter$EventFiringTaskWorker.execute(DefaultTaskGraphExecuter.java:185)
  	at org.gradle.execution.taskgraph.AbstractTaskPlanExecutor$TaskExecutorWorker.processTask(AbstractTaskPlanExecutor.java:66)
  	at org.gradle.execution.taskgraph.AbstractTaskPlanExecutor$TaskExecutorWorker.run(AbstractTaskPlanExecutor.java:50)
  	at org.gradle.execution.taskgraph.DefaultTaskPlanExecutor.process(DefaultTaskPlanExecutor.java:25)
  	at org.gradle.execution.taskgraph.DefaultTaskGraphExecuter.execute(DefaultTaskGraphExecuter.java:110)
  	at org.gradle.execution.SelectedTaskExecutionAction.execute(SelectedTaskExecutionAction.java:37)
  	at org.gradle.execution.DefaultBuildExecuter.execute(DefaultBuildExecuter.java:37)
  	at org.gradle.execution.DefaultBuildExecuter.access$000(DefaultBuildExecuter.java:23)
  	at org.gradle.execution.DefaultBuildExecuter$1.proceed(DefaultBuildExecuter.java:43)
  	at org.gradle.execution.DryRunBuildExecutionAction.execute(DryRunBuildExecutionAction.java:32)
  	at org.gradle.execution.DefaultBuildExecuter.execute(DefaultBuildExecuter.java:37)
  	at org.gradle.execution.DefaultBuildExecuter.execute(DefaultBuildExecuter.java:30)
  	at org.gradle.initialization.DefaultGradleLauncher$4.run(DefaultGradleLauncher.java:154)
  	at org.gradle.internal.Factories$1.create(Factories.java:22)
  	at org.gradle.internal.progress.DefaultBuildOperationExecutor.run(DefaultBuildOperationExecutor.java:90)
  	at org.gradle.internal.progress.DefaultBuildOperationExecutor.run(DefaultBuildOperationExecutor.java:52)
  	at org.gradle.initialization.DefaultGradleLauncher.doBuildStages(DefaultGradleLauncher.java:151)
  	at org.gradle.initialization.DefaultGradleLauncher.access$200(DefaultGradleLauncher.java:32)
  	at org.gradle.initialization.DefaultGradleLauncher$1.create(DefaultGradleLauncher.java:99)
  	at org.gradle.initialization.DefaultGradleLauncher$1.create(DefaultGradleLauncher.java:93)
  	at org.gradle.internal.progress.DefaultBuildOperationExecutor.run(DefaultBuildOperationExecutor.java:90)
  	at org.gradle.internal.progress.DefaultBuildOperationExecutor.run(DefaultBuildOperationExecutor.java:62)
  	at org.gradle.initialization.DefaultGradleLauncher.doBuild(DefaultGradleLauncher.java:93)
  	at org.gradle.initialization.DefaultGradleLauncher.run(DefaultGradleLauncher.java:82)
  	at org.gradle.launcher.exec.InProcessBuildActionExecuter$DefaultBuildController.run(InProcessBuildActionExecuter.java:94)
  	at org.gradle.tooling.internal.provider.ExecuteBuildActionRunner.run(ExecuteBuildActionRunner.java:28)
  	at org.gradle.launcher.exec.ChainingBuildActionRunner.run(ChainingBuildActionRunner.java:35)
  	at org.gradle.launcher.exec.InProcessBuildActionExecuter.execute(InProcessBuildActionExecuter.java:43)
  	at org.gradle.launcher.exec.InProcessBuildActionExecuter.execute(InProcessBuildActionExecuter.java:28)
  	at org.gradle.launcher.exec.ContinuousBuildActionExecuter.execute(ContinuousBuildActionExecuter.java:78)
  	at org.gradle.launcher.exec.ContinuousBuildActionExecuter.execute(ContinuousBuildActionExecuter.java:48)
  	at org.gradle.launcher.exec.DaemonUsageSuggestingBuildActionExecuter.execute(DaemonUsageSuggestingBuildActionExecuter.java:51)
  	at org.gradle.launcher.exec.DaemonUsageSuggestingBuildActionExecuter.execute(DaemonUsageSuggestingBuildActionExecuter.java:28)
  	at org.gradle.launcher.cli.RunBuildAction.run(RunBuildAction.java:43)
  	at org.gradle.internal.Actions$RunnableActionAdapter.execute(Actions.java:170)
  	at org.gradle.launcher.cli.CommandLineActionFactory$ParseAndBuildAction.execute(CommandLineActionFactory.java:237)
  	at org.gradle.launcher.cli.CommandLineActionFactory$ParseAndBuildAction.execute(CommandLineActionFactory.java:210)
  	at org.gradle.launcher.cli.JavaRuntimeValidationAction.execute(JavaRuntimeValidationAction.java:35)
  	at org.gradle.launcher.cli.JavaRuntimeValidationAction.execute(JavaRuntimeValidationAction.java:24)
  	at org.gradle.launcher.cli.CommandLineActionFactory$WithLogging.execute(CommandLineActionFactory.java:206)
  	at org.gradle.launcher.cli.CommandLineActionFactory$WithLogging.execute(CommandLineActionFactory.java:169)
  	at org.gradle.launcher.cli.ExceptionReportingAction.execute(ExceptionReportingAction.java:33)
  	at org.gradle.launcher.cli.ExceptionReportingAction.execute(ExceptionReportingAction.java:22)
  	at org.gradle.launcher.Main.doAction(Main.java:33)
	  at org.gradle.launcher.bootstrap.EntryPoint.run(EntryPoint.java:45)
	  at org.gradle.launcher.bootstrap.ProcessBootstrap.runNoExit(ProcessBootstrap.java:54)
	  at org.gradle.launcher.bootstrap.ProcessBootstrap.run(ProcessBootstrap.java:35)
  	at org.gradle.launcher.GradleMain.main(GradleMain.java:23)
  	at org.gradle.wrapper.BootstrapMainStarter.start(BootstrapMainStarter.java:30)
  	at org.gradle.wrapper.WrapperExecutor.execute(WrapperExecutor.java:129)
  	at org.gradle.wrapper.GradleWrapperMain.main(GradleWrapperMain.java:61)
  Caused by: java.lang.RuntimeException: Empty Main scope for syncLibJars
  	at com.android.build.gradle.internal.tasks.LibraryJarTransform.transform(LibraryJarTransform.java:185)
  	at com.android.build.gradle.internal.pipeline.TransformTask$3.call(TransformTask.java:178)
  	at com.android.build.gradle.internal.pipeline.TransformTask$3.call(TransformTask.java:174)
  	at com.android.builder.profile.ThreadRecorder$1.record(ThreadRecorder.java:55)
  	at com.android.builder.profile.ThreadRecorder$1.record(ThreadRecorder.java:47)
  	at com.android.build.gradle.internal.pipeline.TransformTask.transform(TransformTask.java:173)
  	at org.gradle.internal.reflect.JavaMethod.invoke(JavaMethod.java:75)
  	at org.gradle.api.internal.project.taskfactory.AnnotationProcessingTaskFactory$IncrementalTaskAction.doExecute(AnnotationProcessingTaskFactory.java:244)
  	at org.gradle.api.internal.project.taskfactory.AnnotationProcessingTaskFactory$StandardTaskAction.execute(AnnotationProcessingTaskFactory.java:220)
  	at org.gradle.api.internal.project.taskfactory.AnnotationProcessingTaskFactory$IncrementalTaskAction.execute(AnnotationProcessingTaskFactory.java:231)
  	at org.gradle.api.internal.project.taskfactory.AnnotationProcessingTaskFactory$StandardTaskAction.execute(AnnotationProcessingTaskFactory.java:209)
  	at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.executeAction(ExecuteActionsTaskExecuter.java:80)
  	at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.executeActions(ExecuteActionsTaskExecuter.java:61)
  	... 60 more


BUILD FAILED
```
