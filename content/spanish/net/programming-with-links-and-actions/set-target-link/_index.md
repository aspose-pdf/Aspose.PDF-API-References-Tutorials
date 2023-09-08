---
title: Establecer enlace de destino en archivo PDF
linktitle: Establecer enlace de destino en archivo PDF
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a configurar un enlace de destino en un archivo PDF usando Aspose.PDF para .NET.
type: docs
weight: 100
url: /es/net/programming-with-links-and-actions/set-target-link/
---
Aprenda cómo configurar un enlace de destino en un archivo PDF usando Aspose.PDF para .NET con esta guía paso a paso.

## Paso 1: configurar el entorno

Asegúrese de haber configurado su entorno de desarrollo con un proyecto C# y las referencias Aspose.PDF adecuadas.

## Paso 2: cargar el archivo PDF

Establezca la ruta del directorio de sus documentos y cargue el archivo PDF usando el siguiente código:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Cargue el archivo PDF
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## Paso 3: editar el enlace de destino

Obtenga la anotación del enlace para modificar usando el siguiente código:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

 Puedes ajustar el`[1]` índices para seleccionar una página o anotación específica.

A continuación, actualice el destino sin actualizar el archivo:

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

Y si también quieres actualizar el archivo:

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## Paso 4: guarde el documento con el enlace actualizado

 Guarde el documento con el enlace actualizado utilizando el`Save` método:

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## Paso 5: Mostrar el resultado

Muestre un mensaje que indique que el enlace de destino se configuró correctamente y especifique la ubicación del archivo guardado:

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### Código fuente de muestra para establecer enlace de destino usando Aspose.PDF para .NET 
```csharp
try
{
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Cargue el archivo PDF
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	// Destino de actualización de la siguiente línea, no actualizar el archivo
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	// Archivo de actualización de siguiente línea
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	// Guarde el documento con el enlace actualizado.
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusión

¡Enhorabuena! Ahora sabe cómo configurar un enlace de destino en un archivo PDF usando Aspose.PDF para .NET. Utilice este conocimiento para personalizar enlaces en sus documentos PDF y crear experiencias interactivas para los usuarios.

Ahora que ha completado esta guía, puede aplicar estos conceptos a sus propios proyectos y explorar más a fondo las funciones que ofrece Aspose.PDF para .NET.

### Preguntas frecuentes sobre cómo establecer el enlace de destino en un archivo PDF

#### P: ¿Qué es un enlace de destino en un archivo PDF?

R: Un enlace de destino en un archivo PDF es un enlace en el que se puede hacer clic y que lleva al lector a un destino específico dentro del mismo documento o a otro archivo PDF.

#### P: ¿Por qué querría establecer un enlace de destino en un archivo PDF?

R: Configurar enlaces de destino le permite crear una experiencia de navegación fluida dentro de un documento PDF o vincular a secciones o páginas específicas dentro de otros archivos PDF.

#### P: ¿Cómo ayuda Aspose.PDF para .NET a configurar enlaces de destino?

R: Aspose.PDF para .NET proporciona API para manipular varios aspectos de los archivos PDF, incluida la creación y modificación de enlaces. Este tutorial demuestra cómo configurar un enlace de destino usando código C#.

#### P: ¿Puedo configurar enlaces de destino para navegar a páginas específicas dentro del mismo documento?

R: Sí, Aspose.PDF para .NET le permite configurar enlaces de destino para navegar a páginas específicas dentro del mismo documento.

#### P: ¿Puedo configurar enlaces de destino para navegar a páginas específicas en otro archivo PDF?

R: Sí, puede configurar enlaces de destino para navegar a páginas específicas dentro de otro archivo PDF usando Aspose.PDF para .NET.

#### P: ¿Existe alguna limitación para establecer enlaces de destino?

R: Los enlaces de destino solo pueden navegar dentro del mismo documento o a páginas específicas dentro de otros archivos PDF. No pueden vincular directamente a contenido específico dentro de otros documentos.

#### P: ¿Cómo puedo personalizar la apariencia de un enlace de destino?

R: La apariencia de un enlace de destino, como su color y estilo, se puede personalizar utilizando las propiedades proporcionadas por Aspose.PDF para .NET.

#### P: ¿Puedo configurar varios enlaces de destino en el mismo documento PDF?

R: Sí, puede configurar varios enlaces de destino en el mismo documento PDF. Simplemente repita el proceso para cada enlace que desee crear.

#### P: ¿Puedo establecer un enlace de destino usando una forma o texto específico?

R: Sí, puede adjuntar un enlace de destino a formas o texto específicos dentro del documento PDF utilizando las propiedades y métodos apropiados proporcionados por Aspose.PDF para .NET.

#### P: ¿Cómo puedo probar si el enlace de destino funciona según lo previsto?

R: Después de configurar el enlace de destino utilizando el código proporcionado, abra el PDF modificado y haga clic en el enlace para asegurarse de que navega hasta el destino deseado.

#### P: ¿Puedo establecer enlaces de destino en archivos PDF protegidos con contraseña?

R: Sí, puede establecer enlaces de destino en archivos PDF protegidos con contraseña siempre que proporcione las credenciales adecuadas para acceder y modificar el documento.