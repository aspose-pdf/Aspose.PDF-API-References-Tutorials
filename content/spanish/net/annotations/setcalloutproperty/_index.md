---
title: Establecer propiedad de llamada en archivo PDF
linktitle: Establecer propiedad de llamada en archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a configurar la propiedad de llamada en un archivo PDF usando Aspose.PDF para .NET. Personalice las anotaciones con líneas de leyenda, color de texto y estilos finales.
type: docs
weight: 130
url: /es/net/annotations/setcalloutproperty/
---
 Aspose.PDF para .NET es una poderosa biblioteca para crear, manipular y convertir documentos PDF en C#. Una de las características que ofrece esta biblioteca es la capacidad de establecer propiedades de llamada para anotaciones de texto libre en documentos PDF. Esto se puede hacer usando el`FreeTextAnnotation` clase, que le permite crear anotaciones con llamadas.

En este tutorial, lo guiaremos a través del proceso de configuración de propiedades de llamada para una anotación de texto libre usando Aspose.PDF para .NET en C#. Siga los pasos a continuación para comenzar.

## Instalar Aspose.PDF para .NET

 Si aún no lo ha hecho, deberá[descargar](https://releases.aspose.com/pdf/net/) e instale Aspose.PDF para .NET desde Aspose Releases o mediante el administrador de paquetes NuGet.

## Paso 1: crea un nuevo documento PDF

 Cree un nuevo documento PDF utilizando el`Document`clase proporcionada por Aspose.PDF para .NET.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Paso 2: agregue una nueva página al documento

 Agregue una nueva página al documento usando el`Pages` colección de la`Document` clase.

```csharp
Page page = doc.Pages.Add();
```

## Paso 3: establecer la apariencia predeterminada

 Establezca la apariencia predeterminada para la anotación de texto libre creando una nueva`DefaultAppearance` objeto y estableciendo sus propiedades como`TextColor` y`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Paso 4: crea una anotación de texto libre con llamada

 Cree una nueva anotación de texto libre con llamada usando el`FreeTextAnnotation` clase. Selecciona el`Intent` propiedad a`FreeTextIntent.FreeTextCallout` para especificar que se trata de una anotación de llamada. Selecciona el`EndingStyle` propiedad a`LineEnding.OpenArrow` para especificar el estilo de la flecha al final de la llamada. Selecciona el`Callout` propiedad a una serie de`Point` objetos que representan los puntos de la página donde se debe dibujar la línea de llamada.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Paso 5: agregue la anotación de texto libre a la página

 Agregue la anotación de texto libre a la página usando el`Annotations` colección de la`Page` clase.

```csharp
page.Annotations.Add(fta);
```

## Paso 6: agregue texto a la anotación

 Agregue texto a la anotación configurando el`RichText`propiedad a una cadena de XML formateado. En este tutorial, configuraremos el color del texto en rojo y el tamaño de fuente en 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" estilo=\"color:#FF
```

## Paso 7: guarda el documento

Ahora guarde el documento usando el siguiente código:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Código fuente de ejemplo para establecer propiedad de llamada usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Esto es una muestra</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## Conclusión

En este tutorial, exploramos cómo configurar propiedades de llamada para una anotación de texto libre en un documento PDF usando Aspose.PDF para .NET. Las anotaciones de llamada son útiles para proporcionar información adicional o explicaciones relacionadas con áreas específicas de un documento. Aspose.PDF para .NET proporciona una amplia gama de funciones y capacidades para trabajar con archivos PDF, incluida la creación y personalización de anotaciones, como llamadas. Siguiendo la guía paso a paso y utilizando el código fuente C# proporcionado, los desarrolladores pueden implementar fácilmente anotaciones en sus documentos PDF, mejorando la usabilidad y claridad de sus documentos. Aspose.PDF para .NET es una biblioteca versátil y confiable para operaciones de PDF en aplicaciones .NET, que ofrece herramientas poderosas para manejar diversas tareas relacionadas con PDF de manera eficiente.

### Preguntas frecuentes sobre cómo establecer la propiedad de llamada en un archivo PDF

#### P: ¿Qué es una anotación en un documento PDF?

R: Una anotación de llamada en un documento PDF es un tipo de anotación que le permite crear un cuadro de texto con una línea guía que apunta a un área específica del documento. Se utiliza comúnmente para proporcionar información adicional o comentarios relacionados con una sección o elemento particular del documento.

#### P: ¿Puedo personalizar la apariencia de la anotación de llamada usando Aspose.PDF para .NET?

R: Sí, puede personalizar varias propiedades de la anotación de llamada, como el color, el tamaño de fuente, la alineación del texto, el estilo de línea, el estilo de flecha y más.

#### P: ¿Cómo agrego texto a la anotación de llamada?

 R: Para agregar texto a la anotación de llamada, puede configurar el`RichText` propiedad de la`FreeTextAnnotation` objeto. El`RichText` La propiedad toma una cadena de XML formateado que representa el texto que se mostrará en la anotación de llamada.

#### P: ¿Puedo agregar varias anotaciones a un documento PDF usando Aspose.PDF para .NET?

 R: Sí, puede crear varias anotaciones de leyenda en un documento PDF creando varias instancias de la`FreeTextAnnotation`objeto y agregarlos a diferentes páginas o ubicaciones en el documento.