![Logo](../img/UPWT.png)
# Unblocked Primer
The Unblocked platform is a new platform for writing distributed applications. It leverages Blazor, a new Web UI frameowrk using C#, Razor and HTML with WebAssembly. It is designed to allow you to build interactive database multi-user web applications with no server infrastructure required and all in C#. The platform runs a distributed ledger and stores data in IndexedDB which allows applications and users to securely share data across their environments and applications

## Web Assembly (Wasm)
A W3C open standard to run low level byte code in browser. With this standard we can run server side languages(Rust, C++, C#… ) in browser directly instead of Javascript.

Remember those Java applets and Microsoft silverlight, where we have to install plugins in browser to run Java and C# code, but WebAssembly provides base standard and no need for any plugins now. The binary format are represented in .wasm file provide near native performance.

## SPAs
Single Page Application(SPA) is a web application build on a single page in browser and the block of the page get dynamically renders without rendering the complete page.

Angular, React, Vue and many other language provides support to build SPA, but all these languages build on top of same Javascript language. Now, Microsoft provides the base to build SPA using C# with Razor pages like syntax in ASP.Net Core and its called as Blazor.

## ASP.Net Core
ASP.Net core is an open source web framework which runs on Linux, Mac or Windows OS. Now ASP.Net core provides new web framework Blazor to build SPA using C# along with WebAssembly standard in browser.

## Distributed Ledger
A Distributed ledger is a technology based on Blockchain principles which allows data to be shared peer-to-peer in a secure and immutable way.

## IndexedDB
IndexedDB is a NoSQL database engine present in every modern browser. It allows rapid store, index and retrieval of data for applications.

## Components
In SPA, the dynamically renders block in a page based on user interaction are called as Components. SPA is a collection of component and also provides client side routing to provide the feel of multiple page and page navigations.

## Advantages
* Provides near native performance, efficient and it's portable.
* We can use existing rich .net ecosystem to include in web pages like Office tools and other tools from Nuget.
* Code maintenance and debugging is more reliable.

## Disadvantages
* Javascript is already very mature and lot of libraries already exists in the market.
* Blazor with Web Assembly standard is new to the market and takes time to mature and .net is early in the WebAssembly race.