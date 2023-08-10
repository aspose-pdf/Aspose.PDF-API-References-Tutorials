---
title: Obtener factor de zoom en archivo PDF
linktitle: Obtener factor de zoom en archivo PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a usar Aspose.PDF para .NET para obtener el factor de zoom en un archivo PDF con esta guía paso a paso.
type: docs
weight: 210
url: /es/net/programming-with-document/getzoomfactor/
---
Aspose.PDF para .NET es una biblioteca de manipulación de PDF que proporciona muchas funciones para realizar diversas operaciones en documentos PDF. Una de estas características es la capacidad de obtener el factor de zoom en un archivo PDF. En este tutorial, explicaremos cómo usar Aspose.PDF para .NET para obtener el factor de zoom en un archivo PDF usando el código fuente de C#.


## Paso 1: crear una instancia del nuevo objeto de documento

 El primer paso para obtener el factor de zoom de un archivo PDF utilizando Aspose.PDF para .NET es crear una instancia de un nuevo`Document` objeto. El`Document` El objeto representa un documento PDF que se puede cargar desde un archivo o una secuencia.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar un nuevo objeto de documento
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 En el código anterior, hemos creado un`Document` objeto pasando la ruta del archivo PDF al constructor del`Document` clase. Debe reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real del directorio donde se encuentra su archivo PDF.

## Paso 2: Crear objeto GoToAction

 El siguiente paso es crear un`GoToAction` objeto. A`GoToAction`objeto representa una acción que va a un destino específico en un documento PDF. En nuestro caso, queremos obtener el factor de zoom del archivo PDF, por lo que usaremos el`OpenAction` propiedad de la`Document` objeto para obtener el`GoToAction` objeto.

```csharp
// Crear objeto GoToAction
GoToAction action = doc.OpenAction as GoToAction;
```

 En el código anterior, hemos creado un`GoToAction` objeto lanzando el`OpenAction` propiedad de la`Document` oponerse a`GoToAction`.

## Paso 3: obtenga el factor de zoom del archivo PDF

 El tercer paso es obtener el factor de zoom del archivo PDF. Podemos obtener el factor de zoom del archivo PDF accediendo a la`Destination` propiedad de la`GoToAction` objeto y luego lanzarlo a`XYZExplicitDestination` . El`XYZExplicitDestination` class representa un destino en un documento PDF que especifica las coordenadas y el factor de zoom al que ir.

```csharp
// Obtenga el factor de zoom del archivo PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valor de zoom del documento;
```

 En el código anterior, hemos accedido al`Destination` propiedad de la`GoToAction` objeto y luego lanzarlo a`XYZExplicitDestination` . Después de eso, hemos accedido a la`Zoom` propiedad de la`XYZExplicitDestination` objeto para obtener el factor de zoom del archivo PDF.

## Paso 4: salida del factor de zoom

 El paso final es generar el factor de zoom del archivo PDF. Podemos usar el`System.Console.WriteLine`

```csharp
// Obtenga el factor de zoom del archivo PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valor de zoom del documento;
```        

### Código fuente de ejemplo para Obtener factor de zoom usando Aspose.PDF para .NET

Aquí está el código fuente de ejemplo completo para Obtener factor de zoom usando Aspose.PDF para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciar un nuevo objeto de documento
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// Crear objeto GoToAction
GoToAction action = doc.OpenAction as GoToAction;

// Obtenga el factor de zoom del archivo PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valor de zoom del documento;
```

## Conclusión

En este tutorial, hemos explorado cómo usar Aspose.PDF para .NET para obtener el factor de zoom de un archivo PDF. El factor de zoom es un aspecto crucial de un documento PDF, ya que determina el tamaño de visualización inicial cuando se abre en un visor. Al acceder y utilizar el factor de zoom, los desarrolladores pueden personalizar la experiencia de visualización para los usuarios finales. Aspose.PDF para .NET proporciona una API simple y eficaz para recuperar el factor de zoom y otra información relacionada con la navegación de un documento PDF, lo que permite a los desarrolladores crear aplicaciones PDF interactivas y ricas en funciones.

### Preguntas frecuentes para obtener el factor de zoom en un archivo PDF

#### P: ¿Qué es el factor de zoom en un archivo PDF?

R: El factor de zoom en un archivo PDF se refiere al nivel de ampliación que se aplica al documento cuando se visualiza. Determina el tamaño de visualización inicial del archivo PDF en la pantalla. Un factor de zoom de 1,0 representa el tamaño real (100 % de zoom), mientras que un factor de zoom superior a 1,0 representa una ampliación y un factor de zoom inferior a 1,0 representa una reducción.

#### P: ¿Cómo puedo usar la información del factor de zoom en mi aplicación?

R: Puede utilizar la información del factor de zoom para personalizar el tamaño de visualización inicial de un documento PDF cuando se abre en un visor. Por ejemplo, puede establecer un factor de zoom específico para asegurarse de que el PDF se muestre en un tamaño particular o ajuste la página completa a la ventana del visor.

#### P: ¿Puedo modificar el factor de zoom de un documento PDF mediante programación usando Aspose.PDF para .NET?

 R: Sí, puede modificar el factor de zoom de un documento PDF mediante programación usando Aspose.PDF para .NET. Puede establecer el factor de zoom para acciones específicas, como`GoToAction` o`GoToRemoteAction`para controlar cómo se muestra el documento cuando el usuario interactúa con enlaces o marcadores.

#### P: ¿Hay otras formas de navegar a ubicaciones específicas en un documento PDF utilizando Aspose.PDF para .NET?

 R: Sí, Aspose.PDF para .NET proporciona varias funciones para navegar a ubicaciones específicas en un documento PDF. Además de usar`GoToAction` , puedes usar otras acciones como`GoToURIAction` para abrir una URL,`GoToEmbeddedAction` para navegar a los archivos incrustados, y`GoToNamedAction` para ir a destinos con nombre dentro del documento PDF.