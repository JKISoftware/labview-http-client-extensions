# labview-http-client-extensions
LabVIEW HTTP Client Extensions

A set of VIs that extend the functionality of the LabVIEW HTTP Client library in some useful ways:

- Asynchronous file download with progress monitoring and abort
- Follow redirects

# Proof of Concept (demonstrating use case)
![image](https://user-images.githubusercontent.com/381432/105542174-c76f7480-5cad-11eb-8df3-fb00deadc6b9.png)

# Development Plan
Create an HTTP GET (Asynchronous) actor that can be aborted, if needed, and messages progress back to the caller.
