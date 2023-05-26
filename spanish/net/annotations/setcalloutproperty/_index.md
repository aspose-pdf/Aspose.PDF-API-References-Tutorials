---
title: Establecer propiedad de llamada
linktitle: Establecer propiedad de llamada
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a configurar la propiedad de la llamada con Aspose.PDF para .NET. Personalice las anotaciones con líneas de llamada, color de texto y estilos finales.
type: docs
weight: 130
url: /es/net/annotations/setcalloutproperty/
---
Aspose.PDF para .NET es una poderosa biblioteca para crear, manipular y convertir documentos PDF en C#. Una de las características proporcionadas por esta biblioteca es la capacidad de establecer propiedades de llamada para anotaciones de texto libre en documentos PDF. Esto se puede hacer usando el`FreeTextAnnotation` class, que le permite crear anotaciones con llamadas.

En este tutorial, lo guiaremos a través del proceso de configuración de propiedades de llamada para una anotación de texto libre usando Aspose.PDF para .NET en C#. Siga los pasos a continuación para comenzar.

## Instalar Aspose.PDF para .NET

 Si aún no lo ha hecho, deberá[descargar](https://releases.aspose.com/pdf/net/) e instale Aspose.PDF para .NET desde Aspose Releases o a través del administrador de paquetes NuGet.

## Crear un nuevo documento PDF

 Cree un nuevo documento PDF usando el`Document` clase proporcionada por Aspose.PDF para .NET.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Agregar una nueva página al documento

 Agregue una nueva página al documento usando el`Pages` colección de la`Document` clase.

```csharp
Page page = doc.Pages.Add();
```

## Establecer apariencia predeterminada

Establezca la apariencia predeterminada para la anotación de texto libre creando una nueva`DefaultAppearance` objeto y establecer sus propiedades tales como`TextColor` y`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Crear una anotación de texto libre con llamada

 Cree una nueva anotación de texto libre con llamada usando el`FreeTextAnnotation` clase. Selecciona el`Intent` propiedad a`FreeTextIntent.FreeTextCallout` para especificar que se trata de una anotación de llamada. Selecciona el`EndingStyle` propiedad a`LineEnding.OpenArrow` para especificar el estilo de la flecha al final de la llamada. Selecciona el`Callout` propiedad a una matriz de`Point` objetos que representan los puntos de la página donde se debe dibujar la línea de llamada.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Agregar la anotación de texto libre a la página

 Agregue la anotación de texto libre a la página usando el`Annotations` colección de la`Page` clase.

```csharp
page.Annotations.Add(fta);
```

## Agregar texto a la anotación

 Agregue texto a la anotación configurando el`RichText` propiedad a una cadena de XML formateado. En este tutorial, estamos configurando el color del texto en rojo y el tamaño de fuente en 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF
```

## 8. guardar el documento

Ahora guarde el documento usando el siguiente código:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Ejemplo de código fuente para Establecer propiedad de llamada usando Aspose.PDF para .NET

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
            fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Esta es una muestra</span></p></body>";
            doc.Save(dataDir + "SetCalloutProperty.pdf");

            
        
```
