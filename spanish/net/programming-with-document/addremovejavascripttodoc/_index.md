---
title: Agregar Quitar Javascript al documento
linktitle: Agregar Quitar Javascript al documento
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a agregar y quitar JavaScript de documentos PDF usando Aspose.PDF para .NET. Guía paso a paso con tutoriales de código para secuencias de comandos a nivel de documento.
type: docs
weight: 30
url: /es/net/programming-with-document/addremovejavascripttodoc/
---

Para agregar y eliminar JavaScript de los documentos PDF, utilizaremos la biblioteca Aspose.PDF para .NET. Esta poderosa biblioteca nos permite manipular archivos PDF en aplicaciones .NET. Siga las instrucciones paso a paso a continuación para agregar y quitar JavaScript usando Aspose.PDF para .NET.

## Paso 1: cree un nuevo documento PDF

 Comience por crear una nueva instancia de la`Document` clase proporcionada por Aspose.PDF para .NET. Esto servirá como el documento PDF donde agregaremos el JavaScript.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Paso 2: agregue JavaScript a nivel de documento

 Para agregar JavaScript a nivel de documento, use el`JavaScript` propiedad de la`Document` clase. Asigne funciones de JavaScript a las claves en el diccionario de JavaScript.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 En este tutorial, hemos agregado dos funciones de JavaScript,`func1` y`func2`, al documento PDF.

## Paso 3: Eliminar JavaScript de nivel de documento

 Para eliminar JavaScript a nivel de documento, cargue el documento PDF y acceda a la`JavaScript`diccionario. Repita las claves y elimine la función de JavaScript deseada.

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

## Paso 4: Guardar y verificar los cambios

Guarde el documento PDF modificado y verifique los cambios.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Este código guardará el documento PDF modificado y mostrará el mensaje de éxito.

### Ejemplo de código fuente para Agregar Quitar Javascript de documentos PDF usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// Eliminar JavaScript de nivel de documento
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

En este artículo, proporcionamos una guía paso a paso para agregar y eliminar JavaScript de documentos PDF usando Aspose.PDF para .NET. Siguiendo las instrucciones y utilizando los tutoriales de código proporcionados, puede incorporar fácilmente JavaScript en sus documentos PDF y eliminarlo cuando sea necesario. JavaScript permite la funcionalidad dinámica y la interactividad en sus archivos PDF, lo que mejora la experiencia del usuario.