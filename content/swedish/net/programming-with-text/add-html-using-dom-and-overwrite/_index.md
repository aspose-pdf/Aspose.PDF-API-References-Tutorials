---
title: Lägg till HTML med DOM och PDF-överskrivning
linktitle: Lägg till HTML med DOM och skriv över
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till HTML-innehåll med DOM och PDF-överskrivning i Aspose.PDF för .NET.
type: docs
weight: 50
url: /sv/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Denna handledning guidar dig genom processen att lägga till HTML-innehåll med DOM (Document Object Model) i Aspose.PDF för .NET. Dessutom kommer du att lära dig hur du skriver över stilar för HTML-innehållet. Den medföljande C#-källkoden visar de nödvändiga stegen.

## Krav
Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan C#-kompilator installerad på din maskin.
- Aspose.PDF för .NET-bibliotek. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda en pakethanterare som NuGet för att installera den.

## Steg 1: Konfigurera projektet
1. Skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö.
2. Lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnrymder
I kodfilen där du vill lägga till HTML-innehållet, lägg till följande med hjälp av direktiv överst i filen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Steg 3: Ställ in dokumentkatalogen och utdatafilens sökväg
 I koden, lokalisera raden som säger`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där dina dokument är lagrade.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 4: Skapa ett nytt dokumentobjekt
 Instantiera en ny`Document` objekt genom att lägga till följande kodrad:

```csharp
Document doc = new Document();
```

## Steg 5: Lägg till en sida i dokumentet
 Lägg till en ny sida i dokumentet med hjälp av`Add` metod för`Pages`samling. I den angivna koden är den nya sidan tilldelad variabeln`page`.

```csharp
Page page = doc.Pages.Add();
```

## Steg 6: Skapa ett HtmlFragment med HTML-innehållet
 Instantiera en`HtmlFragment` objekt och tillhandahålla önskat HTML-innehåll. I den medföljande koden är HTML-innehållet tilldelat variabeln`title`. Du kan ändra HTML-innehållet efter behov.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Steg 7: Skriv över stilarna för HTML-innehållet
 För att skriva över HTML-innehållets stilar kan du ändra`TextState` egenskaper hos`HtmlFragment` objekt. I den medföljande koden ändras teckensnittsfamiljen till "Arial" och teckenstorleken är inställd på 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Steg 8: Ställ in marginalinformation
Justera HTML-fragmentets nedre och övre marginaler om det behövs. I den medföljande koden är den nedre marginalen inställd på 10 och den övre marginalen är inställd på 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Steg 9: Lägg till HtmlFragmentet på sidan
 Lägg till`HtmlFragment` invända mot styckesamlingen på sidan.

```csharp
page.Paragraphs.Add(title);
```

## Steg 10: Spara PDF-dokumentet
 Spara PDF-dokumentet med hjälp av`Save` metod för`Document` objekt. Ange sökvägen till utdatafilen som du ställde in i steg 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Exempel på källkod för Add HTMLUsing DOMAnd Overwrite med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiera dokumentobjekt
Document doc = new Document();
// Lägg till en sida till sidsamling av PDF-fil
Page page = doc.Pages.Add();
// Instantiera HtmlFragment med HTML-innehåll
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//Teckensnittsfamiljen från 'Verdana' kommer att återställas till 'Arial'
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Ställ in bottenmarginalinformation
title.Margin.Bottom = 10;
// Ange toppmarginalinformation
title.Margin.Top = 400;
// Lägg till HTML-fragment till styckesamlingen på sidan
page.Paragraphs.Add(title);
// Spara PDF-fil
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Spara PDF-fil
doc.Save(dataDir);
```

## Slutsats
Du har framgångsrikt lagt till HTML-innehåll med DOM i Aspose.PDF för .NET och skrivit över stilarna för HTML-innehållet. Den resulterande PDF-filen kan nu hittas på den angivna sökvägen för utdatafilen.

### FAQ's

#### F: Vad är fokus för denna handledning?

S: Denna handledning är utformad för att leda dig genom processen att lägga till HTML-innehåll till ett PDF-dokument med hjälp av Document Object Model (DOM) i Aspose.PDF för .NET. Dessutom kommer du att lära dig hur du skriver över stilar för HTML-innehållet, så att du kan anpassa dess utseende. Handledningen tillhandahåller C#-källkodsavsnitt för att demonstrera de nödvändiga stegen.

#### F: Vilka namnutrymmen behöver jag importera för den här handledningen?

S: I kodfilen där du tänker lägga till HTML-innehåll, importera följande namnområden i början av filen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### F: Hur anger jag dokumentkatalogen och sökvägen till utdatafilen?

 S: Lokalisera raden i koden`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

#### F: Hur skapar jag ett dokumentobjekt?

 S: I steg 4 kommer du att instansiera en ny`Document` objekt med följande kodrad:

```csharp
Document doc = new Document();
```

#### F: Hur lägger jag till en sida i dokumentet?

 S: I steg 5 lägger du till en ny sida i dokumentet med hjälp av`Add` metod för`Pages` samling:

```csharp
Page page = doc.Pages.Add();
```

#### F: Hur kan jag ställa in HTML-innehåll med DOM?

 S: I steg 6 skapar du en`HtmlFragment` objekt och tilldela önskat HTML-innehåll till det. HTML-innehållet tilldelas variabeln`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### F: Hur kan jag skriva över formaten för HTML-innehållet?

 S: I steg 7 kommer du att skriva över formaten för HTML-innehållet genom att ändra`TextState` egenskaper hos`HtmlFragment` objekt. Du kan till exempel ändra teckensnittsfamiljen till "Arial" och ställa in teckenstorleken till 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### F: Kan jag justera marginalen på HTML-innehållet?

S: Ja, i steg 8 kan du justera HTML-fragmentets nedre och övre marginaler efter behov:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### F: Hur lägger jag till HtmlFragmentet i PDF-dokumentet?

 S: I steg 9 lägger du till`HtmlFragment` objekt (`title`) till styckesamlingen på sidan:

```csharp
page.Paragraphs.Add(title);
```

#### F: Hur sparar jag det resulterande PDF-dokumentet?

 S: Efter att ha lagt till HTML-innehållet och anpassat dess stilar, använd`Save` metod för`Document` objekt för att spara PDF-dokumentet:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### F: Vad är nyckeln till den här handledningen?

S: Genom att följa denna handledning har du framgångsrikt lärt dig hur du införlivar HTML-innehåll med hjälp av Document Object Model (DOM) i Aspose.PDF för .NET. Dessutom har du fått möjligheten att skriva över stilar för att skräddarsy utseendet på HTML-innehållet i det resulterande PDF-dokumentet.