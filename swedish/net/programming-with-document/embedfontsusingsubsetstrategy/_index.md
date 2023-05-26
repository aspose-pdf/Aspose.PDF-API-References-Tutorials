---
title: Bädda in teckensnitt med hjälp av delmängdsstrategi
linktitle: Bädda in teckensnitt med hjälp av delmängdsstrategi
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du bäddar in teckensnitt i en PDF-fil med Subset Strategy med Aspose.PDF för .NET. Optimera din PDF-storlek genom att bädda in endast nödvändiga tecken.
type: docs
weight: 130
url: /sv/net/programming-with-document/embedfontsusingsubsetstrategy/
---

den här handledningen kommer vi att diskutera hur man bäddar in teckensnitt i en PDF-fil med en delmängdsstrategi med Aspose.PDF för .NET. Aspose.PDF för .NET är ett kraftfullt bibliotek som låter utvecklare skapa, redigera och manipulera PDF-dokument programmatiskt. Att bädda in typsnitt i en PDF-fil är ett viktigt steg för att säkerställa att dokumentet visas korrekt på olika enheter, oavsett om de nödvändiga typsnitten är installerade på dessa enheter eller inte.

## Steg 1: Skapa en ny C# Console Application
För att komma igång, skapa en ny C# Console Application i Visual Studio. Du kan namnge det vad du vill. När projektet har skapats måste du lägga till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera Aspose.PDF-namnområdet
Lägg till följande kodrad överst i din C#-fil för att importera Aspose.PDF-namnrymden:

```csharp
using Aspose.Pdf;
```

## Steg 3: Ladda en befintlig PDF-fil
För att bädda in teckensnitt i en befintlig PDF-fil måste du ladda den filen med klassen Document. Följande kod visar hur man laddar en befintlig PDF-fil:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda en befintlig PDF-fil
Document doc = new Document(dataDir + "input.pdf");
```

## Steg 4: Bädda in teckensnitt med delmängdsstrategi
Aspose.PDF för .NET tillhandahåller två strategier för inbäddning av teckensnitt: SubsetAllFonts och SubsetEmbeddedFontsOnly.

Strategin SubsetAllFonts kommer att bädda in alla teckensnitt i dokumentet som en delmängd. En delmängd är en del av teckensnittet som endast innehåller de tecken som används i dokumentet. Denna strategi är användbar för att minska filstorleken på PDF-dokumentet.

Strategin SubsetEmbeddedFontsOnly kommer endast att bädda in den delmängd av teckensnitt som redan är inbäddade i dokumentet. Om ett teckensnitt inte är inbäddat kommer det inte att påverkas av denna strategi.

Följande kod visar hur man bäddar in teckensnitt i en PDF-fil med en delmängdsstrategi:

```csharp
// Alla teckensnitt kommer att bäddas in som delmängder i dokumentet i händelse av SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// Teckensnittsunderuppsättning kommer att bäddas in för helt inbäddade teckensnitt, men teckensnitt som inte är inbäddade i dokumentet kommer inte att påverkas.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## Steg 5: Spara PDF-dokumentet
När du har bäddat in alla teckensnitt i PDF-filen med en delmängdsstrategi måste du spara dokumentet. Följande kod visar hur du sparar PDF-filen:

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### Exempel på källkod för inbäddning av typsnitt med delmängdsstrategi med Aspose.PDF för .NET. 

```csharp

            
            // Sökvägen till dokumentkatalogen.
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "input.pdf");
            // Alla teckensnitt kommer att bäddas in som delmängder i dokumentet i händelse av SubsetAllFonts.
            doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
            // Teckensnittsunderuppsättning kommer att bäddas in för helt inbäddade teckensnitt, men teckensnitt som inte är inbäddade i dokumentet kommer inte att påverkas.
            doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
            doc.Save(dataDir + "Output_out.pdf");
            

        
```

## Slutsats
den här artikeln har vi diskuterat hur man bäddar in typsnitt i en PDF-fil med en delmängdsstrategi med Aspose.PDF för .NET. Aspose.PDF för .NET tillhandahåller ett enkelt och lättanvänt API för att arbeta med PDF-dokument, inklusive att lägga till och bädda in typsnitt med olika strategier. Att bädda in teckensnitt i en PDF-fil är ett viktigt steg för att säkerställa att dokumentet visas korrekt på olika enheter, och delmängdsstrategin är en användbar funktion för att minska filstorleken på PDF-dokumentet.

