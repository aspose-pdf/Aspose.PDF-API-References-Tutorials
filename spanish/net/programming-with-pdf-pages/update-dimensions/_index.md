---
title: Actualizar dimensiones
linktitle: Actualizar dimensiones
second_title: Referencia de API de Aspose.PDF para .NET
description: Guía paso a paso para actualizar las dimensiones de la página PDF usando Aspose.PDF para .NET. Consulta las dimensiones según tus necesidades.
type: docs
weight: 150
url: /es/net/programming-with-pdf-pages/update-dimensions/
---
En este tutorial, lo guiaremos a través del proceso paso a paso para actualizar las dimensiones de la página en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo cambiar las dimensiones de la página en un documento PDF utilizando Aspose.PDF para .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:

- Un conocimiento básico del lenguaje de programación C#
- Aspose.PDF para .NET instalado en su entorno de desarrollo

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento PDF editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Abra el documento PDF
 Luego puede abrir el documento PDF existente usando el`Document` clase de Aspose.PDF. Asegúrese de especificar la ruta correcta del documento.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Paso 3: obtener la colección de páginas
 Ahora puede acceder a la colección de páginas del documento PDF usando el`Pages` propiedad de la`Document` clase.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Paso 4: Obtener una página específica
Luego puede seleccionar una página específica del documento usando el índice de la página en la colección. En este ejemplo, estamos usando la segunda página (índice 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Paso 5: Definir las nuevas dimensiones de la página
 Ahora puede configurar el nuevo tamaño de página usando el`SetPageSize()` metodo de la`Page` objeto. En este ejemplo, estamos configurando las dimensiones de la página en A4 (11,7 x 8,3 pulgadas), convertidas en puntos (1 pulgada = 72 puntos).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Paso 6: Guarde el documento actualizado
Finalmente, puede guardar el documento PDF actualizado en un archivo usando el`Save()` metodo de la`Document`clase. Asegúrese de especificar la ruta y el nombre de archivo correctos.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Ejemplo de código fuente para Actualizar dimensiones usando Aspose.PDF para .NET 

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Obtener colección de páginas
PageCollection pageCollection = pdfDocument.Pages;
// Obtener página particular
Page pdfPage = pageCollection[1];
// Establezca el tamaño de la página como A4 (11,7 x 8,3 pulgadas) y en Aspose.Pdf, 1 pulgada = 72 puntos
// Entonces las dimensiones A4 en puntos serán (842.4, 597.6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Guardar el documento actualizado
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Conclusión
En este tutorial, aprendimos cómo actualizar las dimensiones de una página en un documento PDF utilizando Aspose.PDF para .NET. Siguiendo esta guía paso a paso, puede cambiar fácilmente las dimensiones de una página en un documento PDF según sea necesario. Aspose.PDF ofrece una API potente y flexible para trabajar con archivos PDF y realizar diversas manipulaciones, incluido el cambio de dimensiones de página. Con este conocimiento, puede controlar y personalizar las dimensiones de sus páginas PDF para satisfacer sus necesidades específicas.
