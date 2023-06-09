---
title: Aplanar formularios
linktitle: Aplanar formularios
second_title: Referencia de API de Aspose.PDF para .NET
description: Acople fácilmente formularios en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/programming-with-forms/flatten-forms/
---

En este tutorial, le mostraremos cómo aplanar formularios usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Primero, asegúrese de haber importado las bibliotecas necesarias y establezca la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el formulario PDF de origen

Cargue el formulario PDF de origen:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 3: aplana los formularios

Primero verifique si hay campos de formulario en el documento. Si es así, itere a través de cada campo y aplique aplanamiento:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Paso 4: Guarde el documento actualizado

Guarde el documento PDF actualizado:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Ejemplo de código fuente para Flatten Forms usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar formulario PDF de origen
Document doc = new Document(dataDir + "input.pdf");
// Aplanar formularios
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Guardar el documento actualizado
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendimos a aplanar formularios con Aspose.PDF para .NET. Siguiendo estos pasos, puede acoplar fácilmente formularios en sus documentos PDF, haciendo que los campos no se puedan editar y fusionando anotaciones con el contenido del documento.