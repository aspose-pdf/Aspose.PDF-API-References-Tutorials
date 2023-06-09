---
title: Preservar los derechos
linktitle: Preservar los derechos
second_title: Referencia de API de Aspose.PDF para .NET
description: Conserve los derechos de formulario en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 210
url: /es/net/programming-with-forms/preserve-rights/
---

En este tutorial, le mostraremos cómo conservar los derechos de formulario en un documento PDF utilizando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: Preparación

Asegúrese de haber importado las bibliotecas necesarias y establezca la ruta a su directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: abre el documento

 Abra el documento PDF de origen con un`FileStream` con permiso de lectura y escritura:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Paso 3: Editar campos de formulario

Revise todos los campos del formulario en el documento y realice los cambios necesarios. En este ejemplo, estamos cambiando el valor de un campo de formulario que tiene "A1" en su nombre:

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## Paso 4: Guarde el documento actualizado

Guarde el documento PDF modificado:

```csharp
pdfDocument.Save();
```

##  Paso 5: Cierra el`FileStream`

 No olvides cerrar el`FileStream` objeto cuando hayas terminado:

```csharp
fs. Close();
```

### Ejemplo de código fuente para Preservar derechos usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Lea el formulario PDF de origen con FileAccess de lectura y escritura.
// Necesitamos permiso de lectura y escritura porque después de la modificación,
// Necesitamos guardar los contenidos actualizados en el mismo documento/archivo.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Instanciar instancia de documento
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Obtener valores de todos los campos
foreach (Field formField in pdfDocument.Form)
{
	// Si el nombre completo del campo contiene A1, realice la operación
	if (formField.FullName.Contains("A1"))
	{
		// Enviar campo de formulario como cuadro de texto
		TextBoxField textBoxField = formField as TextBoxField;
		// Modificar valor de campo
		textBoxField.Value = "Testing";
	}
}
// Guarde el documento actualizado en guardar FileStream
pdfDocument.Save();
// Cierre el objeto File Stream
fs.Close();
```

## Conclusión

En este tutorial, aprendimos cómo conservar los derechos de un formulario en un documento PDF usando Aspose.PDF para .NET. Siguiendo estos pasos, puede acceder fácilmente a los campos del formulario y realizar cambios específicos mientras conserva los permisos de acceso y escritura.
