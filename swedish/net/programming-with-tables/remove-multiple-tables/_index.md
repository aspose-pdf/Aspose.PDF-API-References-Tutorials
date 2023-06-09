---
title: Ta bort flera tabeller
linktitle: Ta bort flera tabeller
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du tar bort flera tabeller i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 150
url: /sv/net/programming-with-tables/remove-multiple-tables/
---

I den här handledningen guidar vi dig steg för steg för att ta bort flera tabeller i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den.

## Steg 1: Laddar det befintliga PDF-dokumentet
Först måste du ladda det befintliga PDF-dokumentet med följande kod:

```csharp
// Sökväg till dokumentkatalogen
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda det befintliga PDF-dokumentet
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");
```

## Steg 2: Skapa TableAbsorber-objektet för att hitta tabellerna
Därefter skapar vi ett TableAbsorber-objekt för att hitta tabellerna i PDF-dokumentet:

```csharp
// Skapa ett TableAbsorber-objekt för att hitta tabellerna
TableAbsorber absorber = new TableAbsorber();
```

## Steg 3: Besök den andra sidan med absorbenten
Vi kommer nu att besöka den andra sidan av PDF-dokumentet med hjälp av absorberaren:

```csharp
// Besök den andra sidan med absorbenten
absorb.Visit(pdfDocument.Pages[1]);
```

## Steg 4: Skaffa en kopia av bordssamlingen
För att kunna släppa tabellerna behöver vi få en kopia av tabellsamlingen:

```csharp
// Få en kopia av bordssamlingen
AbsorbedTable[] tables = new AbsorbedTable[absorb.TableList.Count];
absorb.TableList.CopyTo(tables, 0);
```

## Steg 5: Bläddra i kopian av samlingen och ta bort tabellerna
Låt oss nu iterera igenom kopian av tabellsamlingen och ta bort dem en efter en:

```csharp
// Bläddra i kopian av samlingen och ta bort tabellerna
foreach(AbsorbedTable table in tables)
     absorb.Remove(table);
```

## Steg 6: Spara dokumentet
Slutligen sparar vi det modifierade PDF-dokumentet:

```csharp
// Spara dokumentet
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

### Exempel på källkod för Ta bort flera tabeller med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda befintligt PDF-dokument
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");

// Skapa TableAbsorber-objekt för att hitta tabeller
TableAbsorber absorber = new TableAbsorber();

// Besök andra sidan med absorbent
absorber.Visit(pdfDocument.Pages[1]);

// Få kopia av bordssamlingen
AbsorbedTable[] tables = new AbsorbedTable[absorber.TableList.Count];
absorber.TableList.CopyTo(tables, 0);

// Gå igenom kopian av insamling och borttagning av tabeller
foreach (AbsorbedTable table in tables)
	absorber.Remove(table);

// Spara dokument
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

## Slutsats
Grattis! Du har nu lärt dig hur du tar bort flera tabeller i ett PDF-dokument med Aspose.PDF för .NET. Den här steg-för-steg-guiden visade hur du laddar upp dokumentet, hittar tabellerna och tar bort dem. Nu kan du tillämpa denna kunskap i dina egna projekt.