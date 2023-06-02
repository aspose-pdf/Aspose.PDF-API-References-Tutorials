---
title: Eliminar tabla
linktitle: Eliminar tabla
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a eliminar una tabla en un documento PDF usando Aspose.PDF para .NET.
type: docs
weight: 160
url: /es/net/programming-with-tables/remove-table/
---

En este tutorial, lo guiaremos paso a paso para eliminar una tabla en un documento PDF utilizando Aspose.PDF para .NET. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo.

## Paso 1: Cargar el documento PDF existente
Primero, debe cargar el documento PDF existente usando el siguiente código:

```csharp
// Ruta al directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento PDF existente
Document pdfDocument = new Document(dataDir + "Table_input.pdf");
```

## Paso 2: Crear el objeto TableAbsorber para encontrar las tablas
A continuación, crearemos un objeto TableAbsorber para encontrar las tablas en el documento PDF:

```csharp
// Cree un objeto TableAbsorber para encontrar las tablas
TableAbsorber absorber = new TableAbsorber();
```

## Paso 3: Visite la primera página con el absorbedor
Ahora visitaremos la primera página del documento PDF usando el absorbedor:

```csharp
//Visite la primera página con el absorbedor
absorb.Visit(pdfDocument.Pages[1]);
```

## Paso 4: Obtener la primera tabla en la página
Para poder quitar la tabla, obtendremos la primera tabla de la página:

```csharp
// Obtenga la primera tabla en la página
AbsorbedTable table = absorb.TableList[0];
```

## Paso 5: Eliminar la tabla
Ahora eliminemos la tabla usando el absorbedor:

```csharp
// quita la mesa
absorb.Remove(table);
```

## Paso 6: Guardar PDF
Finalmente, guardamos el documento PDF modificado:

```csharp
// Guardar el PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

### Ejemplo de código fuente para Quitar tabla usando Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar documento PDF existente
Document pdfDocument = new Document(dataDir + "Table_input.pdf");

// Crear objeto TableAbsorber para encontrar tablas
TableAbsorber absorber = new TableAbsorber();

// Visita la primera página con absorbedor
absorber.Visit(pdfDocument.Pages[1]);

// Obtener la primera mesa en la página
AbsorbedTable table = absorber.TableList[0];

// quitar la mesa
absorber.Remove(table);

// Guardar PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

## Conclusión
¡Felicidades! Ahora ha aprendido cómo eliminar una tabla en un documento PDF usando Aspose.PDF para .NET. Esta guía paso a paso le mostró cómo cargar el documento, encontrar la tabla y quitarla. Ahora puedes aplicar este conocimiento a tus propios proyectos.