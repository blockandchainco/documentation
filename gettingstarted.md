![Logo](./img/UPWT.png)
# Getting Started
Follow the simple process below to get started with the Unblocked platform



The following 5 steps will help you get started.
1. Install the latest [.NET Core 3.0 Preview SDK](https://aka.ms/netcore3download) Release.
2. Install the Blazor templates by running the following command in a command shell:
    ```
    dotnet new -i Microsoft.AspNetCore.Blazor.Templates::3.0.0-preview7.19365.7
    ```
3. Follow the guidance for your choice of tooling
    1. For Visual Studio:
        1. Install the latest [Visual Studio preview](https://visualstudio.microsoft.com/vs/preview/) with the **ASP.NET and web development** and **.NET Core cross-platform development** workload. Note, the Unblocked Platform only works on Visual Studio 2019 16.3 Preview 1, which is now available.
        2. Install the latest [Unblocked Platform extension](https://marketplace.visualstudio.com/items?itemName=BlockandChainCompany.unblocked-v1) from the Visual Studio Marketplace
        3. In Visual Studio 2019 Preview, Create a new project
        4. Select **unblocked-platform**, the Unblocked Platform Starter Project.
        5. Provide a project name in the **Project name** field or accept the default project name. Confirm the Location entry is correct or provide a location for the project. Select **Create**.
        6. Obtain a new Application Certificate by completing the [online form here](https://bcpayments.azurewebsites.net/application).
           1. Click Order Certificate
           2. Download and save the PFX file
           3. The Certificate Name is in the format "CN=\<ApplicationID\>, CN=\<PlatformID\>, NC=unblocked, CN=io. Make a note of the Application ID.
           4. In the Application's Environment Folder, Open config.dev.json and amend the AppID field to eb the new Application ID from step 6.3 above.
           5. Now edit the config.prod.json folder to include the new application id.
        7. Press **F5** to run the app.
        8. Navigate to the **Address Management** page, and click here under "If you need a certificate for this application" at the top of the page.
           1. Complete the form and choose **order certificate**
           2. Click **Download PFX** and save the file to your hard drive
           3. Close the BC.Payment Portal Tab
        9. CLick **Browse** and upload the new certificate
        10. Type the passphrase you entered in Step 8.1 and click **Upload**
        11. The Application is now operational and running on your own distributed ledger.
    2. For Visual Studio Code *NOTE: Visual Studio Code Support is not yet available*
    3. For .Net Core CLI *NOTE: CLI Support is not yet aviailable*
    

Multiple pages are available from tabs in the sidebar:
* **Home** - This is the default page from the Blazor Template, with the addition of the User Interface for the Unblocked platform node.
* **Counter** - This is a default page from the Blazor Template showing a counter.
* **Fetch Data** - This page shows the ability of the unblocked platform to persist and send data peer to peer.
* **Address Management** - This page shows how to manage the X509 Certificates that secure the unblocked platform.

You can see the status of the unblocked node at the bottom of each page.


On the Counter page, select the Click me button to increment the counter without a page refresh. Incrementing a counter in a webpage normally requires writing JavaScript, but Razor components provide a better approach using C#.

```csharp
@page "/counter"

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button class="btn btn-primary" @onclick="@IncrementCount">Click me</button>

@code {
    private int currentCount = 0;

    private void IncrementCount()
    {
        currentCount++;
    }
}
```
*Pages/Counter.razor*

A request for ```/counter``` in the browser, as specified by the ```@page``` directive at the top, causes the Counter component to render its content. Components render into an in-memory representation of the render tree that can then be used to update the UI in a flexible and efficient way.

Each time the Click me button is selected:

* The ```onclick``` event is fired.
* The ```IncrementCount``` method is called.
* The ```currentCount``` is incremented.
* The component is rendered again.


The runtime compares the new content to the previous content and only applies the changed content to the Document Object Model (DOM).

Add a component to another component using HTML syntax. For example, add the Counter component to the app's homepage by adding a <Counter /> element to the Index component.

*Pages/Index.razor*:

```Cs

@page "/"

<h1>Hello, world!</h1>

Welcome to your new app.

<Counter />
```
Run the app. The homepage has its own counter provided by the Counter component.

Component parameters are specified using attributes or child content, which allow you to set properties on the child component. To add a parameter to the Counter component, update the component's @code block:

Add a property for IncrementAmount with a [Parameter] attribute.
Change the IncrementCount method to use the IncrementAmount when increasing the value of currentCount.


*Pages/Counter.razor*:
```cs
@page "/counter"

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button class="btn btn-primary" @onclick="@IncrementCount">Click me</button>

@code {
    private int currentCount = 0;

    [Parameter]
    private int IncrementAmount { get; set; } = 1;

    private void IncrementCount()
    {
        currentCount += IncrementAmount;
    }
}
```

Specify the IncrementAmount in the Index component's ```<Counter>``` element using an attribute.

*Pages/Index.razor*:

```cs
@page "/"

<h1>Hello, world!</h1>

Welcome to your new app.

<Counter IncrementAmount="10" />
```

Run the app. The Index component has its own counter that increments by ten each time the Click me button is selected. The Counter component (Counter.razor) at /counter continues to increment by one.

## How do I deliver the application to my users?
We support multiple ways to deliver an unblocked application. You can host the application in any of the major cloud providers or indeed in any fixed file based web services such as github pages. Read below to learn how to do this.

## Where do I find out more?
Read our product documentation [here](https://blockandchainco.github.io/API/).
