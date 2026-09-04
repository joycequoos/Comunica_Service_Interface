# Communication between Service and Interface

[← Back](https://github.com/joycequoos/Controllers_Services/blob/main/README.md)

Step to register the communication between the `IAutorInterface` interface and the `AutorService` class within the `Program.cs` file, through dependency injection.

## Registering the Communication in Program.cs

For the `IAutorInterface` interface and the `AutorService` implementation to communicate, they need to be registered in the application's dependency injection container, in the `Program.cs` file.

[![Communication between Service and Interface](https://github.com/joycequoos/Controllers_Services/raw/main/img/01_Comunicacao_Services_Interface.png)](https://github.com/joycequoos/Controllers_Services/blob/main/img/01_Comunicacao_Services_Interface.png)

```
builder.Services.AddScoped<IAutorInterface, AutorService>();
```

This registration tells ASP.NET Core that whenever the `IAutorInterface` interface is requested (for example, in a Controller's constructor), the framework should provide an instance of the `AutorService` class. The `Scoped` lifetime ensures that each HTTP request receives its own instance of the service.
