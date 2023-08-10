---
title: Lägg till HTML med DOM
linktitle: Lägg till HTML med DOM
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till HTML-innehåll med DOM i Aspose.PDF för .NET.
type: docs
weight: 40
url: /sv/net/programming-with-text/add-html-using-dom/
---

Denna handledning guidar dig genom processen att lägga till HTML-innehåll med DOM (Document Object Model) i Aspose.PDF för .NET. Den medföljande C#-källkoden visar de nödvändiga stegen.

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
```

## Steg 3: Ställ in dokumentkatalogen och utdatafilens sökväg
 I koden, lokalisera raden som säger`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där dina dokument är lagrade.

## Steg 4: Skapa ett nytt dokumentobjekt
 Instantiera en ny`Document` objekt genom att lägga till följande kodrad:

```csharp
Document doc = new Document();
```

## Steg 5: Lägg till en sida i dokumentet
 Lägg till en ny sida i dokumentet med hjälp av`Add` metod för`Pages` samling. I den angivna koden är den nya sidan tilldelad variabeln`page`.

```csharp
Page page = doc.Pages.Add();
```

## Steg 6: Skapa ett HtmlFragment med HTML-innehållet
Instantiera en`HtmlFragment` objekt och tillhandahålla önskat HTML-innehåll. I den medföljande koden är HTML-innehållet tilldelat variabeln`titel`. Du kan ändra HTML-innehållet efter behov.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Steg 7: Ställ in marginalinformation
Justera den nedre och övre marginalen på HTML-fragmentet om det behövs. I den medföljande koden är den nedre marginalen inställd på 10 och den övre marginalen är inställd på 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Steg 8: Lägg till HtmlFragmentet på sidan
 Lägg till`HtmlFragment` invända mot styckesamlingen på sidan.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Steg 9: Spara PDF-dokumentet
 Spara PDF-dokumentet med hjälp av`Save` metod för`Document` objekt. Ange sökvägen till utdatafilen som du ställde in i steg 3.

```csharp
doc.Save(dataDir);
```

## Steg 10: Visa framgångsmeddelandet
Visa ett framgångsmeddelande tillsammans med sökvägen där PDF-filen sparades.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Exempel på källkod för Add HTMLUsing DOM med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiera dokumentobjekt
Document doc = new Document();
// Lägg till en sida till sidsamling av PDF-fil
Page page = doc.Pages.Add();
// Instantiera HtmlFragment med HTML-innehåll
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Ställ in bottenmarginalinformation
titel.Margin.Bottom = 10;
// Ange toppmarginalinformation
titel.Margin.Top = 200;
// Lägg till HTML-fragment till styckesamlingen på sidan
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// Spara PDF-fil
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Slutsats
Du har framgångsrikt lagt till HTML-innehåll med DOM i Aspose.PDF för .NET. Den resulterande PDF-filen kan nu hittas på den angivna sökvägen för utdatafilen.