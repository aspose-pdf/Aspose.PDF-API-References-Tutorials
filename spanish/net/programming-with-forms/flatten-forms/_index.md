---
title: Aplanar formularios en documento PDF
linktitle: Aplanar formularios en documento PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aplane fácilmente formularios en documentos PDF usando Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/programming-with-forms/flatten-forms/
---
En este tutorial, le mostraremos cómo aplanar formularios usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Primero, asegúrese de haber importado las bibliotecas necesarias y establezca la ruta al directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el formulario PDF de origen

Cargue el formulario PDF de origen:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Paso 3: aplana los formularios

Primero verifique si hay campos de formulario en el documento. Si es así, itere a través de cada campo y aplique aplanamiento:

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

### Ejemplo de código fuente para Flatten Forms usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar formulario PDF de origen
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

En este tutorial, aprendimos a aplanar formularios con Aspose.PDF para .NET. Siguiendo estos pasos, puede acoplar fácilmente formularios en sus documentos PDF, haciendo que los campos no se puedan editar y fusionando anotaciones con el contenido del documento.

### Preguntas frecuentes

#### P: ¿Qué significa "aplanar formularios" en Aspose.PDF para .NET?

R: Aplanar formularios en Aspose.PDF para .NET se refiere al proceso de hacer que los campos de formulario en un documento PDF no se puedan editar y fusionar anotaciones (como campos de formulario, anotaciones y firmas digitales) con el contenido del documento. Una vez que se aplanan los formularios, los usuarios no pueden modificar los campos del formulario y la apariencia visual de los campos del formulario se convierte en parte del contenido estático del documento PDF.

#### P: ¿Puedo revertir el proceso de aplanamiento y volver a hacer que los campos del formulario sean editables?

R: No, una vez que se aplanan los campos del formulario, el proceso es irreversible usando Aspose.PDF para .NET. El aplanamiento fusiona permanentemente la apariencia de los campos de formulario con el contenido del PDF, y los elementos de campo de formulario individuales ya no son accesibles ni editables.

#### P: ¿Cuándo debo acoplar formularios en un documento PDF?

R: Aplanar formularios es útil cuando desea conservar la apariencia visual de los campos de formulario y las anotaciones en un documento PDF y evitar que los usuarios modifiquen los datos. Esto se hace comúnmente cuando desea compartir un documento PDF con datos de formulario precargados o anotaciones que los destinatarios no deben modificar.

#### P: ¿Afectará el aplanamiento de formularios a otras anotaciones, como las firmas digitales?

R: Sí, los formularios acoplados fusionarán todas las anotaciones, incluidas las firmas digitales, con el contenido del PDF. Una vez que se aplanan los formularios, las firmas digitales existentes se convertirán en una parte permanente del documento y los usuarios no podrán modificarlas ni eliminarlas.

#### P: ¿Puedo aplanar selectivamente campos de formulario específicos y dejar otros editables?

R: Sí, puede aplanar selectivamente campos de formulario específicos en un documento PDF y dejar otros editables. En lugar de utilizar el código para aplanar todos los campos del formulario, puede optar por aplanar solo los campos del formulario que desee en función de sus nombres u otros criterios.