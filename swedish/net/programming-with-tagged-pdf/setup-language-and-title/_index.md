---
title: Ställ in språk och titel
linktitle: Ställ in språk och titel
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att konfigurera språket och titeln på ett PDF-dokument med Aspose.PDF för .NET. Skapa personliga flerspråkiga dokument.
type: docs
weight: 140
url: /sv/net/programming-with-tagged-pdf/setup-language-and-title/
---
I den här guiden kommer vi att berätta hur du konfigurerar språket och titeln på ett PDF-dokument med hjälp av Aspose.PDF-biblioteket för .NET. Aspose.PDF är ett kraftfullt bibliotek som låter dig skapa, manipulera och konvertera PDF-filer programmatiskt.

Låt oss dyka in i koden och lära oss hur man konfigurerar språket och titeln på ett PDF-dokument med Aspose.PDF för .NET.

## Förutsättningar

Innan du börjar, se till att du har installerat Aspose.PDF för .NET och ställt in din utvecklingsmiljö.

## Steg 1: Skapa dokumentet

 Det första steget är att skapa ett nytt PDF-dokument med hjälp av`Document` klass.

```csharp
// Skapa PDF-dokumentet
Document document = new Document();
```

## Steg 2: Få åtkomst till taggat innehåll

 Därefter kommer vi åt det taggade innehållet i dokumentet med hjälp av`ITaggedContent` objekt.

```csharp
//Få tillgång till taggat innehåll
Tagged.ITaggedContent taggedContent = document.TaggedContent;
```

## Steg 3: Ställ in titel och språk

 Nu kan vi ställa in dokumentets titel och språk med hjälp av`SetTitle` och`SetLanguage` metoder för`ITaggedContent` objekt.

```csharp
// Definiera titeln på dokumentet
taggedContent.SetTitle("Example of tagged document");

// Ställ in dokumentets språk
taggedContent.SetLanguage("fr-FR");
```

## Steg 4: Lägg till flerspråkigt innehåll

Därefter lägger vi till flerspråkigt innehåll i dokumentet med hjälp av styckeelement för varje språk.

```csharp
// Lägg till ett stycke på engelska
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Lägg till ett stycke på tyska
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hello Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Lägg till ett stycke på franska
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Hello world!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Lägg till ett stycke på spanska
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);
```

## Steg 5: Spara det taggade PDF-dokumentet

Slutligen sparar vi det taggade PDF-dokumentet.

```csharp
// Spara det taggade PDF-dokumentet
document.Save(dataDir + "SetupLanguageAndTitle.pdf");
```

### Exempel på källkod för Setup Language And Title med Aspose.PDF för .NET 
```csharp

Document document = new Document();

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Skaffa TaggedContent
Tagged.ITaggedContent taggedContent = document.TaggedContent;

// Ställ in titel och språk
taggedContent.SetTitle("Example Tagged Document");
taggedContent.SetLanguage("en-US");

// Header (sv-US, ärvt från dokument)
LogicalStructure.HeaderElement h1 = taggedContent.CreateHeaderElement(1);
h1.SetText("Phrase on different languages");
taggedContent.RootElement.AppendChild(h1);

// Paragraf (engelska)
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Paragraf (tyska)
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hallo Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Paragraf (franska)
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Bonjour le monde!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Paragraf (spanska)
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);

// Spara taggat pdf-dokument
document.Save(dataDir + "SetupLanguageAndTitle.pdf");

```

## Slutsats

Grattis! Du vet nu hur du konfigurerar språket och titeln på ett PDF-dokument med Aspose.PDF för .NET. Du kan utforska funktionerna i Aspose.PDF ytterligare för att skapa personliga och flerspråkiga PDF-dokument.
