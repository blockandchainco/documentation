![Logo](./img/UPWT.png)
# Release Notes
## unblocked platform 1.0.0 preview6

Welcome to the release notes for Bock and Chain Version 1.0.0-preview6. Please note, although this is a code complete release, we have a dependency on the Microsoft Blazor Project which is still in preview, thus the -preview6 moniker following our version information.

Whilst this is a **public** release, we are still in closed beta, and as such the following functions remain unavailable:

* **Certificate Generation** - It is not currently possible to generate certificates for the platform automatically. If you would like a certificate, you will need to [apply to the private beta program](https://mailchi.mp/747009030b07/unblockedplatformpreview).
* **VSIX file** In order to create unblocked platform applications, you need the Visual Studio Template file. This is currently not available in the marketplace and to obtain a preview copy, you will need to [apply to the private beta program](https://mailchi.mp/747009030b07/unblockedplatformpreview).

## Go Live License
This current release does not contain a go-live license. Therefore members of the private beta program may develop and use applications developed in pre-production environments only.

## Disclaimer
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## Products in this release
The following products are available following this release:

* [Unblocked Platform](https://www.nuget.org/packages/BC.Platform) - The Unblocked platform is a consolidated NuGet Package containing the core platform excluding all but a few UI Elements. It forms the basis for customers wishing to develop applications on the platform.

## Testing and Code Coverage
Currently we have approximately 30% code coverage in automated tests and up to 50% in manual passes. All tests are passing with this release. We have performed static code analysis and are currently actioning a number of recommendations.

## Open and Closed Source
The following items are open source:

* **[Documentation](https://github.com/blockandchainco/documentation)** - This Site
* **[Template and Sample Applications](https://github.com/blockandchainco/UP.AppTemplate)** - A range of template and sample applications to get up to speed on the platform.
* **[Visual Studio Extension](https://github.com/blockandchainco/UP.VSExtension)** - The Visual Studio Extension to quickly build applications

The following items are closed source
* **[BC.UnblockedPlatform](https://www.nuget.org/packages/BC.UnblockedPlatform)** - The Platform NuGet containing all the components below:
* **[BC.DataAccess](./dataaccess.md)** - The public API for working with Data
* **[BC.FileReader](./filereader.md)** - The public API for working with files in Blazor Applications
* **[BC.IndexedDB](./indexeddb.md)** - API for working directly with IndexedDB in the browser.
* **[BC.Node](./node.md)** - The software that maintains the distributed ledger and communication between application versions.
* **[BC.PKI.Core](./pki.md)** - Cryptography and Public Key Library designed for dotnet standard and dotnet code.
* **[BC.Shared](./shared.md)** - Shared objects and language snippets
* **[BC.Shared.Services](./services.md)** - Shared Services for Dependency Injection
* **[BC.Storage](./storage.md)** - Library to work with LocalStorage and SessionStorage in the browser.

# Items in this release
The following details the major development items that were completed in this release. 

* **Move from LocalStorage to IndexedDB** - The refactor of the platform to store information in IndexedDB is complete.
* **Implement DataAccess Layer** - The DataAccess Layer provides an interface to simply create data objects and models.
* **Implement X509 Certificates** - This release implemented X509 Certificates for the PKI Platform
* **Remove BouncyCastle** - All Cryptography is now using the System.Security.Cryptography namespaces from Microsoft.
* **Update to Blazor Preview6** - The platform now works on Microsoft Blazor Preview6.
* **Release Sample Application** - The platform now has a sample application.
* **Upgrade Comms to new WebRTC Platform** - Communications now uses a new WebRTC Library