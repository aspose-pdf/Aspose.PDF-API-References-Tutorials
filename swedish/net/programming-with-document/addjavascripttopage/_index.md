---
title: Lägg till Java-skript på sidan
linktitle: Lägg till Java-skript på sidan
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till JavaScript i PDF-filer med Aspose.PDF för .NET. Steg-för-steg-guide med kodhandledning för dokument- och sidnivåskript.
type: docs
weight: 10
url: /sv/net/programming-with-document/addjavascripttopage/
---

För att lägga till JavaScript i en PDF-fil kommer vi att använda Aspose.PDF för .NET. Detta bibliotek ger ett enkelt och effektivt sätt att arbeta med PDF-filer i .NET-program. Följande steg guidar dig genom processen att lägga till JavaScript i en PDF-fil med Aspose.PDF för .NET.

## Steg 1: Ladda PDF-filen

 Det första steget är att ladda PDF-filen som du vill lägga till JavaScript i. Du kan göra detta med hjälp av`Document` klass tillhandahållen av Aspose.PDF för .NET. De`Document` klass tillhandahåller metoder för att ladda, spara och manipulera PDF-filer.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda en befintlig PDF-fil
Document doc = new Document(dataDir + "input.pdf");
```

## Steg 2: Lägg till JavaScript på dokumentnivå

 För att lägga till JavaScript på dokumentnivå kommer vi att använda`JavascriptAction` klass tillhandahållen av Aspose.PDF för .NET. Den här klassen låter dig ange JavaScript-satsen som du vill lägga till i PDF-filen.

```csharp
// Lägga till JavaScript på dokumentnivå
// Instantiera JavascriptAction med önskad JavaScript-sats
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Tilldela JavascriptAction-objekt till önskad handling i dokumentet
doc.OpenAction = javaScript;
```

I den här handledningen lägger vi till en JavaScript-sats som kommer att skriva ut PDF-filen med de angivna alternativen när dokumentet öppnas.

## Steg 3: Lägg till JavaScript på sidnivå

 För att lägga till JavaScript på sidnivå kommer vi att använda`JavascriptAction` klass och`Actions`egendom tillhandahållen av Aspose.PDF för .NET. Den här egenskapen låter dig ange JavaScript-satser som kommer att köras när sidan öppnas eller stängs.

```csharp
// Lägger till JavaScript på sidnivå
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

I den här handledningen lägger vi till JavaScript-satser som visar ett varningsmeddelande när sidan öppnas eller stängs.

## Steg 4: Spara PDF-filen

 När du har lagt till JavaScript i PDF-filen måste du spara den ändrade filen. Du kan göra detta med hjälp av`Save` metod som tillhandahålls av`Document` klass.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// Spara PDF-dokument
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Denna kod kommer att spara den modifierade PDF-filen i den angivna katalogen.

### Exempel på källkod för Add Java Script To Page med Aspose.PDF för .NET

```csharp
            
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda en befintlig PDF-fil
Document doc = new Document(dataDir + "input.pdf");

// Lägga till JavaScript på dokumentnivå
// Instantiera JavascriptAction med önskat JavaScript-uttalande
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Tilldela JavascriptAction-objekt till önskad handling i dokumentet
doc.OpenAction = javaScript;

// Lägger till JavaScript på sidnivå
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// Spara PDF-dokument
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## Slutsats

den här artikeln har vi förklarat hur man lägger till JavaScript i en PDF-fil på både dokumentnivå och sidnivå med Aspose.PDF för .NET. Vi har tillhandahållit steg-för-steg-instruktioner och inkluderat hela källkoden för varje exempel. Med denna kunskap kan du lägga till JavaScript i dina PDF-filer och anpassa deras beteende efter dina behov.


