---
title: Ställ in bildtextegenskap
linktitle: Ställ in bildtextegenskap
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ställer in bildtextegenskap med Aspose.PDF för .NET. Anpassa kommentarer med textlinjer, textfärg och avslutningsstilar.
type: docs
weight: 130
url: /sv/net/annotations/setcalloutproperty/
---
 Aspose.PDF för .NET är ett kraftfullt bibliotek för att skapa, manipulera och konvertera PDF-dokument i C#. En av funktionerna i det här biblioteket är möjligheten att ställa in bildtextegenskaper för fritextkommentarer i PDF-dokument. Detta kan göras med hjälp av`FreeTextAnnotation` klass, som låter dig skapa kommentarer med länktexter.

I den här handledningen kommer vi att guida dig genom processen att ställa in bildtextegenskaper för en fritextkommentar med Aspose.PDF för .NET i C#. Följ stegen nedan för att komma igång.

## Installera Aspose.PDF för .NET

 Om du inte redan har gjort det måste du göra det[ladda ner](https://releases.aspose.com/pdf/net/) och installera Aspose.PDF för .NET från Aspose-versionerna eller via NuGet-pakethanteraren.

## Skapa ett nytt PDF-dokument

 Skapa ett nytt PDF-dokument med hjälp av`Document` klass tillhandahållen av Aspose.PDF för .NET.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Lägg till en ny sida i dokumentet

 Lägg till en ny sida i dokumentet med hjälp av`Pages` samling av`Document` klass.

```csharp
Page page = doc.Pages.Add();
```

## Ställ in standardutseende

 Ställ in standardutseendet för fritextkommentaren genom att skapa en ny`DefaultAppearance` objekt och ställa in dess egenskaper som t.ex`TextColor` och`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Skapa en fritextkommentar med bildtext

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

## Lägg till fritextkommentaren på sidan

 Lägg till fritextkommentaren på sidan genom att använda`Annotations` samling av`Page` klass.

```csharp
page.Annotations.Add(fta);
```

## Lägg till text i anteckningen

 Lägg till text i kommentaren genom att ställa in`RichText`egenskap till en sträng av formaterad XML. I den här handledningen ställer vi in textfärgen till röd och teckenstorleken till 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"färg:#FF
```

## 8. spara dokumentet

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
