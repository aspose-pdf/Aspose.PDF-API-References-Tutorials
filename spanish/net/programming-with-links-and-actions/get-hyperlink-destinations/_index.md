---
title: Obtener destinos de hipervínculos
linktitle: Obtener destinos de hipervínculos
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a extraer destinos de hipervínculos de un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 60
url: /es/net/programming-with-links-and-actions/get-hyperlink-destinations/
---

Aspose.PDF para .NET es una poderosa biblioteca para manipular y extraer información de archivos PDF usando el lenguaje de programación C#. En este tutorial, nos centraremos en extraer destinos de hipervínculos de un archivo PDF utilizando Aspose.PDF para .NET.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo integrado (IDE) como Visual Studio.
- La biblioteca Aspose.PDF para .NET instalada en su máquina.

## Paso 1: Configuración del entorno de desarrollo

Antes de comenzar a escribir código, debe configurar su entorno de desarrollo creando un nuevo proyecto de C# en su IDE favorito.

## Paso 2: Importar referencias de Aspose.PDF

Para usar Aspose.PDF para .NET, debe agregar las referencias adecuadas a su proyecto. Siga los pasos a continuación para importar las referencias necesarias:

1. En su proyecto, haga clic derecho en "Referencias" y seleccione "Agregar referencia".
2. En la ventana "Agregar referencia", busque y seleccione los archivos DLL de Aspose.PDF para .NET.
3. Haga clic en "Aceptar" para importar las referencias a su proyecto.

## Paso 3: Cargar el archivo PDF

Antes de poder extraer destinos de hipervínculos, debe cargar el archivo PDF en su aplicación. Utilice el siguiente código para cargar el archivo PDF:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Cargue el archivo PDF
Document document = new Document(dataDir + "input.pdf");
```

Asegúrese de especificar la ruta correcta a su directorio de documentos y el archivo PDF que desea procesar.

## Paso 4: Navegación por las páginas del documento

Ahora que el archivo PDF está cargado, debe revisar todas las páginas del documento. Esto le permitirá obtener

Ir a las anotaciones de hipervínculos presentes en cada página. Use el siguiente código para iterar a través de las páginas del documento:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Obtener las anotaciones de enlaces de una página específica
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Crear una lista para almacenar todos los enlaces
     IList<Annotation> list = selector. Selected;
     // Recorra cada elemento de la lista
     foreach(LinkAnnotation a in list)
     {
         // Imprimir URL de destino
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Este código recorre cada página del documento y selecciona las anotaciones de hipervínculo presentes en cada página. Luego almacena estas anotaciones en una lista e imprime la URL de destino para cada enlace.

## Paso 5: Obtención de destinos de hipervínculos

El último paso es extraer los destinos del hipervínculo de las anotaciones del hipervínculo. El siguiente código te muestra cómo hacerlo:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Usa el destino como quieras
     }
}
```

En este código, obtenemos el destino de cada hipervínculo de las anotaciones del vínculo y almacenamos el destino en una variable. A continuación, puede utilizar este destino como desee en su aplicación.

### Ejemplo de código fuente para Obtener destinos de hipervínculos mediante Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargue el archivo PDF
	Document document = new Document(dataDir + "input.pdf");
	// Recorre toda la página del PDF
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Obtener las anotaciones de enlaces de una página en particular
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Crear lista con todos los enlaces
		IList<Annotation> list = selector.Selected;
		// Iterar a través del elemento individual dentro de la lista
		foreach (LinkAnnotation a in list)
		{
			// Imprime la URL de destino
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```