---
slug: build
title: Start Building Blazor application
author: Andrew Chan
author_title: Analyst Programmer @ ASL
author_url: https://github.com/chanandrew96
author_image_url: https://avatars.githubusercontent.com/u/12830221?s=400&v=4
tags: [docusaurus, blazor]
---

開始建立Blazor Application的學習筆記

依賴: .Net Core 5
先到Micorsoft官方網站下載.Net SDK 5安裝，安裝完成後開啟Console輸入```dotnet``` 來驗證安裝是否順利完成
使用```dotnet new blazorserver -o [Application Name] --no-https``` 指令來建立Blazor Application Project
-   Program.cs is the entry point for the app that starts the server.
-   Startup.cs is where you configure the app services and middleware.
-   App.razor is the root component for the app.
-   The BlazorApp/Pages directory contains some example web pages for the app.
-   BlazorApp.csproj defines the app project and its dependencies.

使用```dotnet watch run```指令來開始Build & Start Blazor Application
當程式碼更新時，watch會自動更新程式
預設的Project會以```/Pages/Index.razor```為主頁

跳至Counter頁面，可以看到有一個Button
在Blazor當中，Counter的Method可以使用C#來完成
使用``` @code { } ```來包住C#的Code，然後Button的@onClick Event可以直接呼叫C#的Method
而直接使用C#中的Varibles時需要在HTML中加上@在Varibles前，如呼叫C#的``` currentCount ``` 則使用 ``` @currentCount ```

每個以.razor為副檔名的檔案都可以視為一個可重用的UI Element
因此，我們可以在其他頁面加上``` <Counter /> ```來將Counter.razor的內容加上

在C# Parameter前加上```[Parameter]```可以將該Parameter轉為一個Public Property
Public Property可以在使用razor file as UI Element時加上Property定義，如
```
// Counter.razor
@code {
    [Parameter]
    public int IncrementAmount { get; set; } = 1;
}
// Index.razor
<Counter IncrementAmount="10" />
```

在.razor檔案中，我們可以Inject C#檔案以在@code段落中使用其他程式碼
```
@using [namespace]
@inject [ClassName] [Local Define Object Name]
```

同時，我們可以結合C# Code與UI Elemet用於Render頁面，例如
```
@if (name == null) {
    <p><em>Loading...</em></p>
} else {
    <table class="table">
        <thead>
            <tr>
                <th>Date</th>
                <th>Temp. (C)</th>
                <th>Temp. (F)</th>
                <th>Summary</th>
            </tr>
        </thead>
        <tbody>
            @foreach (var forecast in forecasts)
            {
                <tr>
                    <td>@forecast.Date.ToShortDateString()</td>
                    <td>@forecast.TemperatureC</td>
                    <td>@forecast.TemperatureF</td>
                    <td>@forecast.Summary</td>
                </tr>
            }
        </tbody>
    </table>
}

@code {
    private WeatherForecast[] forecasts;
}
```

使用 ```@* ... *@```來Comment @code中的程式碼

當使用 ```Console.WriteLine("")```時，在Blazor WebAssembly中可以在Browser Console中Print Log，而Blazor Server App則會在Output Window中打印
如想要在Server上打印至Browser，可參考[此文](https://newbedev.com/how-can-i-write-into-the-browsers-console-via-blazor-webassembly)

[Expression body  definition](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/lambda-operator#expression-body-definition)
在C#中，我們可以使用```=>```來定義Parameter，如
```
// member => expression;
public override string ToString() => $"{fname} {lname}".Trim();
private string NavMenuCssClass => collapseNavMenu ? "collapse" : null;
```

在Properties資料夾下，我們可以找到launchSettings.json，當中定義了不同的設定檔
在預設的Project中，我們在"BlazorApp"的設定下可以找到"applicationUrl"以定義程式使用哪一個Port位開啟


[Ref](https://dotnet.microsoft.com/learn/aspnet/blazor-tutorial/intro)
[ASP.Net Core Blazor Ref](https://docs.microsoft.com/en-us/aspnet/core/blazor/?WT.mc_id=dotnet-35129-website&view=aspnetcore-5.0)

[Next: Build API using ASP.Net Core](https://docs.microsoft.com/en-us/learn/modules/build-web-api-aspnet-core/?WT.mc_id=dotnet-35129-website)
[Next: Publish & Deployment & API](https://docs.microsoft.com/en-us/learn/modules/publish-app-service-static-web-app-api-dotnet/?WT.mc_id=dotnet-35129-website&source=learn)