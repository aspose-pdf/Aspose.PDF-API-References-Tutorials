---
title: Hämta formulärfält i tabbordning
linktitle: Hämta formulärfält i tabbordning
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du hämtar formulärfält i tabbordning med Aspose.PDF för .NET.
type: docs
weight: 240
url: /sv/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
När du arbetar med PDF-dokument i C# med Aspose.PDF för .NET kan du stöta på ett scenario där du behöver hämta formulärfält i en specifik tabbordning. Detta kan vara användbart när du vill utföra operationer på formulärfält baserat på deras fliksekvens. I den här handledningen guidar vi dig steg för steg om hur du hämtar formulärfält i tabbordning med Aspose.PDF för .NET.

## Krav

Innan vi börjar, se till att du har följande förutsättningar:

- Visual Studio installerat på ditt system
- Aspose.PDF för .NET-biblioteket installerat

Låt oss nu dyka in i stegen för att hämta formulärfält i tabbordning.

## Steg 1: Ställa in dokumentkatalogen

 Till att börja med måste du ställa in dokumentkatalogen där ditt PDF-dokument finns. Du kan göra detta genom att ange sökvägen till katalogen i`dataDir` variabel.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 2: Ladda PDF-dokumentet

 I det här steget kommer vi att ladda PDF-dokumentet med Aspose.PDF för .NET. De`Document` klass ger möjligheten att ladda och manipulera PDF-dokument.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Här,`"Test2.pdf"`är namnet på PDF-dokumentet du vill ladda. Se till att dokumentet finns i den angivna dokumentkatalogen.

## Steg 3: Hämta formulärfält i tabbordning

 För att hämta formulärfält i tabbordning måste vi komma åt`FieldsInTabOrder` egendom av`Page` klass. Den här egenskapen returnerar en lista med formulärfält sorterade efter deras fliksekvens.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

I kodavsnittet ovan hämtar vi formulärfälten från den andra sidan (`doc.Pages[1]` ) och iterera genom varje fält för att sammanfoga deras delnamn till`s` variabel. Du kan ändra detta kodavsnitt baserat på dina specifika krav.

## Steg 4: Ändra flikordningen

 Om du vill ändra flikordningen för formulärfält kan du göra det genom att gå till`TabOrder` egenskapen för varje fält och tilldela ett nytt tabulatorvärde. Här är ett exempel:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

I kodavsnittet ovan tilldelar vi nya tabbordningsvärden till tre formulärfält (`doc.Form[3]`, `doc.Form[1]` , och`doc.Form[2]`). Justera fältindex och tabbordningsvärden enligt dina specifika krav.

## Steg 5: Spara det ändrade dokumentet

 Efter att ha ändrat tabbordningen för formulärfält måste du spara det ändrade dokumentet. Du kan göra detta med hjälp av`Save` metod för`Document` klass.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Här,`"39522_out.pdf"` är namnet på utdatafilen där det ändrade dokumentet kommer att sparas. Ange önskat namn och plats för utdatafilen.

### Exempel på källkod för Hämta formulärfält i flikordning med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## Slutsats

I den här handledningen lärde vi oss hur man hämtar formulärfält i tabbordning med Aspose.PDF för .NET. Vi täckte stegen som är involverade i att ladda ett PDF-dokument, hämta formulärfält i tabbordning, ändra tabbordningen och spara det ändrade dokumentet. Genom att följa dessa steg kan du effektivt arbeta med formulärfält och anpassa deras fliksekvens enligt dina krav.


### FAQ's

#### F: Hur kan jag använda de hämtade formulärfälten i min C#-kod för vidare bearbetning?

 S: Du kan använda de hämtade formulärfälten i din C#-kod genom att komma åt deras egenskaper som t.ex`Value`, `Name`, `Rect`etc. Dessa egenskaper låter dig läsa och ändra formulärfältsdata efter behov.

#### F: Kan jag hämta formulärfält från alla sidor i PDF-dokumentet i tabbordning?

 S: Ja, du kan hämta formulärfält från alla sidor i PDF-dokumentet genom att iterera genom varje sida och komma åt`FieldsInTabOrder` egenskap som visas i handledningen. Detta ger dig formulärfält sorterade efter deras fliksekvens på alla sidor.

#### F: Är det möjligt att bara hämta specifika typer av formulärfält, såsom textfält eller kryssrutor, i tabbordning?

S: Ja, du kan filtrera formulärfält baserat på deras typer, såsom textfält eller kryssrutor, efter att ha hämtat dem i tabbordning. Du kan använda villkorliga uttalanden för att kontrollera typen av varje formulärfält och bearbeta dem därefter.

#### F: Kan jag hämta formulärfält baserat på deras namn istället för tabbordning?

 S: Ja, du kan hämta formulärfält baserat på deras namn genom att använda`doc.Form` samling och ange fältnamnet som ett index. Till exempel,`doc.Form["fieldName"]`kommer att hämta formulärfältet med det angivna namnet.

#### F: Stöder Aspose.PDF för .NET arbete med krypterade PDF-dokument?

S: Ja, Aspose.PDF för .NET ger stöd för att arbeta med krypterade PDF-dokument. Du kan ladda och manipulera krypterade PDF-filer med lämpliga lösenordsparametrar.