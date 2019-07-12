![Logo](./img/UPWT.png)
# Architecture
The Unblocked platform was designed from the ground up to allow application developers to write applications with the following key attributes:

* **Run Anywhere** - Applications developed with the unblocked platform run on any modern web browser.
* **Include Full functionality data access** - Applications developed with the unblocked platform provide full featured data models and access
* **Require no backend** - Unblocked platform applications only require a flat file web server. There is no requirement for central databases or servers.
* **Are very secure** - Unblocked platform applications use a comprehensive X509 Certificate infrastucture and industry grade encryption and decryption.
* **Are highly scalable** - Processing occurs on users devices and data is shared peer-to-peer meaning these applications are highly scalable.
* **Are simple to write** - Unblocked platform applications are easy and quick to write
* **Uses your current knowledge** - Developers with an understanding of HTML, CSS and C# can easily write unblocked applications.

We've been developing this platform since the advent of the [Blazor](https://blazor.net) project to provide a way to solve some of our challenging technology issues. In January 2019, we decided to release our system as a platform that others can use to develop their own distributed applications.

At the core of the platform is a **distributed ledger**, using a technology that we developed purely in .net. Our distributed ledger implements end to end cryptography, merkle trees for speed, epochs for data storage and X509 Certificates for Private and Public key storage.

![Diagram](./img/ArchitectureDiagram.png)
*Architecture Diagram*

The diagram above shows a high level overview of the complete architecture of an application written on the unblocked platform. The various components are described below:

## User Generated

### User Application
Users (or developers) using the unblocked platform develop their applications in visual studio. The development experience is similar to developing a Razor application or more closely aligned a Microsoft Blazor Client Side application.

As there is no need for servers in this platform implementation, we do not have a concept of a server hosted example.

  ***Note**: It may be possible in the future to leverage functionality in the dotnet core server functions but for version 1 of the platform, this is not considered.*

## Microsoft Provided
### Microsoft Blazor
Microsoft's blazor framework is a new Single Page Application Framework, written in .Net which takes advantage of WebAssembly. As our platform requires WebAssembly, the Blazor framework makes sens to use.

## 3rd Party
### IndexedDB
IndexedDB is a No-SQL database included in every modern browser which supports html5. It provides a high performance local database.

### WebAssembly
WebAssembly is a new technology which allows the compilation of code into a new assembly language which operates at high speed inside a browser virtual machine.

### WebRTC
WebRTC is a peer to peer communication system within the browser. Initially designed to support voice and video, WebRTC allows the transmission of data across and through complex networks.

## Unblocked Components
### BC.DataAccess
The BC.DataAccess Layer provides a public API to support data operations. Using the BC.DataAccess Layer, one can define and manage data models and send and receive data between users of teh application using a simple, accessible programming style.

### BC.IndexedDB

### BC.Node

### BC.PKI.Core

### BC.FileReader

### BC.Storage

# External Functions
## Payment Portal

## STUN and TURN Server

## Azure Functions

