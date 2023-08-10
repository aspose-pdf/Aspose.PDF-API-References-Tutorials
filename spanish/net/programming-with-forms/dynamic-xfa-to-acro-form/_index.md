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

En este tutorial, aprendimos cómo convertir un formulario XFA To dinámico en un formulario AcroForm estándar usando Aspose.PDF para .NET. Siguiendo estos pasos, puede convertir fácilmente sus formularios XFATo dinámicos a AcroForms para un uso más común.

### Preguntas frecuentes

#### P: ¿Cuál es la diferencia entre un formulario XFA dinámico y un AcroForm estándar?

R: Un formulario XFA (Arquitectura de formularios XML) dinámico es un tipo de formulario PDF que utiliza datos basados en XML para definir su diseño y comportamiento. Los formularios XFA se utilizan a menudo en formularios interactivos y de uso intensivo de datos. Por otro lado, un AcroForm estándar es un tipo de formulario PDF más tradicional que utiliza el propio formato PDF para definir su estructura y apariencia. AcroForms es ampliamente compatible con los visores de PDF y puede ser más compatible con varias aplicaciones.

#### P: ¿Por qué querría convertir un formulario XFA dinámico en un AcroForm estándar?

R: La conversión de un formulario XFA dinámico a un AcroForm estándar puede ser útil en escenarios donde los formularios XFA no son totalmente compatibles o cuando desea lograr una mayor compatibilidad con diferentes visores y aplicaciones de PDF. Los AcroForms estándar generalmente son más compatibles en diferentes plataformas y dispositivos.

#### P: ¿Puedo modificar los campos del formulario después de convertir un formulario XFA dinámico en un AcroForm estándar?

R: Sí, después de convertir un formulario XFA dinámico en un AcroForm estándar, puede modificar los campos del formulario según sea necesario utilizando Aspose.PDF para .NET. Puede agregar nuevos campos, cambiar sus propiedades, establecer valores de campo y realizar otras operaciones relacionadas con formularios.

#### P: ¿Existen limitaciones o consideraciones al convertir formularios XFA dinámicos a AcroForms estándar?

R: Sí, hay algunas limitaciones a tener en cuenta al convertir formularios XFA dinámicos a AcroForms estándar. Los formularios XFA pueden tener diseños complejos y dinámicos, incluidas funciones como tablas dinámicas, secciones repetitivas y cálculos de formularios, que pueden no conservarse por completo en el proceso de conversión. Además, algunas propiedades de campos de formulario específicas exclusivas de los formularios XFA pueden no ser aplicables en AcroForms.

#### P: ¿Puedo convertir un AcroForm estándar en un formulario XFA dinámico usando Aspose.PDF para .NET?

R: Aspose.PDF para .NET actualmente admite la conversión de formularios XFA dinámicos a AcroForms estándar, pero no admite la operación inversa de conversión de AcroForms estándar a formularios XFA dinámicos. La conversión de AcroForms estándar a formularios XFA dinámicos implica transformaciones más complejas y es posible que no se admita completamente en todos los escenarios.