---
title: Mesa de esquina redondeada en documento PDF
linktitle: Mesa de esquina redondeada en documento PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear una tabla con esquinas redondeadas en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 190
url: /es/net/programming-with-tables/rounded-corner-table/
---
En este tutorial, lo guiaremos paso a paso para crear una tabla con esquinas redondeadas en un documento PDF con Aspose.PDF para .NET. Le explicaremos el código fuente de C# proporcionado y le mostraremos cómo implementarlo.

## Paso 1: Creación de la tabla
Primero, crearemos la tabla usando el siguiente código:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Paso 2: Configuración del estilo de esquinas redondeadas
A continuación, configuraremos el estilo de esquinas redondeadas para la mesa:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Paso 3: Configuración del borde de la tabla
Para darle a la tabla un borde con esquinas redondeadas, necesitamos crear un objeto BorderInfo y configurarlo con los parámetros apropiados:

```csharp
// Crea un objeto GraphInfo para establecer el color del borde
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Crear un objeto BorderInfo vacío
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Establezca el radio del borde redondeado en 15
bInfo.RoundedBorderRadius = 15;

// Aplicar información de borde a la tabla
tab1.Border = bInfo;
```

### Código fuente de ejemplo para una tabla con esquinas redondeadas utilizando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Crear un objeto BorderInfo en blanco
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Establezca el borde como un borde más redondeado donde el radio de la ronda sea 15
bInfo.RoundedBorderRadius = 15;
// Establezca el estilo de la esquina de la tabla como Redonda.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Establecer la información del borde de la tabla
tab1.Border = bInfo;
```

## Conclusión
¡Felicitaciones! Ya aprendió a crear una tabla con esquinas redondeadas en un documento PDF con Aspose.PDF para .NET. Esta guía paso a paso le mostró cómo configurar el estilo de esquinas redondeadas y el borde de la tabla. Ahora puede aplicar este conocimiento a sus propios proyectos.

### Preguntas frecuentes sobre mesas con esquinas redondeadas en formato PDF

#### P: ¿Puedo personalizar el radio de las esquinas redondeadas de la mesa?

R: Sí, puedes personalizar el radio de las esquinas redondeadas de la mesa modificando el valor de la`bInfo.RoundedBorderRadius` Propiedad en el código fuente C# proporcionado. Simplemente configure el valor de radio deseado (en puntos) para lograr la apariencia de esquina redondeada deseada.

#### P: ¿Puedo aplicar esquinas redondeadas a celdas individuales dentro de la tabla?

R: No, el estilo de esquinas redondeadas se aplica a toda la tabla en su conjunto. Actualmente, Aspose.PDF para .NET no ofrece compatibilidad integrada para aplicar esquinas redondeadas a celdas individuales dentro de la tabla.

#### P: ¿Puedo cambiar el color del borde de las esquinas redondeadas?

 R: Sí, puede cambiar el color del borde de la esquina redondeada modificando el valor de la`graph.Color` propiedad en el código fuente de C#. Simplemente proporcione el color deseado, como`Aspose.Pdf.Color.Red` o cualquier otra representación de color válida.

#### P: ¿Es posible aplicar diferentes estilos de esquinas (por ejemplo, cuadradas y redondeadas) a diferentes tablas dentro del mismo documento PDF?

R: Sí, es posible aplicar distintos estilos de esquinas a distintas tablas dentro del mismo documento PDF. Puedes crear varias tablas y configurar sus estilos de esquinas individualmente según tus necesidades.

#### P: ¿Puedo ajustar el grosor del borde de la esquina redondeada?

 R: Sí, puede ajustar el grosor del borde de la esquina redondeada modificando el`BorderInfo` propiedades del objeto en el código fuente de C#. Por ejemplo, puede configurar el`bInfo.Width` Propiedad para ajustar el grosor del borde.