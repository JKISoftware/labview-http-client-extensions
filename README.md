# labview-http-client-extensions
LabVIEW HTTP Client Extensions

A set of VIs that extend the functionality of the LabVIEW HTTP Client library in some useful ways:

- Asynchronous file download with progress monitoring and abort
- Follow redirects

# Proof of Concept (demonstrating use case)
![2021-01-22_17-46-45-2](https://user-images.githubusercontent.com/381432/105565157-2e0a8780-5cda-11eb-8715-e8ef35e02447.gif)
![image](https://user-images.githubusercontent.com/381432/105565260-d7517d80-5cda-11eb-98e9-84387756999f.png)



# Development Plan
- Create an HTTP GET (Asynchronous) actor that can be aborted, if needed, and messages progress back to the caller.
- Create an HTTP GET (Follow Redirects) that can follow redirects
