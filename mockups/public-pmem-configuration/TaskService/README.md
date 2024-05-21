## TaskService
This TaskService contains the example Task for **PMEM-AllMem**. The TaskService describes the overall task implemented functionality, policies, enabled, etc.  and is the starting link to get to the actual Task Resources.

From Redfish School - Tasks:
> * Any operation could end up as an Asynchronous Operation
>   * If the operation has been accepted for processing, a 202 can be returned. This mean a
> Task has been started to complete the request
>      * The “Location” header is set to the URI of a Task Monitor.
>      * There may also be a “Retry-After” header to specify the amount of time the client should wait before querying the Task Monitor
>      * The Response Body should contain the Task Resource and not the expected Resource.
>* What is a Task Monitor?
>   * The Task Monitor is used by the Client to get the Response Body of the actual operation.
>   * While the operation is going on, a 202 will be returned.
>   * When the operation is finished, the Response Body will be returned with the content the same as if the Request had been synchronous.
>* What’s the Task Resource for then?
>   * The Task Resource can be used by entities other than the client to track the operation.
>      * The Client can use either the Task Resource or the Task Monitor, but the Task Monitor is probably preferable since it would have the expected Response Body but the Task Resource will not.
> * Canceling is done via the DELETE operation
>   * To either the Task Resource or the Task Monitor

**For more information**:
- [Redfish School - Tasks](https://www.dmtf.org/sites/default/files/Redfish%20School%20-%20Tasks_1.pdf)
- [Redfish Schema Index](https://redfish.dmtf.org/redfish/schema_index)
