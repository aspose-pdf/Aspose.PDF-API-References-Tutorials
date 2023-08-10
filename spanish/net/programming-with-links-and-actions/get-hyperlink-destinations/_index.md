---
title: Obtener destinos de hipervínculos en archivo PDF
linktitle: Obtener destinos de hipervínculos en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a extraer destinos de hipervínculos en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 60
url: /es/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF para .NET es una poderosa biblioteca para manipular y extraer información en un archivo PDF usando el lenguaje de programación C#. En este tutorial, nos centraremos en extraer destinos de hipervínculos de un archivo PDF utilizando Aspose.PDF para .NET.

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

### Preguntas frecuentes para obtener destinos de hipervínculos en un archivo PDF

#### P: ¿Qué es un destino de hipervínculo en un archivo PDF?

R: Un destino de hipervínculo en un archivo PDF es una ubicación u objetivo específico al que apunta un hipervínculo. Podría ser una URL, una página dentro del mismo documento o un documento externo.

#### P: ¿Cómo puede beneficiar la extracción de destinos de hipervínculos el análisis de mi documento PDF?

R: La extracción de destinos de hipervínculos le permite identificar y catalogar todos los destinos a los que apuntan los hipervínculos dentro de un documento PDF. Esta información puede ser útil para la validación de contenido, la verificación de enlaces y el análisis de datos.

#### P: ¿Cómo ayuda Aspose.PDF para .NET a extraer destinos de hipervínculos?

R: Aspose.PDF para .NET proporciona potentes API para extraer destinos de hipervínculos con facilidad. Este tutorial demuestra paso a paso cómo extraer destinos de hipervínculos usando C#.

#### P: ¿Puedo extraer destinos de hipervínculos de forma selectiva en función de determinados criterios?

R: Sí, puede extraer destinos de hipervínculos de forma selectiva iterando a través de las páginas del documento PDF y filtrando las anotaciones de hipervínculos deseadas según sus criterios.

#### P: ¿Es posible extraer destinos de hipervínculos de documentos PDF protegidos con contraseña?

R: Aspose.PDF para .NET puede extraer destinos de hipervínculos de documentos PDF protegidos con contraseña siempre que proporcione las credenciales de autenticación necesarias al abrir el documento.

#### P: ¿Cómo puedo utilizar los destinos de hipervínculos extraídos en mi aplicación?

R: Una vez que haya extraído los destinos de los hipervínculos, puede usarlos para realizar varias acciones, como validar las URL de los enlaces, crear informes o implementar una navegación personalizada.

#### P: ¿Existen limitaciones al extraer destinos de hipervínculos?

R: Si bien la extracción de destinos de hipervínculos es poderosa, es esencial tener en cuenta la estructura del documento PDF. Los hipervínculos incrustados en gráficos complejos o contenido multimedia pueden requerir un manejo adicional.

#### P: ¿Puedo extraer otros atributos de los hipervínculos, como tipos de enlace o coordenadas?

R: El tutorial se centra en la extracción de destinos de hipervínculos. Sin embargo, puede consultar la documentación oficial de Aspose.PDF para explorar funciones avanzadas, incluida la extracción de tipos de enlace y coordenadas.