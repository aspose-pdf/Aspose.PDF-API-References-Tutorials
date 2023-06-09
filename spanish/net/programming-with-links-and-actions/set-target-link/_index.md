---
title: Establecer enlace de destino
linktitle: Establecer enlace de destino
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a establecer un enlace de destino en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/programming-with-links-and-actions/set-target-link/
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
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## Paso 3: Edición del enlace de destino

Obtenga la anotación del enlace para modificar usando el siguiente código:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

 Puede ajustar el`[1]` índices para seleccionar una página o anotación específica.

A continuación, actualice el destino sin actualizar el archivo:

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

Y si también quieres actualizar el archivo:

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## Paso 4: Guarde el documento con el enlace actualizado

Guarde el documento con el enlace actualizado usando el`Save` método:

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## Paso 5: Mostrar el resultado

Muestre un mensaje que indique que el enlace de destino se configuró correctamente y especifique la ubicación del archivo guardado:

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### Ejemplo de código fuente para Establecer enlace de destino usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargue el archivo PDF
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	// Destino de actualización de siguiente línea, no actualizar archivo
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	// Archivo de actualización de la siguiente línea
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	// Guarde el documento con el enlace actualizado
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

¡Felicidades! Ahora sabe cómo establecer un enlace de destino en un archivo PDF utilizando Aspose.PDF para .NET. Utilice este conocimiento para personalizar vínculos en sus documentos PDF y crear experiencias interactivas para los usuarios.

Ahora que completó esta guía, puede aplicar estos conceptos a sus propios proyectos y seguir explorando las características que ofrece Aspose.PDF para .NET.