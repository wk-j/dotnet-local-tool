## .NET Local Tool

```bash
dotnet new tool-manifest
dotnet tool install dotnet-outdated
dotnet dotnet-outdated src/MyApp/MyApp.csproj
```

*Pack*

```bash
dotnet new console --language C# --output sr/MyApp

dotnet pack src/MyApp \
    /p:PackAsTool=true \
    /p:ToolCommandName=wk-my-app \
    /p:PackageId=wk.MyApp \
    /p:Version=1.0.2 \
    --output .publish

dotnet new tool-manifest

dotnet tool install wk.MyApp \
    --add-source .publish

dotnet wk-my-app

dotnet tool uninstall wk.MyApp
```