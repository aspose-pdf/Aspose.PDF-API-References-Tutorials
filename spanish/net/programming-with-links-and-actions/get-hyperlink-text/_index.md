---
title: Obtener texto de hipervínculo
linktitle: Obtener texto de hipervínculo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a extraer texto de hipervínculo de un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 70
url: /es/net/programming-with-links-and-actions/get-hyperlink-text/
---

Aprenda a extraer texto de hipervínculos en un archivo PDF usando Aspose.PDF para .NET con esta guía paso a paso.

## Paso 1: Configuración del entorno

Asegúrese de haber configurado su entorno de desarrollo con un proyecto C# y las referencias de Aspose.PDF adecuadas.

## Paso 2: Cargar el archivo PDF

Establezca la ruta del directorio de sus documentos y cargue el archivo PDF usando el siguiente código:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Cargue el archivo PDF
Document document = new Document(dataDir + "input.pdf");
```

## Paso 3: Navegación por las páginas del documento

 Iterar a través de cada página del documento usando un`foreach` bucle:

```csharp
foreach(Page page in document.Pages)
{
     // Mostrar anotaciones de enlaces
     ShowLinkAnnotations(page);
}
```

## Paso 4: Manejo de errores

Agregue manejo de errores para capturar cualquier excepción y mostrar el mensaje de error correspondiente:

```csharp
catch (Exception ex)
{
     Console.WriteLine(ex.Message);
}
```

### Ejemplo de código fuente para Obtener texto de hipervínculo usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargue el archivo PDF
	Document document = new Document(dataDir + "input.pdf");
	// Iterar a través de cada página de PDF
	foreach (Page page in document.Pages)
	{
		// Mostrar anotación de enlace
		ShowLinkAnnotations(page);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

¡Felicidades! Ahora sabe cómo extraer texto de hipervínculo de un archivo PDF utilizando Aspose.PDF para .NET. Puede usar este conocimiento para manejar hipervínculos en sus proyectos y automatizar tareas relacionadas con archivos PDF.

Ahora que completó esta guía, puede aplicar estos conceptos a sus propios proyectos y seguir explorando las características que ofrece Aspose.PDF para .NET.