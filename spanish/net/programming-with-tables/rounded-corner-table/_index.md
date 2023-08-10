---
title: Mesa de esquinas redondeadas en documento PDF
linktitle: Mesa de esquinas redondeadas en documento PDF
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a crear una tabla de esquinas redondeadas en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 190
url: /es/net/programming-with-tables/rounded-corner-table/
---
En este tutorial, lo guiaremos paso a paso para crear una tabla de esquinas redondeadas en un documento PDF usando Aspose.PDF para .NET. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo.

## Paso 1: Crear la tabla
Primero, crearemos la tabla usando el siguiente código:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Paso 2: Configuración de estilo de esquina redondeada
A continuación, configuraremos el estilo de esquinas redondeadas para la tabla:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Paso 3: Configuración del borde de la tabla
Para darle a la tabla un borde de esquina redondeada, necesitamos crear un objeto BorderInfo y configurarlo con los parámetros apropiados:

```csharp
// Cree un objeto GraphInfo para establecer el color del borde
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Crear un objeto BorderInfo vacío
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Establezca el radio del borde redondeado en 15
bInfo.RoundedBorderRadius = 15;

// Aplicar información de borde a la tabla
tab1.Border = bInfo;
```

### Ejemplo de código fuente para la tabla de esquinas redondeadas usando Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Crear un objeto BorderInfo en blanco
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Establezca el borde en un borde más redondo donde el radio de la ronda sea 15
bInfo.RoundedBorderRadius = 15;
// Establezca el estilo de la esquina de la mesa como Redondo.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Establecer la información del borde de la tabla
tab1.Border = bInfo;
```

## Conclusión
¡Felicidades! Ahora ha aprendido a crear una tabla de esquinas redondeadas en un documento PDF utilizando Aspose.PDF para .NET. Esta guía paso a paso le mostró cómo configurar el estilo de esquina redondeada y el borde de la mesa. Ahora puedes aplicar este conocimiento a tus propios proyectos.

### Preguntas frecuentes sobre mesa de esquinas redondeadas en documento PDF

#### P: ¿Puedo personalizar el radio de las esquinas redondeadas de la mesa?

R: Sí, puede personalizar el radio de las esquinas redondeadas de la mesa modificando el valor de la`bInfo.RoundedBorderRadius` propiedad en el código fuente de C# proporcionado. Simplemente establezca el valor del radio deseado (en puntos) para lograr la apariencia de esquina redondeada deseada.

#### P: ¿Puedo aplicar esquinas redondeadas a celdas individuales dentro de la tabla?

R: No, el estilo de esquinas redondeadas se aplica a toda la mesa como un todo. Aspose.PDF para .NET actualmente no proporciona soporte integrado para aplicar esquinas redondeadas a celdas individuales dentro de la tabla.

#### P: ¿Puedo cambiar el color del borde de la esquina redondeada?

 R: Sí, puede cambiar el color del borde de la esquina redondeada modificando el valor de la`graph.Color` propiedad en el código fuente de C#. Simplemente proporcione el color deseado, como`Aspose.Pdf.Color.Red` o cualquier otra representación de color válida.

#### P: ¿Es posible aplicar diferentes estilos de esquinas (por ejemplo, cuadradas y redondeadas) a diferentes tablas dentro del mismo documento PDF?

R: Sí, es posible aplicar diferentes estilos de esquina a diferentes tablas dentro del mismo documento PDF. Puede crear varias tablas y configurar sus estilos de esquina individualmente según sus requisitos.

#### P: ¿Puedo ajustar el grosor del borde de la esquina redondeada?

 R: Sí, puede ajustar el grosor del borde de la esquina redondeada modificando el`BorderInfo` propiedades del objeto en el código fuente de C#. Por ejemplo, puede configurar el`bInfo.Width` propiedad para ajustar el grosor del borde.