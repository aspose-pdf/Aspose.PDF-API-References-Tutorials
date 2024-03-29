---
title: Especificar página al visualizar
linktitle: Especificar página al visualizar
second_title: Aspose.PDF para referencia de API .NET
description: Aprenda a especificar una página al visualizar un PDF usando Aspose.PDF para .NET.
type: docs
weight: 110
url: /es/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Aprenda cómo especificar una página al visualizar un archivo PDF usando Aspose.PDF para .NET con esta guía paso a paso.

## Paso 1: configurar el entorno

Asegúrese de haber configurado su entorno de desarrollo con un proyecto C# y las referencias Aspose.PDF adecuadas.

## Paso 2: cargar el archivo PDF

Establezca la ruta del directorio de sus documentos y cargue el archivo PDF usando el siguiente código:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Cargue el archivo PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Paso 3: especificar la página de destino

Obtenga la instancia de la página de destino utilizando el siguiente código:

```csharp
Page page2 = doc.Pages[2];
```

 Puedes ajustar el índice.`[2]` para seleccionar la página deseada.

## Paso 4: Configurar la configuración del zoom

Cree una variable para establecer el factor de zoom de la página de destino:

```csharp
double zoom = 1;
```

Puede ajustar el valor del zoom según sus necesidades.

## Paso 5: crear la acción de navegación

Cree una instancia de la acción de navegación utilizando la página de destino especificada:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Paso 6: Configurar el destino

Establezca el destino para ir a la página de destino usando coordenadas y zoom:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Paso 7: Configurar la acción de apertura de documento

Configure la acción de apertura del documento con la acción de navegación creada:

```csharp
doc. OpenAction = action;
```

## Paso 8: guarde el documento actualizado

 Guarde el documento actualizado usando el`Save` método:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Código fuente de muestra para Especificar página al visualizar usando Aspose.PDF para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cargue el archivo PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Obtener la instancia de la segunda página del documento.
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

¡Enhorabuena! Ahora sabe cómo especificar una página al visualizar un PDF usando Aspose.PDF para .NET. Utilice este conocimiento para personalizar la experiencia de visualización del usuario en sus documentos PDF.

Ahora que ha completado esta guía, puede aplicar estos conceptos a sus propios proyectos y explorar más a fondo las funciones que ofrece Aspose.PDF para .NET.

### Preguntas frecuentes 

#### P: ¿Cuál es el propósito de especificar una página de destino al visualizar un archivo PDF?

R: Especificar una página de destino le permite controlar qué página de un documento PDF se muestra cuando se abre el archivo. Esto puede mejorar la experiencia del usuario dirigiéndolo a una página de interés específica.

#### P: ¿Cómo puede resultar útil especificar una página de destino en documentos PDF?

R: Especificar una página de destino es beneficioso cuando desea guiar a los usuarios a una sección o contenido particular dentro de un documento PDF sin necesidad de navegar manualmente por las páginas.

#### P: ¿Cómo facilita Aspose.PDF para .NET la especificación de una página de destino para su visualización?

R: Aspose.PDF para .NET proporciona API que le permiten configurar la vista inicial de un documento PDF, incluida la página de destino, el nivel de zoom y otras propiedades de visualización.

#### P: ¿Puedo especificar cualquier página como página de destino?

R: Sí, puede especificar cualquier página dentro del documento PDF como página de destino para su visualización. Simplemente utilice el índice apropiado para seleccionar la página deseada.

#### P: ¿Cuál es la importancia del factor de zoom al especificar una página de destino?

R: El factor de zoom determina el nivel de ampliación aplicado a la página de destino cuando se abre el documento PDF. Controla la cantidad de contenido que se muestra dentro de la ventana gráfica.

#### P: ¿Puedo establecer diferentes factores de zoom para diferentes páginas de destino?

R: Sí, puede establecer diferentes factores de zoom para diferentes páginas de destino creando`GoToAction` instancias y configurar sus destinos en consecuencia.

#### P: ¿Existe alguna limitación para especificar una página de destino?

R: La especificación de una página de destino se limita a controlar la vista inicial cuando se abre el PDF. No afecta las interacciones del usuario ni la navegación una vez que se muestra el PDF.

#### P: ¿Puedo utilizar esta función para crear presentaciones dentro de un documento PDF?

R: Sí, puede utilizar esta función para crear experiencias similares a presentaciones dentro de un documento PDF, guiando a los usuarios a través de diferentes secciones o temas.

#### P: ¿Puedo personalizar otros aspectos de la vista inicial, como el diseño de la página?

R: Sí, Aspose.PDF para .NET proporciona propiedades para personalizar otros aspectos de la vista inicial, incluido el diseño de página, el modo de página y más.

#### P: ¿Cómo puedo comprobar si la página de destino especificada y el factor de zoom funcionan según lo previsto?

R: Después de aplicar el código proporcionado para especificar la página de destino y el factor de zoom, abra el archivo PDF modificado y verifique que se abra con la página y el nivel de zoom correctos.