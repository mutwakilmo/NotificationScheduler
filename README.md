# NotificationScheduler

## Summary

-   `JobScheduler`  provides a flexible framework to intelligently accomplish background services.
-   `JobScheduler`  is only available on devices running API 21 and higher.
-   To use the  `JobScheduler`, you need two parts:  `JobService`  and  `JobInfo`.
-   `JobInfo`  is a set of conditions that trigger the job to run.
-   `JobService`  implements the job to run under the conditions specified by  `JobInfo`.
-   You only have to implement the  `onStartJob()`  and  `onStopJob()`  callback methods, which you do in your  `JobService`.
-   The implementation of your job occurs, or is started, in  `onStartJob()`.
-   The  `onStartJob()`  method returns a  `boolean`  value that indicates whether the service needs to process the work in a separate thread.
-   If  `onStartJob()`  returns  `true`, you must explicitly call  `jobFinished()`. If  `onStartJob()`  returns  `false`, the runtime calls  `jobFinished()`  on your behalf.
-   `JobService`  is processed on the main thread, so you should avoid lengthy calculations or I/O.
-   `JobScheduler`  is the manager class responsible for scheduling the task.  `JobScheduler`  batches tasks to maximize the efficiency of system resources, which means that you do not have exact control of when tasks are executed.
