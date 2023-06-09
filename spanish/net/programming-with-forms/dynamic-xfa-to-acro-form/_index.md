---
title: XFA dinámico a forma Acro
linktitle: XFA dinámico a forma Acro
second_title: Referencia de API de Aspose.PDF para .NET
description: Convierta fácilmente formularios XFA To dinámicos en formularios AcroForm estándar con Aspose.PDF para .NET.
type: docs
weight: 70
url: /es/net/programming-with-forms/dynamic-xfa-to-acro-form/
---

En este tutorial, le mostraremos cómo convertir un formulario XFA To dinámico a un AcroForm utilizando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Primero, asegúrese de haber importado las bibliotecas necesarias y establezca la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el formulario XFA dinámico

Cargue el formulario XFA dinámico:

```csharp
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
```

## Paso 3: establezca el tipo de formulario como AcroForm estándar

Establezca el tipo de formulario como AcroForm estándar:

```csharp
document.Form.Type = FormType.Standard;
```

## Paso 4: Guarde el PDF resultante

Guarde el PDF resultante:

```csharp
dataDir = dataDir + "Standard_AcroForm_out.pdf";
document. Save(dataDir);
```

### Ejemplo de código fuente para Dynamic XFA To Acro Form usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar formulario XFA dinámico
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
// Establecer el tipo de campos de formulario como estándar AcroForm
document.Form.Type = FormType.Standard;
dataDir = dataDir + "Standard_AcroForm_out.pdf";
// Guarde el PDF resultante
document.Save(dataDir);
Console.WriteLine("\nDynamic XFA form converted to standard AcroForm successfully.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendimos cómo convertir un formulario XFA To dinámico en un formulario AcroForm estándar utilizando Aspose.PDF para .NET. Siguiendo estos pasos, puede convertir fácilmente sus formularios XFATo dinámicos a AcroForms para un uso más común.