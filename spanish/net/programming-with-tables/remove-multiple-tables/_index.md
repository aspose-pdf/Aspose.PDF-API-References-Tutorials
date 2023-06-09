---
title: Eliminar varias tablas
linktitle: Eliminar varias tablas
second_title: Referencia de API de Aspose.PDF para .NET
description: Aprenda a eliminar varias tablas en un documento PDF con Aspose.PDF para .NET.
type: docs
weight: 150
url: /es/net/programming-with-tables/remove-multiple-tables/
---

En este tutorial, lo guiaremos paso a paso para eliminar varias tablas en un documento PDF utilizando Aspose.PDF para .NET. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo.

## Paso 1: Cargar el documento PDF existente
Primero, debe cargar el documento PDF existente usando el siguiente código:

```csharp
// Ruta al directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento PDF existente
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");
```

## Paso 2: Crear el objeto TableAbsorber para encontrar las tablas
A continuación, crearemos un objeto TableAbsorber para encontrar las tablas en el documento PDF:

```csharp
// Cree un objeto TableAbsorber para encontrar las tablas
TableAbsorber absorber = new TableAbsorber();
```

## Paso 3: visita la segunda página con el absorbedor
Ahora visitaremos la segunda página del documento PDF usando el absorbedor:

```csharp
// Visite la segunda página con el absorbedor
absorb.Visit(pdfDocument.Pages[1]);
```

## Paso 4: Obtener una copia de la colección de tablas
Para poder eliminar las tablas, necesitamos obtener una copia de la colección de tablas:

```csharp
// Obtenga una copia de la colección de tablas
AbsorbedTable[] tables = new AbsorbedTable[absorb.TableList.Count];
absorb.TableList.CopyTo(tables, 0);
```

## Paso 5: Explore la copia de la colección y elimine las tablas
Ahora iteremos a través de la copia de la colección de tablas y eliminémoslas una por una:

```csharp
// Explore la copia de la colección y elimine las tablas.
foreach(AbsorbedTable table in tables)
     absorb.Remove(table);
```

## Paso 6: Guardar el documento
Finalmente, guardamos el documento PDF modificado:

```csharp
// Guardar el documento
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

### Ejemplo de código fuente para eliminar varias tablas con Aspose.PDF para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar documento PDF existente
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");

// Crear objeto TableAbsorber para encontrar tablas
TableAbsorber absorber = new TableAbsorber();

// Visite la segunda página con absorbedor
absorber.Visit(pdfDocument.Pages[1]);

// Obtener una copia de la colección de tablas
AbsorbedTable[] tables = new AbsorbedTable[absorber.TableList.Count];
absorber.TableList.CopyTo(tables, 0);

// Recorra la copia de la colección y la eliminación de tablas
foreach (AbsorbedTable table in tables)
	absorber.Remove(table);

// Guardar documento
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

## Conclusión
¡Felicidades! Ahora ha aprendido a eliminar varias tablas en un documento PDF utilizando Aspose.PDF para .NET. Esta guía paso a paso le mostró cómo cargar el documento, encontrar las tablas y eliminarlas. Ahora puedes aplicar este conocimiento a tus propios proyectos.