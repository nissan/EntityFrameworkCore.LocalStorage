﻿# Entity Framework Core Local Storage

[![nuget](https://img.shields.io/nuget/v/EntityFrameworkCore.LocalStorage.svg)](https://www.nuget.org/packages/Blazor.EntityFrameworkCore.LocalStorage/) ![Downloads](https://img.shields.io/nuget/dt/EntityFrameworkCore.LocalStorage.svg "Downloads")

Ideal for use in Blazor Web Assembly

## Installation

### NuGet
```
PM> Install-Package EntityFrameworkCore.LocalStorage
```

### .Net CLI
```
> dotnet add package EntityFrameworkCore.LocalStorage
```
## Example
* [Local Storage Example](https://eflocalstorage.azurewebsites.net)

## Usage

```
services.AddDbContext<AppDbContext>(options =>
{
	options.UseLocalStorageDatabase(services.GetJSRuntime(), databaseName: "db");
});
```

```
services.AddDbContext<AppDbContext>(options =>
{
	//As the encryption happens on the client side this is NOT secure but is handy for preventing users from altering data via browser tools.
	options.UseLocalStorageDatabase(services.GetJSRuntime(), databaseName: "db", password: "password");
});
```

```
<PropertyGroup>
  <BlazorWebAssemblyEnableLinking>true</BlazorWebAssemblyEnableLinking>
</PropertyGroup>
```

```
<?xml version="1.0" encoding="UTF-8" ?>
<!--
  This file specifies which parts of the BCL or Blazor packages must not be
  stripped by the IL Linker even if they aren't referenced by user code.
-->
<linker>
  <assembly fullname="System.Core" /> 
</linker>
```

## Authors

* **Dave Ikin** - [davidikin45](https://github.com/davidikin45)

## License

This project is licensed under the MIT License

## Tools

* [Chrome Local Storage Explorer](https://chrome.google.com/webstore/detail/local-storage-explorer/hglfomidogadbhelcfomenpieffpfaeb)

## Acknowledgments

* [Blazor](https://dotnet.microsoft.com/apps/aspnet/web-apps/blazor)
* [FileContextCore](https://github.com/morrisjdev/FileContextCore)
* [Blazored LocalStorage](https://github.com/Blazored/LocalStorage)
* [Reshiru.Blazor.IndexedDB.Framework](https://github.com/Reshiru/Blazor.IndexedDB.Framework)