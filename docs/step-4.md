# Paso 4 - Lógica de envío de Preguntas previo a llamar a la API de Azure OpenAI

1. Editar el archivo ubicado en /Components/Pages/Home.razor, agrega después de la líena 16 el siguiente contenido:

```csharp
  private async Task GetResponseFromGPT3()
  {
      generatedText = "Buscando respuestas...";
  }
```

2. Editar el archivo ubicado en /Components/Pages/Home.razor, modificar la línea 7 con el siguiente contenido:

```csharp
<button class="btn btn-success mb-4 px-2" style="max-width:200px;" onclick="@GetResponseFromGPT3">Buscar respuesta</button>
```

3. Editar el archivo ubicado en /Components/Pages/Home.razor, agrega después de la línea 1 el siguiente contenido:

```csharp
@rendermode InteractiveServer
```
4. Levantar el proyecto

```
dotnet run
```