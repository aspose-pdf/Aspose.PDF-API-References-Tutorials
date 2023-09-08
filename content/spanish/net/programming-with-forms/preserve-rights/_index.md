---
title: Preservar los derechos
linktitle: Preservar los derechos
second_title: Aspose.PDF para referencia de API .NET
description: Conserve los derechos de formulario en sus documentos PDF con Aspose.PDF para .NET.
type: docs
weight: 210
url: /es/net/programming-with-forms/preserve-rights/
---
En este tutorial, le mostraremos cómo preservar los derechos de formulario en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# paso a paso para guiarlo a través de este proceso.

## Paso 1: preparación

Asegúrese de haber importado las bibliotecas necesarias y establecer la ruta a su directorio de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: abre el documento

 Abra el documento PDF de origen utilizando un`FileStream` con permiso de lectura y escritura:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Paso 3: editar los campos del formulario

Revise todos los campos del formulario en el documento y realice los cambios necesarios. En este ejemplo, cambiaremos el valor de un campo de formulario que tiene "A1" en su nombre:

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

## Paso 4: guarde el documento actualizado

Guarde el documento PDF modificado:

```csharp
pdfDocument.Save();
```

##  Paso 5: cierre el`FileStream`

 No olvides cerrar el`FileStream` objeto cuando hayas terminado:

```csharp
fs. Close();
```

### Código fuente de muestra para Preservar derechos usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Lea el formulario PDF de origen con FileAccess de lectura y escritura.
// Necesitamos permiso de lectura y escritura porque después de la modificación,
// Necesitamos guardar el contenido actualizado en el mismo documento/archivo.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Crear una instancia de documento
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Obtener valores de todos los campos
foreach (Field formField in pdfDocument.Form)
{
	// Si el nombre completo del campo contiene A1, realice la operación
	if (formField.FullName.Contains("A1"))
	{
		// Transmitir campo de formulario como TextBox
		TextBoxField textBoxField = formField as TextBoxField;
		// Modificar valor de campo
		textBoxField.Value = "Testing";
	}
}
// Guarde el documento actualizado en guardar FileStream
pdfDocument.Save();
// Cerrar el objeto File Stream
fs.Close();
```

## Conclusión

En este tutorial, aprendimos cómo preservar los derechos de un formulario en un documento PDF usando Aspose.PDF para .NET. Si sigue estos pasos, podrá acceder fácilmente a los campos del formulario y realizar cambios específicos mientras conserva los permisos de acceso y escritura.


### Preguntas frecuentes

#### P: ¿Puedo conservar los derechos de campos de formulario específicos sin afectar a otros en el documento PDF?

 R: Sí, usando el`FullName` propiedad de los campos del formulario, puede seleccionar campos de formulario específicos para conservarlos sin afectar a otros.

#### P: ¿Puedo conservar los derechos de un formulario en un documento PDF protegido con contraseña?

R: Sí, Aspose.PDF para .NET le permite conservar los derechos de un formulario incluso en documentos PDF protegidos con contraseña, siempre que proporcione la contraseña correcta para acceder y modificar el archivo.

#### P: ¿Qué sucede si intento modificar los campos del formulario sin los derechos de acceso adecuados?

R: Si intenta modificar los campos del formulario sin los derechos de acceso adecuados, los cambios no se guardarán en el documento PDF y es posible que reciba una excepción o un mensaje de error.

#### P: ¿Aspose.PDF para .NET es compatible con todas las versiones de .NET Framework?

R: Sí, Aspose.PDF para .NET es compatible con todas las versiones de .NET Framework, incluidos .NET Core y .NET Standard.

#### P: ¿Puedo conservar los derechos de formulario en un documento PDF mediante programación en otros lenguajes de programación además de C#?

R: Sí, Aspose.PDF para .NET admite varios lenguajes de programación, como VB.NET y ASP.NET, además de C#.