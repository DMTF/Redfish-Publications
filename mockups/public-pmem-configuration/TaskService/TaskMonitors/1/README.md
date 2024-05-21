## TaskMonitor

What is a Task Monitor?
 - The Task Monitor is used by the Client to get the Response Body of the actual operation.
 - While the operation is going on, a 202 will be returned.
 -  When the operation is finished, the Response Body will be returned with the content the same as if the Request had been synchronous.

The Task Monitor is a URL returned after a Task has been created, and is used by the clients to poll and see when the task has completed (GET on the task monitor URL)
