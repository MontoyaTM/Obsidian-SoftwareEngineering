---
complete: false
tags:
  - Blazor
links:
---
# What is Blazor?

Blazor is a component based <span style="color:rgb(132, 255, 0)">Single Page Application</span> (SPA) web framework from Microsoft that lets you build interactive web apps using C#.

- Built from reusable pieces called components
- UI (HTML)
- Logic (C#)
- State Management (C#)

## Pros:

- Full-stack C#
- Strong typing (no runtime JS errors)
- Shared models between frontend/backend
- EF Core ready
- Component based

## Cons: 

- Smaller ecosystem
- Some JS still needed (interop)
- WASM slow start time


![[Web Server.svg]]


``` run-csharp
<h1>Hello, @name!</h1>

@code {
    private string name = "MontoyaTM";
}
```

# Choices of Interactivity:

In modern Blazor (especially .NET 8/9/10), **interactivity is not one-size-fits-all anymore**. You can choose _how each component becomes interactive_.

Think of it like this:

> **SSR renders HTML → interactivity “wakes it up”**

## Static Server-side Rendering

- HTML is rendered once on the server
- No events (<span style="color:rgb(181, 98, 249)">@onclick</span> won't work)
- Login/Register pages
- Landing Pages
- SEO Content

``` run-csharp
(no @rendermode)
```

![[Static SSR.svg]]
## Interactive Server

Runs on the server using a real-time connection (<span style="color:rgb(181, 98, 249)">SignalR</span>)

> UI is rendered → connection opens → events handled on server

- Fast load
- Small payload
- Great for dashboards
- Requires constant connection

``` run-csharp
@rendermode InteractiveServer
```

![[Interactivity.svg ]]

![[InteractiveServer.svg]]
## Interactive WebAssembly (WASM)

Blazor WebAssembly allows your application to run entirely inside the client’s browser, making it a direct alternative to JavaScript SPA (single-page application) frameworks.

> Downloads .NET runtime → runs C# client-side

- Works offline
- No server round-trips after load
- Large initial download
- Slower startup
- Client-heavy apps

``` run-csharp
@rendermode InteractiveWebAssembly
```


![[WebAssembly.svg]]
## Interactive Auto (Hybrid)

Blazor Hybrid is built on technology from the .NET MAUI framework and allows developers to use Blazor to write cross-platform desktop applications.

---
Referencnes: