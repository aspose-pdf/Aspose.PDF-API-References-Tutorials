---
title: Especificar la página al visualizarla
linktitle: Especificar la página al visualizarla
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a especificar una página al ver un PDF usando Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Aprenda a especificar una página al ver un archivo PDF usando Aspose.PDF para .NET con esta guía paso a paso.

## Paso 1: Configuración del entorno

Asegúrese de haber configurado su entorno de desarrollo con un proyecto C# y las referencias Aspose.PDF adecuadas.

## Paso 2: Cargar el archivo PDF

Establezca la ruta del directorio de sus documentos y cargue el archivo PDF usando el siguiente código:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Cargar el archivo PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Paso 3: Especificar la página de destino

Obtenga la instancia de la página de destino utilizando el siguiente código:

```csharp
Page page2 = doc.Pages[2];
```

 Puedes ajustar el índice`[2]` para seleccionar la página deseada.

## Paso 4: Configurar el ajuste de zoom

Cree una variable para establecer el factor de zoom de la página de destino:

```csharp
double zoom = 1;
```

Puede ajustar el valor del zoom según sus necesidades.

## Paso 5: Crea la acción de navegación

Crea una instancia de la acción de navegación utilizando la página de destino especificada:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Paso 6: Establecer el destino

Establezca el destino para ir a la página de destino mediante coordenadas y zoom:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Paso 7: Configuración de la acción de abrir documento

Establezca la acción de apertura del documento con la acción de navegación creada:

```csharp
doc. OpenAction = action;
```

## Paso 8: Guarde el documento actualizado

 Guarde el documento actualizado utilizando el`Save` método:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Código fuente de muestra para especificar la página al visualizarla con Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargar el archivo PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Obtener la instancia de la segunda página del documento
Page page2 = doc.Pages[2];
// Crea la variable para establecer el factor de zoom de la página de destino
double zoom = 1;
// Crear una instancia de GoToAction
GoToAction action = new GoToAction(doc.Pages[2]);
// Ir a la página 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Establecer la acción de apertura del documento
doc.OpenAction = action;
// Guardar documento actualizado
doc.Save(dataDir + "goto2page_out.pdf");
```

## Conclusión

¡Felicitaciones! Ahora sabe cómo especificar una página al visualizar un PDF con Aspose.PDF para .NET. Utilice este conocimiento para personalizar la experiencia de visualización del usuario en sus documentos PDF.

Ahora que ha completado esta guía, puede aplicar estos conceptos a sus propios proyectos y explorar más a fondo las características que ofrece Aspose.PDF para .NET.

### Preguntas frecuentes 

#### P: ¿Cuál es el propósito de especificar una página de destino al visualizar un archivo PDF?

A: Especificar una página de destino le permite controlar qué página de un documento PDF se muestra cuando se abre el archivo. Esto puede mejorar la experiencia del usuario al dirigirlo a una página específica de interés.

#### P: ¿Cómo puede ser útil especificar una página de destino en documentos PDF?

R: Especificar una página de destino es beneficioso cuando desea guiar a los usuarios a una sección o contenido particular dentro de un documento PDF sin necesidad de navegar manualmente por las páginas.

#### P: ¿Cómo facilita Aspose.PDF para .NET la especificación de una página de destino para su visualización?

R: Aspose.PDF para .NET proporciona API que le permiten configurar la vista inicial de un documento PDF, incluida la página de destino, el nivel de zoom y otras propiedades de visualización.

#### P: ¿Puedo especificar cualquier página como página de destino?

R: Sí, puede especificar cualquier página dentro del documento PDF como la página de destino para visualizar. Simplemente utilice el índice apropiado para seleccionar la página deseada.

#### P: ¿Cuál es la importancia del factor de zoom al especificar una página de destino?

A: El factor de zoom determina el nivel de ampliación que se aplica a la página de destino cuando se abre el documento PDF. Controla la cantidad de contenido que se muestra en la ventana gráfica.

#### P: ¿Puedo establecer diferentes factores de zoom para diferentes páginas de destino?

R: Sí, puede establecer diferentes factores de zoom para diferentes páginas de destino creando páginas separadas.`GoToAction` instancias y configurar sus destinos en consecuencia.

#### P: ¿Existe alguna limitación para especificar una página de destino?

R: La especificación de una página de destino se limita a controlar la vista inicial cuando se abre el PDF. No afecta las interacciones ni la navegación del usuario una vez que se muestra el PDF.

#### P: ¿Puedo utilizar esta función para crear presentaciones dentro de un documento PDF?

R: Sí, puede utilizar esta función para crear experiencias similares a presentaciones dentro de un documento PDF, guiando a los usuarios a través de diferentes secciones o temas.

#### P: ¿Puedo personalizar otros aspectos de la vista inicial, como el diseño de la página?

R: Sí, Aspose.PDF para .NET proporciona propiedades para personalizar otros aspectos de la vista inicial, incluido el diseño de la página, el modo de página y más.

#### P: ¿Cómo puedo probar si la página de destino especificada y el factor de zoom funcionan según lo previsto?

R: Después de aplicar el código proporcionado para especificar la página de destino y el factor de zoom, abra el archivo PDF modificado y verifique que se abra con la página y el nivel de zoom correctos.