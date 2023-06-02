---
title: Obtener XFAProperties
linktitle: Obtener XFAProperties
second_title: Referencia de API de Aspose.PDF para .NET
description: Obtenga fácilmente las propiedades XFA de los campos de formulario en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 160
url: /es/net/programming-with-forms/get-xfaproperties/
---

En este tutorial, le mostraremos cómo obtener las propiedades XFA de los campos de formulario en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Asegúrese de haber importado las bibliotecas necesarias y establezca la ruta a su directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el formulario XFA

Cargue el formulario XFA desde el documento PDF:

```csharp
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
```

## Paso 3: obtener nombres de campo

Obtener nombres de campo XFA:

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## Paso 4: establecer valores de campo

Establecer valores para los campos XFA:

```csharp
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
```

## Paso 5: Obtenga la posición de los campos

Obtenga la posición de los campos XFA:

```csharp
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
```

## Paso 6: Guarde el documento actualizado

Guarde el documento PDF actualizado:

```csharp
dataDir = dataDir + "Filled_XFA_out.pdf";
doc.Save(dataDir);
```

### Ejemplo de código fuente para Obtener XFAProperties usando Aspose.Words para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar formulario XFA
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
string[] names = doc.Form.XFA.FieldNames;
// Establecer valores de campo
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
// Obtener posición de campo
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
// Obtener posición de campo
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
dataDir = dataDir + "Filled_XFA_out.pdf";
// Guardar el documento actualizado
doc.Save(dataDir);
Console.WriteLine("\nXFA fields properties retrieved successfully.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendimos cómo obtener propiedades XFA de campos de formulario en un documento PDF usando Aspose.PDF para .NET. Siguiendo estos pasos, puede extraer fácilmente información de campo XFA, como posiciones, de documentos PDF usando Aspose.PDF.