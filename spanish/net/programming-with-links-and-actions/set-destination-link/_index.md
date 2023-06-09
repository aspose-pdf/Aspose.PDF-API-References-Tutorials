---
title: Establecer enlace de destino
linktitle: Establecer enlace de destino
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a establecer un enlace de destino en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 90
url: /es/net/programming-with-links-and-actions/set-destination-link/
---

Aprenda a establecer un enlace de destino en un archivo PDF usando Aspose.PDF para .NET con esta guía paso a paso.

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

## Paso 3: Edición del enlace de destino

Obtenga la anotación del enlace para modificar usando el siguiente código:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

 Puede ajustar el`[1]` índices para seleccionar una página o anotación específica.

A continuación, edite el enlace cambiando la acción del enlace y configurando el destino como una dirección web:

```csharp
linkAnnot.Action = new GoToURIAction("www.aspose.com");
```

## Paso 4: Guarde el documento con el enlace actualizado

Guarde el documento con el enlace actualizado usando el`Save` método:

```csharp
dataDir = dataDir + "SetDestinationLink_out.pdf";
doc.Save(dataDir);
```

## Paso 5: Mostrar el resultado

Muestre un mensaje que indique que el enlace de destino se configuró correctamente y especifique la ubicación del archivo guardado:

```csharp
Console.WriteLine("\nDestination link configured successfully.\nFile saved to location: " + dataDir);
```

### Ejemplo de código fuente para Establecer enlace de destino usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargue el archivo PDF
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	// Obtener la primera anotación de enlace de la primera página del documento
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	// Enlace de modificación: cambie la acción del enlace y establezca el destino como dirección web
	linkAnnot.Action = new GoToURIAction("www.aspose.com");           
	dataDir = dataDir + "SetDestinationLink_out.pdf";
	// Guarde el documento con el enlace actualizado
	doc.Save(dataDir);
	Console.WriteLine("\nDestination link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

¡Felicidades! Ahora sabe cómo configurar un enlace de destino en un archivo PDF utilizando Aspose.PDF para .NET. Utilice este conocimiento para personalizar vínculos en sus documentos PDF y crear experiencias interactivas para los usuarios.

Ahora que completó esta guía, puede aplicar estos conceptos a sus propios proyectos y seguir explorando las características que ofrece Aspose.PDF para .NET.