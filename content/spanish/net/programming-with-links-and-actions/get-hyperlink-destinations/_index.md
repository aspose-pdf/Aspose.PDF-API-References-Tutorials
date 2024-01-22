---
title: Obtenga destinos de hipervínculos en un archivo PDF
linktitle: Obtenga destinos de hipervínculos en un archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a extraer destinos de hipervínculos en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 60
url: /es/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF para .NET es una poderosa biblioteca para manipular y extraer información en archivos PDF utilizando el lenguaje de programación C#. En este tutorial, nos centraremos en extraer destinos de hipervínculos de un archivo PDF utilizando Aspose.PDF para .NET.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo integrado (IDE) como Visual Studio.
- La biblioteca Aspose.PDF para .NET instalada en su máquina.

## Paso 1: configurar el entorno de desarrollo

Antes de comenzar a escribir código, debe configurar su entorno de desarrollo creando un nuevo proyecto C# en su IDE favorito.

## Paso 2: Importar referencias de Aspose.PDF

Para utilizar Aspose.PDF para .NET, debe agregar las referencias adecuadas a su proyecto. Siga los pasos a continuación para importar las referencias necesarias:

1. En su proyecto, haga clic derecho en "Referencias" y seleccione "Agregar referencia".
2. En la ventana "Agregar referencia", busque y seleccione los archivos DLL de Aspose.PDF para .NET.
3. Haga clic en "Aceptar" para importar las referencias a su proyecto.

## Paso 3: cargar el archivo PDF

Antes de poder extraer destinos de hipervínculos, debe cargar el archivo PDF en su aplicación. Utilice el siguiente código para cargar el archivo PDF:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Cargue el archivo PDF
Document document = new Document(dataDir + "input.pdf");
```

Asegúrese de especificar la ruta correcta a su directorio de documentos y al archivo PDF que desea procesar.

## Paso 4: Navegar por las páginas del documento

Ahora que el archivo PDF está cargado, debe revisar todas las páginas del documento. Esto le permitirá obtener

Vaya a las anotaciones de hipervínculos presentes en cada página. Utilice el siguiente código para recorrer las páginas del documento:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Obtener las anotaciones de enlaces de una página específica.
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Crea una lista para almacenar todos los enlaces.
     IList<Annotation> list = selector. Selected;
     // Recorre cada elemento de la lista.
     foreach(LinkAnnotation a in list)
     {
         // Imprimir URL de destino
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Este código recorre cada página del documento y selecciona las anotaciones de hipervínculo presentes en cada página. Luego almacena estas anotaciones en una lista e imprime la URL de destino para cada enlace.

## Paso 5: Obtener destinos de hipervínculos

El último paso es extraer los destinos de los hipervínculos de las anotaciones de hipervínculos. El siguiente código le muestra cómo hacerlo:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Usa el destino como desees
     }
}
```

En este código, obtenemos cada destino de hipervínculo de las anotaciones del enlace y almacenamos el destino en una variable. Luego podrá utilizar este destino como desee en su aplicación.

### Código fuente de muestra para obtener destinos de hipervínculos usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargue el archivo PDF
	Document document = new Document(dataDir + "input.pdf");
	// Recorre toda la página del PDF.
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Obtenga las anotaciones de enlaces de una página en particular.
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Crear una lista que contenga todos los enlaces.
		IList<Annotation> list = selector.Selected;
		// Iterar a través de un elemento individual dentro de la lista
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

### Preguntas frecuentes para obtener destinos de hipervínculos en un archivo PDF

#### P: ¿Qué es el destino de un hipervínculo en un archivo PDF?

R: El destino de un hipervínculo en un archivo PDF es una ubicación o destino específico al que apunta un hipervínculo. Podría ser una URL, una página dentro del mismo documento o un documento externo.

#### P: ¿Cómo puede beneficiar el análisis de mi documento PDF la extracción de destinos de hipervínculos?

R: La extracción de destinos de hipervínculos le permite identificar y catalogar todos los destinos a los que apuntan los hipervínculos dentro de un documento PDF. Esta información puede resultar útil para la validación de contenido, la verificación de enlaces y el análisis de datos.

#### P: ¿Cómo ayuda Aspose.PDF para .NET a extraer destinos de hipervínculos?

R: Aspose.PDF para .NET proporciona potentes API para extraer destinos de hipervínculos con facilidad. Este tutorial muestra paso a paso cómo extraer destinos de hipervínculos usando C#.

#### P: ¿Puedo extraer selectivamente destinos de hipervínculos según ciertos criterios?

R: Sí, puede extraer selectivamente destinos de hipervínculos recorriendo las páginas del documento PDF y filtrando las anotaciones de hipervínculo deseadas según sus criterios.

#### P: ¿Es posible extraer destinos de hipervínculos de documentos PDF protegidos con contraseña?

R: Aspose.PDF para .NET puede extraer destinos de hipervínculos de documentos PDF protegidos con contraseña siempre que proporcione las credenciales de autenticación necesarias al abrir el documento.

#### P: ¿Cómo puedo utilizar los destinos de hipervínculos extraídos en mi aplicación?

R: Una vez que haya extraído los destinos de los hipervínculos, puede usarlos para realizar diversas acciones, como validar las URL de los enlaces, crear informes o implementar una navegación personalizada.

#### P: ¿Existe alguna limitación al extraer destinos de hipervínculos?

R: Si bien la extracción del destino del hipervínculo es poderosa, es esencial considerar la estructura del documento PDF. Los hipervínculos integrados en gráficos complejos o contenido multimedia pueden requerir un manejo adicional.

#### P: ¿Puedo extraer otros atributos de los hipervínculos, como tipos de vínculos o coordenadas?

R: El tutorial se centra en extraer destinos de hipervínculos. Sin embargo, puede consultar la documentación oficial de Aspose.PDF para explorar funciones avanzadas, incluida la extracción de tipos de enlaces y coordenadas.