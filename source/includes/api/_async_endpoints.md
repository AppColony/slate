# Asynchronous Endpoints

> An example "JobStatus" response body:

```json
{
  "data": {
    "id": "d85a36cce4c7b4964413d056d8da7b39",
    "type": "job_status",
    "attributes": {
      "job_name": "crunching_the_numbers",
      "state": "queued"
    }
  }
}
```

Some operations in the MakeShift API can trigger long running background jobs and cannot return the result of the operation within a synchronous response. Asynchronous endpoints will be labelled so within this documentation and should function mostly the same: If a job was successully queued for the requested operation an **HTTP status code 202** will be return with a content body describing the jobs charateristic (see example). Other status codes, such as 404s, are still valid but an HTTP 200 should never be returned. 

In order to confirm the success or failure of an asynchronous operation the client must hold onto the returned `JobStatus ID` from the response body. A follow up query the <a href="#job-statuses">JobStatus endpoint</a> can then be made to check on the state of the job.  


Status | Meaning
---------- | -------
queued | The job is waiting to run. This state should rarely be seen unless the job queue was backed up.
running | The job is in progress.
completed | The job is done and has succeeded.
failed | The job has completely failed (MakeShift may have retried the operation several times but has now given up)
