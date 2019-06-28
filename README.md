# unblocked platform
The unblocked platform is a distributed computing platform which uses WebAssembly, dotnet core, Microsoft Blazor, WebRTC and IndexedDB to deliver a rapid app development solution for distributed applications.

## What are distributed applications?
Distributed applications are a part of Web 3.0 and allow the development of fully featured multi-user applications without the need for central server infrastructure.

## Why would I care?
Writing distributed applications on the unblocked platform is super simple, they scale enormously, offer world class security and require almost no investment to run.

## How do I start?
The following 5 steps will help you get started.
1. Install the latest [.NET Core 3.0 Preview SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0) Release.
2. Install the Blazor templates by running the following command in a command shell:
    ```
    dotnet new -i Microsoft.AspNetCore.Blazor.Templates::3.0.0-preview6.19307.2
    ```
3. Follow the guidance for your choice of tooling
    1. For Visual Studio:
        1. Install the latest Visual Studio preview with the **ASP.NET and web development** workload
        2. Install the latest Blazor extension from the Visual Studio Marketplace
        3. Install the latest unblocked platform extension from the Visual Studio Marketplace
        4. Create a new project
        5. Select Unblocked Community Edition Project
        6. Provide a project name in the **Project name** field or accept the default project name. Confirm the Location entry is correct or provide a location for the project. Select **Create**.
        7. Press **F5** to run the app.
    2. For Visual Studio Code
        1. Install Visual Studio Code.
        2. Install the latest C# for Visual Studio Code extension.
        3. Execute the following command from a command shell:
            ```
                dotnet new blazor -o WebApplication1
            ```
        4. Open the WebApplication1 folder in Visual Studio Code.
        5. Execute dotnet run from the app's project folder.
        6. In a browser, navigate to https://localhost:5001.
    3. For .Net Core CLI
        1. Execute the following commands from a command shell
            ```
            dotnet new blazor -o WebApplication1
            cd WebApplication1
            dotnet run
            ```

Multiple pages are available from tabs in the sidebar:
* Home
* Counter
* Fetch Data

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
Read our product documentation here.
