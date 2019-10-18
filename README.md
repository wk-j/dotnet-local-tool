## .NET Local Tool

```bash
dotnet new tool-manifest
dotnet tool install dotnet-outdated
dotnet dotnet-outdated src/MyApp/MyApp.csproj
```

*Pack*

```bash
dotnet pack src/MyApp --output .publish /p:Version=1.0.1

dotnet pack src/MyApp \
    /p:PackAsTool=true \
    /p:ToolCommandName=wk-my-app \
    /p:PackageId=wk.MyApp \
    /p:Version=1.0.2 \
    --output .publish

dotnet tool install wk.MyApp \
    --add-source .publish

dotnet tool uninstall wk.MyApp

dotnet wk-my-app
```