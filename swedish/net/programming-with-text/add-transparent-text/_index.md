---
title: Lägg till transparent text
linktitle: Lägg till transparent text
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till transparent text i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 100
url: /sv/net/programming-with-text/add-transparent-text/
---

Denna handledning guidar dig genom processen att lägga till transparent text till ett PDF-dokument med Aspose.PDF för .NET. Den medföljande C#-källkoden visar de nödvändiga stegen.

## Krav
Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan C#-kompilator installerad på din maskin.
- Aspose.PDF för .NET-bibliotek. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda en pakethanterare som NuGet för att installera den.

## Steg 1: Konfigurera projektet
1. Skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö.
2. Lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnrymder
I kodfilen där du vill lägga till transparent text, lägg till följande med hjälp av direktiv överst i filen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Steg 3: Ställ in dokumentkatalogen
 I koden, lokalisera raden som säger`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där dina dokument är lagrade.

## Steg 4: Skapa en ny dokumentinstans
 Instantiera en ny`Document` objekt genom att lägga till följande kodrad:

```csharp
Document doc = new Document();
```

## Steg 5: Lägg till en sida i dokumentet
 Lägg till en ny sida i dokumentet med hjälp av`Add` metod för`Pages` samling. I den angivna koden är den nya sidan tilldelad variabeln`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Steg 6: Skapa ett Graph-objekt
 Skapa en ny`Graph` objekt med en viss bredd och höjd.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## Steg 7: Skapa en rektangel med genomskinlighet
 Skapa en rektangel med specifika mått och ställ in dess fyllningsfärg till en transparent färg med hjälp av`Color.FromRgb` metod.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## Steg 8: Lägg till Graph-objektet på sidan
 Lägg till`Graph` invända mot styckesamlingen på sidan.

```csharp
page.Paragraphs.Add(canvas);
```

## Steg 9: Ställ in position för Graph-objektet
 Ställ in`IsChangePosition` egendom av`Graph` invända mot`false` för att förhindra att den ändrar position.

```csharp
canvas. IsChangePosition = false;
```

## Steg 10: Skapa ett TextFragment med transparens
 Skapa en`TextFragment` objekt och ställ in dess innehåll till önskad text. Ställ in`ForegroundColor` egendom av`TextState` till en färg med genomskinlighet med hjälp av`Color.FromArgb` metod.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## Steg 11: Spara PDF-dokumentet
 Spara PDF-dokumentet med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### Exempel på källkod för Lägg till transparent text med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Skapa dokumentinstans
Document doc = new Document();
// Skapa sida till sida-samling av PDF-fil
Aspose.Pdf.Page page = doc.Pages.Add();
// Skapa Graph-objekt
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Skapa rektangelinstans med vissa dimensioner
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// Skapa färgobjekt från Alpha färgkanal
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Lägg till rektangulär formsamling av Graph-objekt
canvas.Shapes.Add(rect);
// Lägg till grafobjekt till styckesamling av sidobjekt
page.Paragraphs.Add(canvas);
// Ställ in värde för att inte ändra position för grafobjekt
canvas.IsChangePosition = false;
// Skapa TextFragment-instans med exempelvärde
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// Skapa färgobjekt från alfakanalen
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// Ställ in färginformation för textinstans
text.TextState.ForegroundColor = color;
// Lägg till text till styckesamling av sidinstanser
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## Slutsats
Du har framgångsrikt lagt till transparent text till ditt PDF-dokument med Aspose.PDF för .NET. Den resulterande PDF-filen kan nu hittas på den angivna sökvägen för utdatafilen.