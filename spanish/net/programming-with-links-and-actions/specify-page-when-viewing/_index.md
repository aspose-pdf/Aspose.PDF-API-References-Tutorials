---
title: Especificar página al ver
linktitle: Especificar página al ver
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a especificar una página al ver un PDF con Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/programming-with-links-and-actions/specify-page-when-viewing/
---

Aprenda a especificar una página al ver un archivo PDF con Aspose.PDF para .NET con esta guía paso a paso.

## Paso 1: Configuración del entorno

Asegúrese de haber configurado su entorno de desarrollo con un proyecto C# y las referencias de Aspose.PDF adecuadas.

## Paso 2: Cargar el archivo PDF

Establezca la ruta del directorio de sus documentos y cargue el archivo PDF usando el siguiente código:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Cargue el archivo PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Paso 3: Especificar la página de destino

Obtenga la instancia de la página de destino usando el siguiente código:

```csharp
Page page2 = doc.Pages[2];
```

 Puede ajustar el índice`[2]` para seleccionar la página deseada.

## Paso 4: Configuración del ajuste de zoom

Cree una variable para establecer el factor de zoom de la página de destino:

```csharp
double zoom = 1;
```

Puede ajustar el valor del zoom según sus necesidades.

## Paso 5: Crear la acción de navegación

Cree una instancia de la acción de navegación utilizando la página de destino especificada:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Paso 6: Establecer el destino

Establezca el destino para ir a la página de destino usando coordenadas y zoom:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Paso 7: Configuración de la acción Abrir documento

Configure la acción de apertura del documento con la acción de navegación creada:

```csharp
doc. OpenAction = action;
```

## Paso 8: Guarde el documento actualizado

 Guarde el documento actualizado usando el`Save` método:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Ejemplo de código fuente para Especificar página al visualizar usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargue el archivo PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Obtener la instancia de la segunda página del documento
Page page2 = doc.Pages[2];
// Cree la variable para establecer el factor de zoom de la página de destino
double zoom = 1;
// Crear instancia de GoToAction
GoToAction action = new GoToAction(doc.Pages[2]);
// Ir a la página 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Establecer la acción de apertura del documento
doc.OpenAction = action;
// Guardar documento actualizado
doc.Save(dataDir + "goto2page_out.pdf");
```

## Conclusión

¡Felicidades! Ahora sabe cómo especificar una página al ver un PDF con Aspose.PDF para .NET. Utilice este conocimiento para personalizar la experiencia de visualización del usuario en sus documentos PDF.

Ahora que completó esta guía, puede aplicar estos conceptos a sus propios proyectos y seguir explorando las características que ofrece Aspose.PDF para .NET.