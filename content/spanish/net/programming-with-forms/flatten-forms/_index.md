---
title: Aplanar formularios en documentos PDF
linktitle: Aplanar formularios en documentos PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aplana fácilmente formularios en documentos PDF usando Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/programming-with-forms/flatten-forms/
---
En este tutorial, le mostraremos cómo aplanar formularios con Aspose.PDF para .NET. Le explicaremos el código fuente de C# paso a paso para guiarlo en este proceso.

## Paso 1: Preparación

Primero, asegúrese de haber importado las bibliotecas necesarias y configure la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el formulario PDF de origen

Cargar el formato PDF de origen:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 3: Aplanar las formas

Primero, verifique si hay campos de formulario en el documento. Si es así, recorra cada campo y aplique el aplanamiento:

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

### Código fuente de muestra para aplanar formularios con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar fuente de formato PDF
Document doc = new Document(dataDir + "input.pdf");
// Aplanar formas
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

En este tutorial, aprendimos a aplanar formularios con Aspose.PDF para .NET. Si sigue estos pasos, podrá aplanar fácilmente los formularios en sus documentos PDF, haciendo que los campos no se puedan editar y fusionando las anotaciones con el contenido del documento.

### Preguntas frecuentes

#### P: ¿Qué significa "aplanar formularios" en Aspose.PDF para .NET?

A: La aplanación de formularios en Aspose.PDF para .NET se refiere al proceso de hacer que los campos de formulario de un documento PDF no se puedan editar y de fusionar las anotaciones (como campos de formulario, anotaciones y firmas digitales) con el contenido del documento. Una vez que se aplanan los formularios, los usuarios no pueden modificar los campos de formulario y la apariencia visual de los campos de formulario se convierte en parte del contenido estático del documento PDF.

#### P: ¿Puedo revertir el proceso de aplanamiento y hacer que los campos del formulario sean editables nuevamente?

R: No, una vez que se aplanan los campos del formulario, el proceso es irreversible si se utiliza Aspose.PDF para .NET. La aplanación fusiona permanentemente la apariencia de los campos del formulario con el contenido del PDF, y los elementos individuales de los campos del formulario ya no son accesibles ni editables.

#### P: ¿Cuándo debo aplanar formularios en un documento PDF?

R: La combinación de formularios es útil cuando se desea conservar la apariencia visual de los campos de formulario y las anotaciones en un documento PDF y evitar que los usuarios modifiquen los datos. Esto se hace habitualmente cuando se desea compartir un documento PDF con datos de formulario o anotaciones precompletados que los destinatarios no deben modificar.

#### P: ¿La nivelación de formularios afectará otras anotaciones, como las firmas digitales?

R: Sí, al aplanar los formularios se fusionarán todas las anotaciones, incluidas las firmas digitales, con el contenido del PDF. Una vez que se hayan aplanado los formularios, las firmas digitales existentes pasarán a ser parte permanente del documento y los usuarios no podrán modificarlas ni eliminarlas.

#### P: ¿Puedo aplanar selectivamente campos de formulario específicos y dejar otros editables?

R: Sí, puede aplanar selectivamente campos de formulario específicos en un documento PDF y dejar otros editables. En lugar de usar el código para aplanar todos los campos de formulario, puede optar por aplanar solo los campos de formulario deseados en función de sus nombres u otros criterios.