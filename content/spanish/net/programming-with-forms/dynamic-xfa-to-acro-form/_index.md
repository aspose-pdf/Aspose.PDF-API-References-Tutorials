---
title: XFA dinámico a formato Acro
linktitle: XFA dinámico a formato Acro
second_title: Referencia de API de Aspose.PDF para .NET
description: Convierta fácilmente formularios XFA dinámicos en formularios AcroForm estándar con Aspose.PDF para .NET.
type: docs
weight: 70
url: /es/net/programming-with-forms/dynamic-xfa-to-acro-form/
---
En este tutorial, le mostraremos cómo convertir un formulario dinámico XFA a un AcroForm usando Aspose.PDF para .NET. Le explicaremos el código fuente de C# paso a paso para guiarlo en este proceso.

## Paso 1: Preparación

Primero, asegúrese de haber importado las bibliotecas necesarias y configure la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el formulario XFA dinámico

Cargue el formulario XFA dinámico:

```csharp
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
```

## Paso 3: Establezca el tipo de formulario como AcroForm estándar

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

### Código fuente de muestra para conversión dinámica de XFA a Acro Form con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar formulario XFA dinámico
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
// Establezca el tipo de campos de formulario como estándar AcroForm
document.Form.Type = FormType.Standard;
dataDir = dataDir + "Standard_AcroForm_out.pdf";
// Guardar el PDF resultante
document.Save(dataDir);
Console.WriteLine("\nDynamic XFA form converted to standard AcroForm successfully.\nFile saved at " + dataDir);
```

## Conclusión

En este tutorial, aprendimos a convertir un formulario dinámico XFA To a un formulario AcroForm estándar mediante Aspose.PDF para .NET. Si sigue estos pasos, podrá convertir fácilmente sus formularios dinámicos XFA To a AcroForms para un uso más común.

### Preguntas frecuentes

#### P: ¿Cuál es la diferencia entre un formulario XFA dinámico y un AcroForm estándar?

R: Un formulario XFA (XML Forms Architecture) dinámico es un tipo de formulario PDF que utiliza datos basados en XML para definir su diseño y comportamiento. Los formularios XFA se utilizan a menudo en formularios interactivos y con uso intensivo de datos. Por otro lado, un AcroForm estándar es un tipo de formulario PDF más tradicional que utiliza el propio formato PDF para definir su estructura y apariencia. Los AcroForms son ampliamente compatibles con los visores de PDF y pueden ser más compatibles con varias aplicaciones.

#### P: ¿Por qué querría convertir un formulario XFA dinámico en un AcroForm estándar?

R: La conversión de un formulario XFA dinámico a un AcroForm estándar puede resultar útil en situaciones en las que los formularios XFA no son totalmente compatibles o cuando se desea lograr una mayor compatibilidad con diferentes visualizadores y aplicaciones de PDF. Los AcroForms estándar suelen tener una mayor compatibilidad en diferentes plataformas y dispositivos.

#### P: ¿Puedo modificar los campos del formulario después de convertir un formulario XFA dinámico a un AcroForm estándar?

R: Sí, después de convertir un formulario XFA dinámico en un AcroForm estándar, puede modificar los campos del formulario según sea necesario utilizando Aspose.PDF para .NET. Puede agregar nuevos campos, cambiar sus propiedades, establecer valores de campo y realizar otras operaciones relacionadas con el formulario.

#### P: ¿Existen limitaciones o consideraciones al convertir formularios XFA dinámicos a AcroForms estándar?

R: Sí, existen algunas limitaciones que se deben tener en cuenta al convertir formularios XFA dinámicos a AcroForms estándar. Los formularios XFA pueden tener diseños complejos y dinámicos, incluidas características como tablas dinámicas, secciones repetidas y cálculos de formulario, que pueden no conservarse por completo en el proceso de conversión. Además, es posible que algunas propiedades de campos de formulario específicas exclusivas de los formularios XFA no sean aplicables en AcroForms.

#### P: ¿Puedo convertir un AcroForm estándar en un formulario XFA dinámico usando Aspose.PDF para .NET?

R: Aspose.PDF para .NET actualmente admite la conversión de formularios XFA dinámicos a AcroForms estándar, pero no admite la operación inversa de conversión de AcroForms estándar a formularios XFA dinámicos. La conversión de AcroForms estándar a formularios XFA dinámicos implica transformaciones más complejas y es posible que no sea totalmente compatible en todos los escenarios.