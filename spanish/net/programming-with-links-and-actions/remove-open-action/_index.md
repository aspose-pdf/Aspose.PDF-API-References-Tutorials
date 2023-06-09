---
title: Quitar acción abierta
linktitle: Quitar acción abierta
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a eliminar la acción de abrir de un PDF con Aspose.PDF para .NET.
type: docs
weight: 80
url: /es/net/programming-with-links-and-actions/remove-open-action/
---

Aprenda cómo quitar la acción de abrir de un archivo PDF usando Aspose.PDF para .NET con esta guía paso a paso.

## Paso 1: Configuración del entorno

Asegúrese de haber configurado su entorno de desarrollo con un proyecto C# y las referencias de Aspose.PDF adecuadas.

## Paso 2: Cargar el archivo PDF

Establezca la ruta del directorio de sus documentos y cargue el archivo PDF usando el siguiente código:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Abre el documento
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Paso 3: Eliminar la acción abierta

 Elimine la acción de abrir del documento configurando el`OpenAction` propiedad a nulo:

```csharp
document. OpenAction = null;
```

## Paso 4: Guarde el documento actualizado

 Guarde el documento actualizado usando el`Save` método:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Paso 5: Mostrar el resultado

Muestre un mensaje que indique que la acción de abrir se eliminó con éxito y especifique la ubicación del archivo guardado:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Ejemplo de código fuente para Eliminar acción abierta usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Quitar acción de apertura de documento
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Guardar documento actualizado
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Conclusión

¡Felicidades! Ahora sabe cómo eliminar la acción de abrir de un PDF usando Aspose.PDF para .NET. Utilice este conocimiento para personalizar las propiedades y el comportamiento de los archivos PDF en sus proyectos.

Ahora que completó esta guía, puede aplicar estos conceptos a sus propios proyectos y seguir explorando las características que ofrece Aspose.PDF para .NET.