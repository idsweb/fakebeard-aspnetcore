# Basic structure
## Pages (Razor)
Contains the Razor pages and supporting files in pairs of .cshtml and .cshtml.cs. Supporting files are named with an underscore. [See link](https://docs.microsoft.com/en-us/aspnet/core/tutorials/razor-pages/razor-pages-start?view=aspnetcore-3.1&tabs=visual-studio#pages-folder)
## wwwroot
This folder contains static files
## appSettings.json
Contains configuration data, such as connection strings. See [this link](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/configuration/?view=aspnetcore-3.1#appsettingsjson)

__CreateDefaultBuilder__ provides default configuration for the app.

The default [JsonConfigurationProvider](https://docs.microsoft.com/en-us/dotnet/api/microsoft.extensions.configuration.json.jsonconfigurationprovider?view=dotnet-plat-ext-3.1) loads configuration in the following order:
1. appsettings.json
2. appsettings.Environment.json

```json
{
  "Position": {
    "Title": "Editor",
    "Name": "Joe Smith"
  }
}
```csharp
public class TestModel : PageModel
{
    // requires using Microsoft.Extensions.Configuration;
    private readonly IConfiguration Configuration;

    public TestModel(IConfiguration configuration)
    {
        Configuration = configuration;
    }

    public ContentResult OnGet()
    {
        var title = Configuration["Position:Title"];
        var name = Configuration["Position:Name"];
        
        return Content($"Title: {title} \n" +
                       $"Name: {name}");
    }
}
```
## program.cs
Contains the entry point for the program. For more information.
```csharp
    public class Program
    {
        public static void Main(string[] args)
        {
            CreateHostBuilder(args).Build().Run();
        }

        public static IHostBuilder CreateHostBuilder(string[] args) =>
            Host.CreateDefaultBuilder(args)
                .ConfigureWebHostDefaults(webBuilder =>
                {
                    webBuilder.UseStartup<Startup>();
                });
    }
```
The host is an object that encapsulates an app's resources, such as:

* Dependency injection (DI)
* Logging
* Configuration
* IHostedService implementations