---
title: Obtener destinos de hipervínculos en archivos PDF
linktitle: Obtener destinos de hipervínculos en archivos PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a extraer destinos de hipervínculos en archivos PDF usando Aspose.PDF para .NET.
type: docs
weight: 60
url: /es/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF para .NET es una potente biblioteca para manipular y extraer información de archivos PDF mediante el lenguaje de programación C#. En este tutorial, nos centraremos en la extracción de destinos de hipervínculos de un archivo PDF mediante Aspose.PDF para .NET.

## Prerrequisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- Un entorno de desarrollo integrado (IDE) como Visual Studio.
- La biblioteca Aspose.PDF para .NET instalada en su máquina.

## Paso 1: Configuración del entorno de desarrollo

Antes de comenzar a escribir código, debes configurar tu entorno de desarrollo creando un nuevo proyecto C# en tu IDE favorito.

## Paso 2: Importar referencias de Aspose.PDF

Para utilizar Aspose.PDF para .NET, debe agregar las referencias adecuadas a su proyecto. Siga los pasos que se indican a continuación para importar las referencias necesarias:

1. En su proyecto, haga clic derecho en “Referencias” y seleccione “Agregar referencia”.
2. En la ventana "Agregar referencia", busque y seleccione los archivos DLL de Aspose.PDF para .NET.
3. Haga clic en "Aceptar" para importar las referencias a su proyecto.

## Paso 3: Cargar el archivo PDF

Antes de poder extraer los destinos de los hipervínculos, debe cargar el archivo PDF en su aplicación. Utilice el siguiente código para cargar el archivo PDF:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Cargar el archivo PDF
Document document = new Document(dataDir + "input.pdf");
```

Asegúrese de especificar la ruta correcta al directorio de su documento y al archivo PDF que desea procesar.

## Paso 4: Navegar por las páginas del documento

Ahora que el archivo PDF está cargado, debe recorrer todas las páginas del documento. Esto le permitirá obtener

Ir a las anotaciones de hipervínculo presentes en cada página. Utilice el siguiente código para recorrer las páginas del documento:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Obtener las anotaciones de enlaces de una página específica
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Crea una lista para almacenar todos los enlaces
     IList<Annotation> list = selector. Selected;
     // Recorrer cada elemento de la lista
     foreach(LinkAnnotation a in list)
     {
         // URL de destino de impresión
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Este código recorre cada página del documento y selecciona las anotaciones de hipervínculos presentes en cada página. Luego, almacena estas anotaciones en una lista e imprime la URL de destino de cada vínculo.

## Paso 5: Obtención de destinos de hipervínculos

El último paso consiste en extraer los destinos de los hipervínculos de las anotaciones de hipervínculos. El código siguiente muestra cómo hacerlo:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Utiliza el destino como desees
     }
}
```

En este código, obtenemos cada destino de hipervínculo de las anotaciones de vínculo y almacenamos el destino en una variable. Luego, puede usar este destino como desee en su aplicación.

### Código fuente de muestra para obtener destinos de hipervínculos con Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargar el archivo PDF
	Document document = new Document(dataDir + "input.pdf");
	// Recorrer todas las páginas del PDF
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Obtener las anotaciones de enlaces de una página en particular
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Crear una lista que contenga todos los enlaces
		IList<Annotation> list = selector.Selected;
		// Iterar a través de un elemento individual dentro de la lista
		foreach (LinkAnnotation a in list)
		{
			// Imprimir la URL de destino
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

### Preguntas frecuentes sobre cómo obtener hipervínculos a destinos en archivos PDF

#### P: ¿Qué es un destino de hipervínculo en un archivo PDF?

R: Un destino de hipervínculo en un archivo PDF es una ubicación o destino específico al que apunta un hipervínculo. Puede ser una URL, una página dentro del mismo documento o un documento externo.

#### P: ¿Cómo puede la extracción de destinos de hipervínculos beneficiar mi análisis de documentos PDF?

A: La extracción de destinos de hipervínculos le permite identificar y catalogar todos los destinos a los que apuntan los hipervínculos dentro de un documento PDF. Esta información puede ser útil para la validación de contenido, la verificación de vínculos y el análisis de datos.

#### P: ¿Cómo ayuda Aspose.PDF para .NET a extraer destinos de hipervínculos?

A: Aspose.PDF para .NET ofrece potentes API para extraer destinos de hipervínculos con facilidad. Este tutorial demuestra paso a paso cómo extraer destinos de hipervínculos con C#.

#### P: ¿Puedo extraer selectivamente destinos de hipervínculos en función de determinados criterios?

R: Sí, puede extraer de forma selectiva destinos de hipervínculos iterando a través de las páginas del documento PDF y filtrando las anotaciones de hipervínculos deseadas según sus criterios.

#### P: ¿Es posible extraer destinos de hipervínculos de documentos PDF protegidos con contraseña?

R: Aspose.PDF para .NET puede extraer destinos de hipervínculos de documentos PDF protegidos con contraseña siempre que proporcione las credenciales de autenticación necesarias al abrir el documento.

#### P: ¿Cómo puedo utilizar los destinos de hipervínculos extraídos en mi aplicación?

R: Una vez que haya extraído los destinos de hipervínculos, puede usarlos para realizar diversas acciones, como validar URL de enlaces, crear informes o implementar navegación personalizada.

#### P: ¿Existen limitaciones al extraer destinos de hipervínculos?

R: Si bien la extracción de destinos de hipervínculos es eficaz, es esencial tener en cuenta la estructura del documento PDF. Los hipervínculos integrados en gráficos complejos o contenido multimedia pueden requerir un manejo adicional.

#### P: ¿Puedo extraer otros atributos de los hipervínculos, como tipos de enlaces o coordenadas?

R: El tutorial se centra en la extracción de destinos de hipervínculos. Sin embargo, puede consultar la documentación oficial de Aspose.PDF para explorar funciones avanzadas, incluida la extracción de tipos de vínculos y coordenadas.