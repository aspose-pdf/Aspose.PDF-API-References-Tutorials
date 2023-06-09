---
title: Actualizar el color del texto del vínculo
linktitle: Actualizar el color del texto del vínculo
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a actualizar el color del texto de los enlaces en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 130
url: /es/net/programming-with-links-and-actions/update-link-text-color/
---

Aprenda cómo actualizar el color del texto de los enlaces en un archivo PDF usando Aspose.PDF para .NET con esta guía paso a paso.

## Paso 1: Configuración del entorno

Asegúrese de haber configurado su entorno de desarrollo con un proyecto C# y las referencias de Aspose.PDF adecuadas.

## Paso 2: Cargar el archivo PDF

Establezca la ruta del directorio de sus documentos y cargue el archivo PDF usando el siguiente código:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Cargue el archivo PDF
Document doc = new Document(dataDir + "UpdateLinks.pdf");
```

## Paso 3: Navegar por las anotaciones de enlaces

Recorra todas las anotaciones de enlaces en la segunda página del documento usando el siguiente código:

```csharp
foreach(Annotation annotation in doc.Pages[1].Annotations)
{
     if (annotation is LinkAnnotation)
     {
         // Encuentra el texto debajo de la anotación
         TextFragmentAbsorber ta = new TextFragmentAbsorber();
         Rectangle rect = annotation.Rect;
         rect.LLX -= 10;
         rect.LLY -= 10;
         rect.URX += 10;
         rect.URY += 10;
         ta.TextSearchOptions = new TextSearchOptions(rect);
         your.Visit(doc.Pages[1]);
         // Cambiar el color del texto.
         foreach(TextFragment tf in ta.TextFragments)
         {
             tf.TextState.ForegroundColor = Color.Red;
         }
     }
}
```

## Paso 4: Guarde el documento con el texto del enlace actualizado

 Guarde el documento con el texto del enlace actualizado usando el`Save` método:

```csharp
dataDir = dataDir + "UpdateLinkTextColor_out.pdf";
doc.Save(dataDir);
```

## Paso 5: Mostrar el resultado

Muestre un mensaje que indique que el color del texto de la anotación del enlace se actualizó correctamente y especifique la ubicación del archivo guardado:

```csharp
Console.WriteLine("\nText color of link annotations updated successfully.\nFile saved to location: " + dataDir);
```

### Ejemplo de código fuente para actualizar el color del texto del enlace usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargue el archivo PDF
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	foreach (Annotation annotation in doc.Pages[1].Annotations)
	{
		if (annotation is LinkAnnotation)
		{
			// Buscar el texto debajo de la anotación
			TextFragmentAbsorber ta = new TextFragmentAbsorber();
			Rectangle rect = annotation.Rect;
			rect.LLX -= 10;
			rect.LLY -= 10;
			rect.URX += 10;
			rect.URY += 10;
			ta.TextSearchOptions = new TextSearchOptions(rect);
			ta.Visit(doc.Pages[1]);
			// Cambia el color del texto.
			foreach (TextFragment tf in ta.TextFragments)
			{
				tf.TextState.ForegroundColor = Color.Red;
			}
		}
	}
	dataDir = dataDir + "UpdateLinkTextColor_out.pdf";
	// Guarde el documento con el enlace actualizado
	doc.Save(dataDir);
	Console.WriteLine("\nLinkAnnotation text color updated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

¡Felicidades! Ahora sabe cómo actualizar el color del texto de los enlaces en un archivo PDF usando Aspose.PDF para .NET. Utilice este conocimiento para personalizar la apariencia de sus enlaces en documentos PDF.

Ahora que completó esta guía, puede aplicar estos conceptos a sus propios proyectos y seguir explorando las características que ofrece Aspose.PDF para .NET.