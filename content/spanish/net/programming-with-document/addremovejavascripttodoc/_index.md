---
title: Agregar Quitar Javascript al documento PDF
linktitle: Agregar Quitar Javascript al documento
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a agregar y eliminar JavaScript a un documento PDF usando Aspose.PDF para .NET. Guía paso a paso con tutoriales de código para secuencias de comandos a nivel de documento.
type: docs
weight: 30
url: /es/net/programming-with-document/addremovejavascripttodoc/
---
Para agregar y eliminar JavaScript a un documento PDF, utilizaremos la biblioteca Aspose.PDF para .NET. Esta poderosa biblioteca nos permite manipular archivos PDF en aplicaciones .NET. Siga las instrucciones paso a paso a continuación para agregar y eliminar JavaScript usando Aspose.PDF para .NET.

## Paso 1: cree un nuevo documento PDF

 Comience creando una nueva instancia del`Document` clase proporcionada por Aspose.PDF para .NET. Esto servirá como documento PDF donde agregaremos JavaScript.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Paso 2: agregue JavaScript a nivel de documento

 Para agregar JavaScript a nivel de documento, use el`JavaScript` propiedad de la`Document` clase. Asigne funciones de JavaScript a claves en el diccionario de JavaScript.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 En este tutorial, hemos agregado dos funciones de JavaScript,`func1` y`func2`, al documento PDF.

## Paso 3: eliminar JavaScript a nivel de documento

 Para eliminar JavaScript a nivel de documento, cargue el documento PDF y acceda a la`JavaScript`diccionario. Itere sobre las claves y elimine la función de JavaScript deseada.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 En este tutorial, eliminamos el`func1` Función JavaScript del documento PDF.

## Paso 4: guardar y verificar los cambios

Guarde el documento PDF modificado y verifique los cambios.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Este código guardará el documento PDF modificado y mostrará el mensaje de éxito.

### Código fuente de ejemplo para Agregar y eliminar Javascript de documentos PDF usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// Eliminar JavaScript a nivel de documento
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## Conclusión

En este artículo, proporcionamos una guía paso a paso para agregar y eliminar JavaScript de documentos PDF usando Aspose.PDF para .NET. Si sigue las instrucciones y utiliza los tutoriales de código proporcionados, puede incorporar fácilmente JavaScript en sus documentos PDF y eliminarlo cuando sea necesario. JavaScript permite la funcionalidad dinámica y la interactividad en sus archivos PDF, mejorando la experiencia del usuario.


### Preguntas frecuentes para agregar y eliminar javascript a un documento PDF

#### P: ¿Qué es Aspose.PDF para .NET?

R: Aspose.PDF para .NET es una poderosa biblioteca que permite a los desarrolladores manipular archivos PDF en aplicaciones .NET de manera efectiva. Proporciona amplias funciones para trabajar con documentos PDF mediante programación.

#### P: ¿Cómo puedo agregar JavaScript a un documento PDF usando Aspose.PDF para .NET?

 R: Puede agregar JavaScript a nivel de documento usando el`JavaScript` propiedad de la`Document` clase. Simplemente asigne funciones de JavaScript a claves en el diccionario de JavaScript.

#### P: ¿Puedo eliminar JavaScript de un documento PDF usando Aspose.PDF para .NET?

 R: Sí, puedes eliminar JavaScript de un documento PDF accediendo al`JavaScript` diccionario y eliminando la función JavaScript deseada.

#### P: ¿Aspose.PDF para .NET es adecuado para proyectos profesionales?

R: Por supuesto, Aspose.PDF para .NET se usa ampliamente en proyectos profesionales para tareas de manipulación y generación de PDF. Ofrece alto rendimiento y funcionalidad confiable.

#### P: ¿Qué beneficios proporciona agregar JavaScript a un documento PDF?

R: Agregar JavaScript a un documento PDF le permite crear archivos PDF interactivos y dinámicos. Puede implementar la validación de formularios, realizar cálculos y agregar varias funciones de interactividad para mejorar la experiencia del usuario.