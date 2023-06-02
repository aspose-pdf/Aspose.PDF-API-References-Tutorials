---
title: Ta bort tabell
linktitle: Ta bort tabell
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du tar bort en tabell i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 160
url: /sv/net/programming-with-tables/remove-table/
---

I den här handledningen guidar vi dig steg för steg för att ta bort en tabell i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den.

## Steg 1: Laddar det befintliga PDF-dokumentet
Först måste du ladda det befintliga PDF-dokumentet med följande kod:

```csharp
// Sökväg till dokumentkatalogen
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda det befintliga PDF-dokumentet
Document pdfDocument = new Document(dataDir + "Table_input.pdf");
```

## Steg 2: Skapa TableAbsorber-objektet för att hitta tabellerna
Därefter skapar vi ett TableAbsorber-objekt för att hitta tabellerna i PDF-dokumentet:

```csharp
// Skapa ett TableAbsorber-objekt för att hitta tabellerna
TableAbsorber absorber = new TableAbsorber();
```

## Steg 3: Besök den första sidan med absorbenten
Vi kommer nu att besöka den första sidan av PDF-dokumentet med hjälp av absorberaren:

```csharp
//Besök första sidan med absorbenten
absorb.Visit(pdfDocument.Pages[1]);
```

## Steg 4: Få den första tabellen på sidan
För att kunna ta bort tabellen får vi den första tabellen på sidan:

```csharp
// Få den första tabellen på sidan
AbsorbedTable table = absorb.TableList[0];
```

## Steg 5: Ta bort tabellen
Låt oss nu ta bort bordet med hjälp av absorbatorn:

```csharp
// ta bort bordet
absorb.Remove(table);
```

## Steg 6: Spara PDF
Slutligen sparar vi det modifierade PDF-dokumentet:

```csharp
// Spara PDF:en
pdfDocument.Save(dataDir + "Table_out.pdf");
```

### Exempel på källkod för Remove Table med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda befintligt PDF-dokument
Document pdfDocument = new Document(dataDir + "Table_input.pdf");

// Skapa TableAbsorber-objekt för att hitta tabeller
TableAbsorber absorber = new TableAbsorber();

// Besök första sidan med absorbent
absorber.Visit(pdfDocument.Pages[1]);

// Få första tabellen på sidan
AbsorbedTable table = absorber.TableList[0];

// Ta bort bordet
absorber.Remove(table);

// Spara PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

## Slutsats
Grattis! Du har nu lärt dig hur du tar bort en tabell i ett PDF-dokument med Aspose.PDF för .NET. Den här steg-för-steg-guiden visade hur du laddar dokumentet, hittar tabellen och tar bort den. Nu kan du tillämpa denna kunskap i dina egna projekt.