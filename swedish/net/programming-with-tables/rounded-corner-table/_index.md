---
title: Rundat hörnbord i PDF-dokument
linktitle: Rundat hörnbord i PDF-dokument
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du skapar en rundad hörntabell i PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 190
url: /sv/net/programming-with-tables/rounded-corner-table/
---
I denna handledning guidar vi dig steg för steg för att skapa en rundad hörntabell i PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den.

## Steg 1: Skapa tabellen
Först skapar vi tabellen med följande kod:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Steg 2: Konfiguration av rundade hörnstilar
Därefter konfigurerar vi den rundade hörnstilen för bordet:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Steg 3: Inställning av tabellkant
För att ge tabellen en rundad hörnkant måste vi skapa ett BorderInfo-objekt och konfigurera det med lämpliga parametrar:

```csharp
// Skapa ett GraphInfo-objekt för att ställa in kantfärgen
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Skapa ett tomt BorderInfo-objekt
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Ställ in radien för den rundade kanten till 15
bInfo.RoundedBorderRadius = 15;

// Tillämpa gränsinformation på tabellen
tab1.Border = bInfo;
```

### Exempel på källkod för Rounded Corner Table med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Skapa ett tomt BorderInfo-objekt
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Ställ in gränsen som en rundare gräns där rundans radie är 15
bInfo.RoundedBorderRadius = 15;
// Ställ in bordshörnstilen som rund.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Ställ in tabellkantinformationen
tab1.Border = bInfo;
```

## Slutsats
Grattis! Du har nu lärt dig hur du skapar en rundad hörntabell i ett PDF-dokument med Aspose.PDF för .NET. Den här steg-för-steg-guiden visade dig hur du ställer in stilen med rundade hörn och bordskanten. Nu kan du tillämpa denna kunskap i dina egna projekt.

### Vanliga frågor för rundat hörnbord i PDF-dokument

#### F: Kan jag anpassa radien för de rundade hörnen för bordet?

S: Ja, du kan anpassa radien för de rundade hörnen för tabellen genom att ändra värdet på`bInfo.RoundedBorderRadius` egenskapen i den angivna C#-källkoden. Ställ bara in önskat radievärde (i poäng) för att uppnå önskat utseende av rundade hörn.

#### F: Kan jag använda rundade hörn på enskilda celler i tabellen?

S: Nej, stilen med rundade hörn tillämpas på hela bordet som helhet. Aspose.PDF för .NET ger för närvarande inte inbyggt stöd för att applicera rundade hörn på enskilda celler i tabellen.

#### F: Kan jag ändra färgen på den rundade hörnkanten?

 S: Ja, du kan ändra färgen på den rundade hörnkanten genom att ändra värdet på`graph.Color` egenskapen i C#-källkoden. Ange helt enkelt önskad färg, som t.ex`Aspose.Pdf.Color.Red` eller någon annan giltig färgrepresentation.

#### F: Är det möjligt att använda olika hörnstilar (t.ex. kvadratiska och rundade) på olika tabeller inom samma PDF-dokument?

S: Ja, det är möjligt att använda olika hörnstilar på olika tabeller inom samma PDF-dokument. Du kan skapa flera bord och konfigurera deras hörnstilar individuellt baserat på dina krav.

#### F: Kan jag justera tjockleken på den rundade hörnkanten?

 S: Ja, du kan justera tjockleken på den rundade hörnkanten genom att ändra`BorderInfo` objektets egenskaper i C#-källkoden. Du kan till exempel ställa in`bInfo.Width` egenskap för att justera bårdens tjocklek.