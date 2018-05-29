# CarPool

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 6.0.5.

## Requirements

1.  Visual Studio 2017 ( at least 15.7.2)
2.  dot net core sdk 2.1.300 preview 2 or latest
3.  Node 8 or latest
4.  Angular-cli 6 or above

## Development server

```bash
$>__ dotnet build
$>__ dotnet run
```

## Steps to integrate in dotnet core

1.  Create new web project and choose api (.net core version should be 2.1 or above)
2.  Add these lines to **Startup.cs**

```cs
// add in config section
app.UseDefaultFiles();
app.UseStaticFiles();
```

3.  Create angular project with same name (src should be in root of dotnet project)

```bash
# outside dotnet project folder
$>__ ng new "name-of-dotnet-project-folder" --skip-tests --routing
```

4.  Add these config rules to dotnet project .csproj file inside PropertyGroup

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp2.1</TargetFramework>
  <TypeScriptToolsVersion>2.7.2</TypeScriptToolsVersion>
  <TypeScriptCompileBlocked>true</TypeScriptCompileBlocked>
  <PostBuildEvent>ng build --aot</PostBuildEvent>
</PropertyGroup>
```

5.  Edit angular.json file and set the outputPath to wwwroot.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
