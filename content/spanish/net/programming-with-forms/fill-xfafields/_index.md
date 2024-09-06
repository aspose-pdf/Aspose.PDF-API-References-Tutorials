---
title: Rellenar campos XFA
linktitle: Rellenar campos XFA
second_title: Referencia de API de Aspose.PDF para .NET
description: Llene fácilmente los campos XFA en sus documentos PDF usando Aspose.PDF para .NET.
type: docs
weight: 90
url: /es/net/programming-with-forms/fill-xfafields/
---
En este tutorial, le mostraremos cómo completar campos XFA con Aspose.PDF para .NET. Le explicaremos el código fuente de C# paso a paso para guiarlo en este proceso.

## Paso 1: Preparación

Primero, asegúrese de haber importado las bibliotecas necesarias y configure la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el formulario XFA

Cargue el formulario XFA:

```csharp
Document doc = new Document(dataDir + "FillXFAFields.pdf");
```

## Paso 3: Obtener los nombres de los campos XFA

Obtenga los nombres de los campos XFA del formulario:

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## Paso 4: Establecer valores de campo

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

### Código fuente de muestra para rellenar campos XFA utilizando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar formulario XFA
Document doc = new Document(dataDir + "FillXFAFields.pdf");
// Obtener los nombres de los campos del formulario XFA
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

En este tutorial, aprendimos a completar campos XFA con Aspose.PDF para .NET. Si sigue estos pasos, podrá cambiar fácilmente los valores de los campos XFA en sus documentos PDF con Aspose.PDF.

### Preguntas frecuentes

#### P: ¿Qué es XFA (arquitectura de formularios XML)?

R: XFA significa XML Forms Architecture, que es un formato basado en XML para definir formularios interactivos en documentos PDF. Los formularios XFA suelen ser más complejos que los AcroForms tradicionales y pueden incluir contenido dinámico y secuencias de comandos. Aspose.PDF para .NET ofrece compatibilidad para completar campos de formularios XFA.

#### P: ¿Puedo completar campos XFA en cualquier documento PDF?

 R: No todos los documentos PDF contienen formularios XFA. Los formularios XFA son menos comunes que los AcroForms tradicionales. Puede determinar si un documento PDF contiene un formulario XFA consultando la`doc.Form.Type` propiedad. Si el valor es`FormType.Xfa` , el documento contiene un formulario XFA y puede continuar llenando sus campos usando`doc.Form.XFA`.

#### P: ¿Cómo puedo encontrar los nombres de los campos de formulario XFA en un documento PDF?

 A: Para encontrar los nombres de los campos de formulario XFA en un documento PDF, puede utilizar el`doc.Form.XFA.FieldNames` propiedad, que devuelve una matriz de cadenas que contienen los nombres de todos los campos XFA del documento.

#### P: ¿Puedo completar campos XFA con datos dinámicos de una fuente de datos externa?

R: Sí, puede completar campos XFA con datos dinámicos de una fuente de datos externa. Antes de configurar los valores de los campos, recupere los datos de la fuente y utilice los nombres de los campos XFA para configurar sus valores mediante programación.

#### P: ¿Existen limitaciones al trabajar con formularios XFA en Aspose.PDF para .NET?

R: Aspose.PDF para .NET ofrece compatibilidad para completar campos de formularios XFA, pero es posible que no admita todas las funciones y características complejas de los formularios XFA. Es posible que algunas funciones avanzadas específicas de XFA, como la creación de scripts o los cambios de diseño dinámicos, no sean totalmente compatibles con Aspose.PDF para .NET.