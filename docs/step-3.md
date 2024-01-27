# Paso 3 - Creación de formulario en Blazor para el Chat.

1. Editar el archivo ubicado en /Components/Pages/Home.razor, modificar el contenido con el siguiente:
```
@page "/" 
<PageTitle>Chat GPT - Blazor WASM - TCD 2024</PageTitle>
<div class="h1 mb-4 text-center"> Bienvenido a Chat GPT desarrollado con Blazor Web Assembly </div>
<div style="line-height:40px;" class="h4 mb-4 text-center"> Aquí puedes buscar realizar una pregunta sobre el Tech Community Day 2024, horarios e información de los conferencistas. </div>
<div class="form-group text-center">
  <input class="form-control my-4 text-center py-2 m-auto" style="max-width:600px;" type="text" placeholder="Escribe tu mensaje aquí" />
  <button class="btn btn-success mb-4 px-2" style="max-width:200px;" >Buscar respuesta</button>
</div>
<div class="d-flex justify-content-center text-center">
  <div style="min-width:600px; min-height:260px; max-width:700px;" class="mt-2container border border-1 rounded-2 p-3 text-center"></div>
</div>
```

2. Instalación de OpenAI desde la terminal ejecutar el siguiente comando:

```
dotnet add package Azure.AI.OpenAI --version 1.0.0-beta.12
```

3. Instalación de Newtonsoft.JSON desde la terminal ejecutar el siguiente comando:

```
dotnet add package Newtonsoft.Json --version 13.0.3
```

4. Editar el archivo ubicado en /Components/Pages/Home.razor, agregar después de la línea 12 el siguiente bloque:

```csharp
@code {
  public string message { get; set; }
  public string generatedText { get; set; } = "La respuesta se mostrará aquí.";
  private readonly HttpClient _httpClient = new HttpClient();
}

```

5. Editar el archivo ubicado en /Components/Pages/Home.razor, modifica la línea 6 con el siguiente contenido:

```csharp
<input class="form-control my-4 text-center py-2 m-auto" style="max-width:600px;" type="text" @bind="@message" placeholder="Escribe tu mensaje aquí" />
```

6. Editar el archivo ubicado en /Components/Pages/Home.razor, modifica la línea 10 con el siguiente contenido:

```csharp
<div style="min-width:600px; min-height:260px; max-width:700px;" class="mt-2container border border-1 rounded-2 p-3 text-center">@generatedText</div>
```

7. Levantar el proyecto

```
dotnet run
```