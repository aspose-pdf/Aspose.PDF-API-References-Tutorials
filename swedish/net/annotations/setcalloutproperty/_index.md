---
title: Ställ in bildtextegenskap i PDF-fil
linktitle: Ställ in bildtextegenskap i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ställer in bildtextegenskap i PDF-fil med Aspose.PDF för .NET. Anpassa kommentarer med textlinjer, textfärg och avslutningsstilar.
type: docs
weight: 130
url: /sv/net/annotations/setcalloutproperty/
---
 Aspose.PDF för .NET är ett kraftfullt bibliotek för att skapa, manipulera och konvertera PDF-dokument i C#. En av funktionerna i det här biblioteket är möjligheten att ställa in bildtextegenskaper för fritextkommentarer i PDF-dokument. Detta kan göras med hjälp av`FreeTextAnnotation` klass, som låter dig skapa kommentarer med länktexter.

I den här handledningen kommer vi att guida dig genom processen att ställa in bildtextegenskaper för en fritextkommentar med Aspose.PDF för .NET i C#. Följ stegen nedan för att komma igång.

## Installera Aspose.PDF för .NET

 Om du inte redan har gjort det måste du göra det[ladda ner](https://releases.aspose.com/pdf/net/) och installera Aspose.PDF för .NET från Aspose-versionerna eller via NuGet-pakethanteraren.

## Steg 1: Skapa ett nytt PDF-dokument

 Skapa ett nytt PDF-dokument med hjälp av`Document`klass tillhandahållen av Aspose.PDF för .NET.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Steg 2: Lägg till en ny sida i dokumentet

 Lägg till en ny sida i dokumentet med hjälp av`Pages` samling av`Document` klass.

```csharp
Page page = doc.Pages.Add();
```

## Steg 3: Ställ in standardutseende

 Ställ in standardutseendet för fritextkommentaren genom att skapa en ny`DefaultAppearance` objekt och ställa in dess egenskaper som t.ex`TextColor` och`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Steg 4: Skapa en fritextkommentar med bildtext

 Skapa en ny fritextkommentar med bildtext genom att använda`FreeTextAnnotation` klass. Ställ in`Intent` egendom till`FreeTextIntent.FreeTextCallout` för att ange att detta är en förklaringskommentar. Ställ in`EndingStyle` egendom till`LineEnding.OpenArrow` för att ange stilen för pilen i slutet av bildtexten. Ställ in`Callout` egendom till en mängd`Point` objekt som representerar punkterna på sidan där bildtextlinjen ska dras.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Steg 5: Lägg till fritextkommentaren på sidan

 Lägg till fritextkommentaren på sidan genom att använda`Annotations` samling av`Page` klass.

```csharp
page.Annotations.Add(fta);
```

## Steg 6: Lägg till text i kommentaren

 Lägg till text i kommentaren genom att ställa in`RichText`egenskap till en sträng av formaterad XML. I den här handledningen ställer vi in textfärgen till röd och teckenstorleken till 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"färg:#FF
```

## Steg 7: spara dokumentet

Spara nu dokumentet genom att använda följande kod:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Exempel på källkod för Set Callout Property med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"färg:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Detta är ett exempel</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## Slutsats

den här handledningen undersökte vi hur man ställer in bildtextegenskaper för en fritextkommentar i ett PDF-dokument med Aspose.PDF för .NET. Förklaringskommentarer är användbara för att tillhandahålla ytterligare information eller förklaringar relaterade till specifika områden i ett dokument. Aspose.PDF för .NET tillhandahåller ett brett utbud av funktioner och möjligheter för att arbeta med PDF-filer, inklusive att skapa och anpassa anteckningar, till exempel bildtexter. Genom att följa den steg-för-steg-guiden och använda den medföljande C#-källkoden, kan utvecklare enkelt implementera anteckningar för förklaringar i sina PDF-dokument, vilket förbättrar användarvänligheten och tydligheten i sina dokument. Aspose.PDF för .NET är ett mångsidigt och pålitligt bibliotek för PDF-operationer i .NET-applikationer, som erbjuder kraftfulla verktyg för att effektivt hantera olika PDF-relaterade uppgifter.

### Vanliga frågor om ange bildtextegenskap i PDF-fil

#### F: Vad är en informationskommentar i ett PDF-dokument?

S: En förklaringsanteckning i ett PDF-dokument är en typ av anteckning som låter dig skapa en textruta med en ledarlinje som pekar på ett specifikt område i dokumentet. Det används vanligtvis för att tillhandahålla ytterligare information eller kommentarer relaterade till ett visst avsnitt eller element i dokumentet.

#### F: Kan jag anpassa utseendet på bildtextanteckningen med Aspose.PDF för .NET?

S: Ja, du kan anpassa olika egenskaper för bildtextkommentaren, som färg, teckenstorlek, textjustering, linjestil, pilstil med mera.

#### F: Hur lägger jag till text i informationstextanteckningen?

 S: För att lägga till text till bildtextanteckningen kan du ställa in`RichText` egendom av`FreeTextAnnotation` objekt. De`RichText` egenskapen tar en sträng av formaterad XML som representerar texten som ska visas i bildtextanteckningen.

#### F: Kan jag lägga till flera bildtextkommentarer till ett PDF-dokument med Aspose.PDF för .NET?

 S: Ja, du kan skapa flera bildtextkommentarer i ett PDF-dokument genom att skapa flera instanser av`FreeTextAnnotation`objekt och lägga till dem på olika sidor eller platser i dokumentet.