---
title: Rellenar campos XFA
linktitle: Rellenar campos XFA
second_title: Referencia de API de Aspose.PDF para .NET
description: Complete fácilmente los campos XFA en sus documentos PDF usando Aspose.PDF para .NET.
type: docs
weight: 90
url: /es/net/programming-with-forms/fill-xfafields/
---

En este tutorial, le mostraremos cómo llenar campos XFA usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Primero, asegúrese de haber importado las bibliotecas necesarias y establezca la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el formulario XFA

Cargue el formulario XFA:

```csharp
Document doc = new Document(dataDir + "FillXFAFields.pdf");
```

## Paso 3: obtener nombres de campo XFA

Obtenga los nombres de los campos XFA del formulario:

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## Paso 4: establecer valores de campo

Establezca los valores del campo XFA utilizando los nombres obtenidos anteriormente:

```csharp
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
```

## Paso 5: Guarde el documento actualizado

Guarde el documento PDF actualizado:

```csharp
dataDir = dataDir + "Filled_XFA_out.pdf";
doc.Save(dataDir);
```

### Ejemplo de código fuente para llenar XFAFields usando Aspose.Words para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar formulario XFA
Document doc = new Document(dataDir + "FillXFAFields.pdf");
//Obtener nombres de campos de formulario XFA
string[] names = doc.Form.XFA.FieldNames;
// Establecer valores de campo
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
dataDir = dataDir + "Filled_XFA_out.pdf";
// Guardar el documento actualizado
doc.Save(dataDir);
Console.WriteLine("\nXFA fields filled successfully.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendimos cómo llenar campos XFA usando Aspose.PDF para .NET. Siguiendo estos pasos, puede cambiar fácilmente los valores de los campos XFA en sus documentos PDF utilizando Aspose.PDF.