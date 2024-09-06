---
title: Eliminar acción abierta
linktitle: Eliminar acción abierta
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a eliminar la acción de abrir de un PDF usando Aspose.PDF para .NET.
type: docs
weight: 80
url: /es/net/programming-with-links-and-actions/remove-open-action/
---
Aprenda a eliminar la acción de apertura de un archivo PDF usando Aspose.PDF para .NET con esta guía paso a paso.

## Paso 1: Configuración del entorno

Asegúrese de haber configurado su entorno de desarrollo con un proyecto C# y las referencias Aspose.PDF adecuadas.

## Paso 2: Cargar el archivo PDF

Establezca la ruta del directorio de sus documentos y cargue el archivo PDF usando el siguiente código:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Abrir el documento
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Paso 3: Eliminar la acción abierta

 Elimine la acción de apertura del documento configurando la`OpenAction` propiedad a nula:

```csharp
document. OpenAction = null;
```

## Paso 4: Guarde el documento actualizado

 Guarde el documento actualizado utilizando el`Save` método:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Paso 5: Visualización del resultado

Muestra un mensaje que indica que la acción abierta se eliminó correctamente y especifica la ubicación del archivo guardado:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Código fuente de muestra para la acción Eliminar apertura con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Eliminar acción de apertura de documento
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Guardar documento actualizado
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Conclusión

¡Felicitaciones! Ahora ya sabe cómo eliminar la acción de abrir de un PDF con Aspose.PDF para .NET. Utilice este conocimiento para personalizar las propiedades y el comportamiento de los archivos PDF en sus proyectos.

Ahora que ha completado esta guía, puede aplicar estos conceptos a sus propios proyectos y explorar más a fondo las características que ofrece Aspose.PDF para .NET.

### Preguntas frecuentes 

#### P: ¿Qué es la "acción abrir" en un archivo PDF?

R: La "acción de apertura" en un archivo PDF es una instrucción que especifica lo que debe suceder cuando se abre el PDF. Puede incluir acciones como navegar a una página o ubicación específica dentro del documento, iniciar una aplicación externa o mostrar una vista específica.

#### P: ¿Por qué querría eliminar la acción de abrir de un archivo PDF?

R: Eliminar la acción de abrir puede mejorar la seguridad, la experiencia del usuario y el control sobre cómo se presenta el PDF al abrirlo. Por ejemplo, es posible que desee evitar la navegación automática o deshabilitar ciertas acciones al abrir el documento.

#### P: ¿Cómo ayuda Aspose.PDF para .NET a eliminar la acción de abrir?

A: Aspose.PDF para .NET ofrece API para manipular diversos aspectos de los archivos PDF. Este tutorial demuestra cómo eliminar la acción de apertura mediante código C#.

#### P: ¿Existen posibles riesgos o consideraciones a tener en cuenta al eliminar la acción abierta?

R: Eliminar la acción de abrir puede alterar el comportamiento predeterminado del PDF, por lo que debe asegurarse de que coincida con la experiencia de usuario deseada. Pruebe el PDF modificado a fondo para confirmar que la eliminación no afecte otras funciones.

#### P: ¿Puedo personalizar la acción de apertura para realizar otras acciones?

R: Sí, Aspose.PDF para .NET le permite personalizar la acción de apertura configurándola para varios tipos de acciones, como navegar a una página específica o ejecutar JavaScript.

#### P: ¿Puedo eliminar acciones abiertas de archivos PDF protegidos con contraseña?
R: Sí, puede eliminar acciones abiertas de archivos PDF protegidos con contraseña siempre que proporcione las credenciales adecuadas para acceder y modificar el documento.

#### P: ¿Es reversible la eliminación de la acción abierta?

R: No, una vez que se elimina la acción de apertura y se guarda el PDF, la acción de apertura original no se puede restaurar desde el PDF modificado.

#### P: ¿Cómo puedo verificar que la acción abierta se eliminó correctamente?

R: Después de eliminar la acción de apertura usando el código proporcionado, abra el PDF modificado y confirme que no se produzca ninguna acción específica al abrirlo.

#### P: ¿Puedo eliminar acciones abiertas de varios archivos PDF simultáneamente?

R: Sí, puede utilizar el mismo enfoque para eliminar acciones abiertas de varios archivos PDF en un escenario de procesamiento por lotes.