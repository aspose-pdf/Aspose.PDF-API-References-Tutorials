---
title: Aplanar formularios en un documento PDF
linktitle: Aplanar formularios en un documento PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aplane fácilmente formularios en documentos PDF usando Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/programming-with-forms/flatten-forms/
---
En este tutorial, le mostraremos cómo aplanar formularios usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: preparación

Primero, asegúrese de haber importado las bibliotecas necesarias y establecer la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargar el formulario PDF de origen

Cargue el formulario PDF de origen:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 3: aplana los formularios

Primero verifique si hay campos de formulario en el documento. Si es así, repita cada campo y aplique el aplanamiento:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Paso 4: guarde el documento actualizado

Guarde el documento PDF actualizado:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Código fuente de muestra para Flatten Forms usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar formulario PDF fuente
Document doc = new Document(dataDir + "input.pdf");
// Aplanar formularios
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

En este tutorial, aprendimos cómo aplanar formularios usando Aspose.PDF para .NET. Si sigue estos pasos, puede aplanar fácilmente formularios en sus documentos PDF, haciendo que los campos no sean editables y fusionando anotaciones con el contenido del documento.

### Preguntas frecuentes

#### P: ¿Qué significa "aplanar formularios" en Aspose.PDF para .NET?

R: Aplanar formularios en Aspose.PDF para .NET se refiere al proceso de hacer que los campos de formulario en un documento PDF no sean editables y fusionar anotaciones (como campos de formulario, anotaciones y firmas digitales) con el contenido del documento. Una vez que los formularios se aplanan, los usuarios no pueden modificar los campos del formulario y la apariencia visual de los campos del formulario se convierte en parte del contenido estático del documento PDF.

#### P: ¿Puedo revertir el proceso de aplanamiento y volver a editar los campos del formulario?

R: No, una vez que se aplanan los campos del formulario, el proceso es irreversible usando Aspose.PDF para .NET. El aplanamiento fusiona permanentemente la apariencia de los campos del formulario con el contenido del PDF, y los elementos individuales de los campos del formulario ya no son accesibles ni editables.

#### P: ¿Cuándo debo aplanar formularios en un documento PDF?

R: Acoplar formularios es útil cuando desea preservar la apariencia visual de los campos del formulario y las anotaciones en un documento PDF y al mismo tiempo evitar que los usuarios modifiquen los datos. Esto se hace comúnmente cuando desea compartir un documento PDF con datos de formulario precargados o anotaciones que los destinatarios no deben modificar.

#### P: ¿El aplanamiento de formularios afectará otras anotaciones, como las firmas digitales?

R: Sí, al acoplar formularios se fusionarán todas las anotaciones, incluidas las firmas digitales, con el contenido del PDF. Una vez que los formularios se aplanan, cualquier firma digital existente se convertirá en una parte permanente del documento y los usuarios no podrán modificarla ni eliminarla.

#### P: ¿Puedo aplanar selectivamente campos de formulario específicos y dejar otros editables?

R: Sí, puede aplanar selectivamente campos de formulario específicos en un documento PDF y dejar otros editables. En lugar de utilizar el código para aplanar todos los campos del formulario, puede optar por aplanar solo los campos del formulario deseados según sus nombres u otros criterios.