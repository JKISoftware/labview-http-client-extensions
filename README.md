# LabVIEW HTTP Client Extensions
![image](https://user-images.githubusercontent.com/381432/105567072-8f375880-5ce4-11eb-82e8-8c9a94224876.png)

A set of VIs that extend the functionality of the LabVIEW HTTP Client library in some useful ways:

- Asynchronous file download with progress monitoring and abort
- Follow redirects

# Download and Install
[Download package on vipm.io](https://www.vipm.io/package/jki_lib_http_client_extensions/)

# Proof of Concept (demonstrating use case)
![2021-01-22_17-46-45-2](https://user-images.githubusercontent.com/381432/105565157-2e0a8780-5cda-11eb-8715-e8ef35e02447.gif)
![image](https://user-images.githubusercontent.com/381432/105565260-d7517d80-5cda-11eb-98e9-84387756999f.png)

# Design Approach
The asynchronous file download with progress monitoring and abort is achieved by spawning an asynchronous "actor" (not Actor Framework) that calls the "HTTP GET.vi".  This "actor" monitors the output file size and updates an internal DVR that's uses to share data between the actor and the API methods.  Aborting a download in progress is achieved by calling the VI:Abort method on the "actor" VI. This approach is necessary, if the HTTP GET.vi is downloading, since there is no other way to abort the download -- the HTTP Client does not support an abort and not even destroying the HTTP Client handle will abort a download in progress (HTTP GET blocks the call to the HTTP Client's CloseHandle.vi)

# Development Plan
- Create an HTTP GET (Asynchronous) actor that can be aborted, if needed, and messages progress back to the caller.
- Create an HTTP GET (Follow Redirects) that can follow redirects
