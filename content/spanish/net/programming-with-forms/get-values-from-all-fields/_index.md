---
title: Obtener valores de todos los campos en un documento PDF
linktitle: Obtener valores de todos los campos en un documento PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Obtenga fácilmente los valores de todos los campos de formulario en un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 150
url: /es/net/programming-with-forms/get-values-from-all-fields/
---
En este tutorial, le mostraremos cómo obtener los valores de todos los campos de formulario en un documento PDF utilizando Aspose.PDF para .NET. Le explicaremos el código fuente de C# paso a paso para guiarlo en este proceso.

## Paso 1: Preparación

Asegúrese de haber importado las bibliotecas necesarias y de haber configurado la ruta al directorio de sus documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Abra el documento

Abra el documento PDF:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Paso 3: Obtener valores para todos los campos

Recorra todos los campos de formulario del documento y obtenga sus nombres y valores:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Código fuente de muestra para obtener valores de todos los campos con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Obtener valores de todos los campos
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Conclusión

En este tutorial, aprendimos a obtener los valores de todos los campos de formulario en un documento PDF con Aspose.PDF para .NET. Si sigue estos pasos, podrá extraer fácilmente los valores de todos los campos de formulario de sus documentos PDF con Aspose.PDF.

### Preguntas frecuentes

#### P: ¿Puedo modificar los valores de los campos de formulario mientras los recupero usando Aspose.PDF para .NET?

 R: Sí, puede modificar los valores de los campos de formulario mientras los recupera utilizando Aspose.PDF para .NET. Una vez que tenga los`Field` objeto que representa un campo de formulario, puede actualizarlo`Value`Propiedad con el valor deseado. Después de realizar los cambios necesarios, puede guardar el documento PDF actualizado para reflejar los cambios.

#### P: ¿Cómo puedo filtrar y recuperar campos de formulario específicos en función de sus tipos (por ejemplo, campos de texto, casillas de verificación)?

 A: Para recuperar campos de formulario específicos según sus tipos, puede utilizar declaraciones condicionales o consultas LINQ para filtrar los campos de interés. Puede comprobar el tipo de cada campo de formulario utilizando la función de filtrado de campos.`FieldType` propiedad y luego recuperar los valores en consecuencia.

#### P: ¿Qué sucede si el documento PDF no tiene campos de formulario?

 A: Si el documento PDF no contiene ningún campo de formulario, el`pdfDocument.Form` La propiedad devolverá una colección vacía. En tales casos, el bucle para recuperar valores no se ejecutará y no se mostrará ningún valor.

#### P: ¿Puedo extraer los valores del campo de formulario en un orden específico u ordenarlos alfabéticamente?

R: El orden en el que se recuperan los campos del formulario depende de la estructura subyacente del documento PDF. Aspose.PDF para .NET devuelve los campos del formulario en el orden en el que se agregaron al documento. Si desea mostrar o procesar los campos del formulario en un orden específico, puede implementar una lógica de ordenación personalizada según sus requisitos.

#### P: ¿Cómo puedo gestionar documentos PDF cifrados con campos de formulario protegidos con contraseña?

 A: Aspose.PDF para .NET ofrece funciones para trabajar con documentos PDF cifrados y campos de formulario protegidos con contraseña. Antes de cargar el documento, puede configurar la contraseña mediante el botón`pdfDocument.Password` propiedad para acceder al documento PDF protegido y sus campos de formulario.