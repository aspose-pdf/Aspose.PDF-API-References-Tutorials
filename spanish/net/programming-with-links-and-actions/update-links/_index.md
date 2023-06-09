---
title: Actualizar enlaces
linktitle: Actualizar enlaces
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a actualizar enlaces en un archivo PDF con Aspose.PDF para .NET.
type: docs
weight: 120
url: /es/net/programming-with-links-and-actions/update-links/
---

Aprenda a actualizar enlaces en un archivo PDF usando Aspose.PDF para .NET con esta guía paso a paso.

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

## Paso 3: Edición del enlace

Obtenga la anotación del enlace para modificar usando el siguiente código:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

 Puede ajustar el`[1]` índices para seleccionar una página o anotación específica.

A continuación, modifique el enlace cambiando el destino:

```csharp
GoToAction goToAction = (GoToAction)linkAnnot.Action;
goToAction.Destination = new Aspose.Pdf.Annotations.XYZExplicitDestination(1, 1, 2, 2);
```

El primer parámetro representa el tema del documento, el segundo es el número de página de destino. El quinto argumento es el factor de zoom al mostrar la página respectiva. Cuando se establece en 2, la página se mostrará con un zoom del 200 %.

## Paso 4: Guarde el documento con el enlace actualizado

Guarde el documento con el enlace actualizado usando el`Save` método:

```csharp
dataDir = dataDir + "PDFLINK_Modified_UpdateLinks_out.pdf";
doc.Save(dataDir);
```

## Paso 5: Mostrar el resultado

Muestre un mensaje que indique que los enlaces se actualizaron correctamente y especifique la ubicación del archivo guardado:

```csharp
Console.WriteLine("\nLinks updated successfully.\nFile saved to location: " + dataDir);
```

### Ejemplo de código fuente para Actualizar enlaces usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargue el archivo PDF
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	// Obtener la primera anotación de enlace de la primera página del documento
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	// Enlace de modificación: cambiar el destino del enlace
	GoToAction goToAction = (GoToAction)linkAnnot.Action;
	// Especificar el destino del objeto de enlace
	// El primer parámetro es el objeto del documento, el segundo es el número de página de destino.
	// El argumento 5ht es el factor de zoom al mostrar la página respectiva. Al usar 2, la página se mostrará con un zoom del 200 %.
	goToAction.Destination = new Aspose.Pdf.Annotations.XYZExplicitDestination(1, 1, 2, 2);
	dataDir = dataDir + "PDFLINK_Modified_UpdateLinks_out.pdf";
	// Guarde el documento con el enlace actualizado
	doc.Save(dataDir);
	Console.WriteLine("\nLinks updated successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

¡Felicidades! Ahora sabe cómo actualizar enlaces en un archivo PDF usando Aspose.PDF para .NET. Utilice este conocimiento para personalizar vínculos en sus documentos PDF y crear experiencias interactivas para los usuarios.

Ahora que completó esta guía, puede aplicar estos conceptos a sus propios proyectos y seguir explorando las características que ofrece Aspose.PDF para .NET.