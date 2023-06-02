---
title: Obtener recuento de páginas
linktitle: Obtener recuento de páginas
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para obtener el recuento de páginas de un archivo PDF utilizando Aspose.PDF para .NET. Fácil de seguir e implementar en tus proyectos.
type: docs
weight: 80
url: /es/net/programming-with-pdf-pages/get-page-count/
---
En este tutorial, lo guiaremos a través del proceso paso a paso para obtener el recuento de páginas de un archivo PDF utilizando Aspose.PDF para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo obtener el recuento de páginas de un archivo PDF utilizando Aspose.PDF para .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:

- Un conocimiento básico del lenguaje de programación C#
- Aspose.PDF para .NET instalado en su entorno de desarrollo

## Paso 1: crear una instancia de un objeto de documento
Primero, debe crear una instancia de un objeto Documento utilizando la clase Documento de Aspose.PDF.

```csharp
Document doc = new Document();
```

## Paso 2: Agregar una página al documento
 Luego puede agregar una página al documento usando el`Add()` método de la colección Pages del documento.

```csharp
Page page = doc.Pages.Add();
```

## Paso 3: Crea el contenido de la página
Ahora puede crear contenido de página agregando objetos TextFragment a la colección Paragraphs del objeto Page. En este ejemplo, agregamos un TextFragment repetido 300 veces para simular un documento con contenido más extenso.

```csharp
for (int i = 0; i < 300; i++)
page.Paragraphs.Add(new TextFragment("Page count test"));
```

## Paso 4: procesamiento de párrafos y obtención del número de páginas
 Una vez que haya agregado el contenido a la página, debe procesar los párrafos del documento llamando al`ProcessParagraphs()` método. Esto permite que Aspose.PDF calcule el número de páginas con precisión.

```csharp
doc.ProcessParagraphs();
```

## Paso 5: Mostrar el número de páginas
 Finalmente, puede ver el número de páginas del documento accediendo a la`Count` propiedad de la colección Pages.

```csharp
Console.WriteLine("Number of pages in document = " + doc.Pages.Count);
```

### Ejemplo de código fuente para Obtener recuento de páginas con Aspose.PDF para .NET 

```csharp

// Instanciar instancia de documento
Document doc = new Document();
// Agregar página a la colección de páginas del archivo PDF
Page page = doc.Pages.Add();
// Crear instancia de bucle
for (int i = 0; i < 300; i++)
	// Agregue TextFragment a la colección de párrafos del objeto de página
	page.Paragraphs.Add(new TextFragment("Pages count test"));
// Procese los párrafos en un archivo PDF para obtener un recuento de páginas preciso
doc.ProcessParagraphs();
// Imprimir número de páginas en el documento
Console.WriteLine("Number of pages in document = " + doc.Pages.Count);

```

## Conclusión
En este tutorial, aprendimos cómo obtener el recuento de páginas de un archivo PDF usando Aspose.PDF para .NET. Siguiendo los pasos descritos anteriormente, puede implementar fácilmente esta funcionalidad en sus propios proyectos. Siéntase libre de explorar más la documentación de Aspose.PDF para descubrir otras características útiles para trabajar con archivos PDF.
