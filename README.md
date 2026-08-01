# Comunicação entre Service e Interface

[← Voltar](https://github.com/joycequoos/Controllers_Services/blob/main/README.md)

Passo para registrar a comunicação entre a interface `IAutorInterface` e a classe `AutorService` dentro do arquivo `Program.cs`, através da injeção de dependência.

## Registrando a Comunicação no Program.cs

Para que a interface `IAutorInterface` e a implementação `AutorService` se comuniquem, é necessário registrá-las no container de injeção de dependência da aplicação, no arquivo `Program.cs`.

![Comunicação entre Service e Interface](https://github.com/joycequoos/Controllers_Services/blob/main/img/01_Comunicacao_Services_Interface.png)

```csharp
builder.Services.AddScoped<IAutorInterface, AutorService>();
```

Esse registro informa ao ASP.NET Core que, sempre que a interface `IAutorInterface` for solicitada (por exemplo, no construtor de um Controller), o framework deve fornecer uma instância da classe `AutorService`. O escopo `Scoped` garante que cada requisição HTTP receba sua própria instância do serviço.
