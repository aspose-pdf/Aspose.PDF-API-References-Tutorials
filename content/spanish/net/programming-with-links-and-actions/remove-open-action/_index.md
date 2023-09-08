---
title: Eliminar acción abierta
linktitle: Eliminar acción abierta
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda cómo eliminar la acción de abrir de un PDF usando Aspose.PDF para .NET.
type: docs
weight: 80
url: /es/net/programming-with-links-and-actions/remove-open-action/
---
Aprenda cómo eliminar la acción de abrir de un archivo PDF usando Aspose.PDF para .NET con esta guía paso a paso.

## Paso 1: configurar el entorno

Asegúrese de haber configurado su entorno de desarrollo con un proyecto C# y las referencias Aspose.PDF adecuadas.

## Paso 2: cargar el archivo PDF

Establezca la ruta del directorio de sus documentos y cargue el archivo PDF usando el siguiente código:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// abrir el documento
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Paso 3: Eliminar la acción abierta

 Elimine la acción de apertura del documento configurando el`OpenAction` propiedad a nula:

```csharp
document. OpenAction = null;
```

## Paso 4: guarde el documento actualizado

 Guarde el documento actualizado usando el`Save` método:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Paso 5: Mostrar el resultado

Muestre un mensaje que indique que la acción de apertura se eliminó correctamente y especifique la ubicación del archivo guardado:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Código fuente de muestra para Eliminar acción abierta usando Aspose.PDF para .NET 
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

¡Enhorabuena! Ahora ya sabe cómo eliminar la acción de apertura de un PDF usando Aspose.PDF para .NET. Utilice este conocimiento para personalizar las propiedades y el comportamiento de los archivos PDF en sus proyectos.

Ahora que ha completado esta guía, puede aplicar estos conceptos a sus propios proyectos y explorar más a fondo las funciones que ofrece Aspose.PDF para .NET.

### Preguntas frecuentes 

#### P: ¿Qué es la "acción de abrir" en un archivo PDF?

R: La "acción de abrir" en un archivo PDF es una instrucción que especifica lo que debe suceder cuando se abre el PDF. Puede incluir acciones como navegar a una página o ubicación específica dentro del documento, iniciar una aplicación externa o mostrar una vista específica.

#### P: ¿Por qué querría eliminar la acción de abrir de un archivo PDF?

R: Eliminar la acción de abrir puede mejorar la seguridad, la experiencia del usuario y el control sobre cómo se presenta el PDF cuando se abre. Por ejemplo, es posible que desee evitar la navegación automática o desactivar ciertas acciones al abrir el documento.

#### P: ¿Cómo ayuda Aspose.PDF para .NET a eliminar la acción de abrir?

R: Aspose.PDF para .NET proporciona API para manipular varios aspectos de los archivos PDF. Este tutorial muestra cómo eliminar la acción de apertura usando código C#.

#### P: ¿Existen riesgos o consideraciones potenciales al eliminar la acción abierta?

R: Eliminar la acción de abrir puede alterar el comportamiento predeterminado del PDF, así que asegúrese de que se ajuste a la experiencia del usuario prevista. Pruebe minuciosamente el PDF modificado para confirmar que la eliminación no afecta otras funcionalidades.

#### P: ¿Puedo personalizar la acción de abrir para realizar otras acciones?

R: Sí, Aspose.PDF para .NET le permite personalizar la acción de apertura configurándola en varios tipos de acciones, como navegar a una página específica o ejecutar JavaScript.

#### P: ¿Puedo eliminar acciones abiertas de archivos PDF protegidos con contraseña?
R: Sí, puede eliminar acciones abiertas de archivos PDF protegidos con contraseña siempre que proporcione las credenciales adecuadas para acceder y modificar el documento.

#### P: ¿Es reversible la eliminación de la acción abierta?

R: No, una vez que se elimina la acción de apertura y se guarda el PDF, la acción de apertura original no se puede restaurar desde el PDF modificado.

#### P: ¿Cómo verifico que la acción de apertura se eliminó correctamente?

R: Después de eliminar la acción de abrir usando el código proporcionado, abra el PDF modificado y confirme que no se produzca ninguna acción específica al abrirlo.

#### P: ¿Puedo eliminar acciones abiertas de varios archivos PDF simultáneamente?

R: Sí, puede utilizar el mismo método para eliminar acciones abiertas de varios archivos PDF en un escenario de procesamiento por lotes.