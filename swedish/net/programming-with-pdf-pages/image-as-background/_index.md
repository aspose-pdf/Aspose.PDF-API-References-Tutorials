---
title: Ställ in Bild Som Bakgrund
linktitle: Ställ in Bild Som Bakgrund
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att ställa in en bild som en sidbakgrund i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 110
url: /sv/net/programming-with-pdf-pages/image-as-background/
---
I den här handledningen går vi igenom steg-för-steg-processen för att ställa in en bild som sidbakgrund med Aspose.PDF för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du lägger till en bild som en sidbakgrund i ett PDF-dokument med Aspose.PDF för .NET.

## Förutsättningar
Innan du börjar, se till att du har följande:

- Grundläggande kunskaper i programmeringsspråket C#
- Aspose.PDF för .NET installerat i din utvecklingsmiljö

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det här är platsen där du vill spara ditt redigerade PDF-dokument. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa ett nytt dokument
 Sedan kan du skapa ett nytt dokumentobjekt med hjälp av`Document` klass.

```csharp
Document doc = new Document();
```

## Steg 3: Lägg till en ny sida i dokumentet
 Nu kan du lägga till en ny sida till dokumentobjektet med hjälp av`Add()` metod för`Pages` klass.

```csharp
Page page = doc.Pages.Add();
```

## Steg 4: Skapa ett bakgrundsartefaktobjekt
Sedan kan du skapa ett nytt BackgroundArtifact-objekt för att ställa in bakgrundsbilden.

```csharp
BackgroundArtifact background = new BackgroundArtifact();
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
```

## Steg 5: Lägg till bakgrunden på sidan
 Sedan kan du lägga till BackgroundArtifact-objektet till sidans artefaktsamling med hjälp av`Artifacts` egendom av`Page` klass.

```csharp
page. Artifacts. Add(background);
```

## Steg 6: Spara PDF-dokumentet
 Slutligen kan du spara PDF-dokumentet till en fil med hjälp av`Save()` metod för`Document` klass. Var noga med att ange rätt sökväg och filnamn.

```csharp
doc.Save(dataDir + "ImageAsBackground_out.pdf");
```

### Exempel på källkod för bild som bakgrund med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Skapa ett nytt dokumentobjekt
Document doc = new Document();
// Lägg till en ny sida i dokumentobjektet
Page page = doc.Pages.Add();
// Skapa bakgrundsartefaktobjekt
BackgroundArtifact background = new BackgroundArtifact();
// Ange bilden för bakgrundsartefaktobjekt
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
// Lägg till bakgrundsartefakt till artefaktsamlingen på sidan
page.Artifacts.Add(background);
dataDir = dataDir + "ImageAsBackground_out.pdf";
// Spara dokumentet
doc.Save(dataDir);
System.Console.WriteLine("\nImage as page background added successfully.\nFile saved at " + dataDir);

```

## Slutsats
den här handledningen lärde vi oss hur man ställer in en bild som en sidbakgrund i ett PDF-dokument med Aspose.PDF för .NET. Genom att följa denna steg-för-steg-guide kan du enkelt lägga till en bakgrundsbild till dina PDF-dokument. Aspose.PDF erbjuder ett kraftfullt och flexibelt API för att arbeta med PDF-filer, inklusive anpassning av sidbakgrunden. Du kan nu använda den här funktionen i dina egna projekt för att skapa PDF-dokument med anpassade bakgrundsbilder
