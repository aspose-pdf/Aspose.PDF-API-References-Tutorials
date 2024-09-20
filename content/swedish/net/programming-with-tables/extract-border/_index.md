---
title: Extrahera kant i PDF-fil
linktitle: Extrahera kant i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du extraherar ramar från en PDF-fil och sparar dem som en bild med Aspose.PDF för .NET. Steg-för-steg-guide med kodexempel och tips för framgång.
type: docs
weight: 80
url: /sv/net/programming-with-tables/extract-border/
---
## Introduktion

När du arbetar med PDF-filer kan det verka en skrämmande uppgift att extrahera specifika element som gränser eller grafiska banor. Men med Aspose.PDF för .NET kan du enkelt extrahera gränser eller former från en PDF-fil och spara dem som en bild. I den här handledningen kommer vi att dyka in i processen att extrahera en ram från en PDF och spara den som en PNG-bild. Gör dig redo att ta kontroll över din PDFs grafiska innehåll!

## Förutsättningar

Innan vi dyker in i koden, se till att du har allt konfigurerat:

1.  Aspose.PDF för .NET: Om du inte har installerat Aspose.PDF-biblioteket ännu kan du[ladda ner den här](https://releases.aspose.com/pdf/net/). Du måste också ansöka om licensen, antingen genom den kostnadsfria provperioden eller en köpt licens.
2. IDE-installation: Konfigurera ett C#-projekt i Visual Studio eller någon annan .NET IDE. Se till att du har lagt till de nödvändiga referenserna till Aspose.PDF-biblioteket.
3. Mata in PDF-fil: Ha en PDF-fil redo från vilken du extraherar gränserna. Denna handledning kommer att referera till en fil med namnet`input.pdf`.

## Importera nödvändiga paket

Låt oss komma igång genom att importera de nödvändiga namnrymden. Dessa paket tillhandahåller de verktyg som behövs för att manipulera PDF-innehållet.

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Nu när vi har täckt grunderna, låt oss gå till steg-för-steg-guiden där vi kommer att dela upp varje del av koden för att förklara den i detalj.


## Steg 1: Ladda PDF-dokumentet

Det första steget är att ladda PDF-dokumentet som innehåller gränsen du vill extrahera. Tänk på det som att öppna en bok innan du börjar läsa – du behöver tillgång till innehållet!

 Vi börjar med att ange katalogen där din PDF-fil är lagrad och laddar dokumentet med hjälp av`Aspose.Pdf.Document` klass.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Denna kod laddar`input.pdf` fil från din angivna katalog. Se till att sökvägen till filen är korrekt, annars kan du få ett felmeddelande om att filen inte hittades.

## Steg 2: Konfigurera grafik och bitmapp

Innan vi börjar extrahera måste vi skapa en duk att rita på. I .NET-världen innebär detta att du ställer in en bitmap och grafikobjekt. Bitmappen representerar bilden och grafikobjektet låter oss rita former, till exempel kanter, extraherade från PDF:en.

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

Här är en uppdelning:
- Vi skapar en bitmappsbild i storleken på den första sidan i PDF:en.
- GraphicsPath används för att definiera former (i det här fallet gränser).
- Matrix definierar hur grafik kommer att transformeras; vi behöver en inversionsmatris eftersom PDF och .NET har olika koordinatsystem.

## Steg 3: Bearbeta PDF-innehåll


PDF-filen är en serie ritkommandon, och vi måste bearbeta vart och ett av dessa kommandon för att identifiera och extrahera gränsinformationen.

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Bearbetningskommandon som att spara/återställa tillstånd, rita linjer, fylla former, etc.
}
```

Koden går igenom varje ritoperator i PDF-filens innehållsström. Varje operator kan representera en linje, rektangel eller annan grafisk instruktion.

## Steg 4: Hantera PDF-operatörer

Varje operatör i PDF-filen styr en åtgärd. För att extrahera gränsen måste vi identifiera kommandon som "flytta till", "linje till" och "rita rektangel". Följande operatörer hanterar dessa åtgärder:

- MoveTo: Flyttar markören till en startpunkt.
- LineTo: Ritar en linje från den aktuella punkten till en ny punkt.
- Re: Ritar en rektangel (detta kan vara en del av gränsen).

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

I det här steget:
- Vi fångar punkterna för varje linje eller form som ritas.
- För rektanglar (`opRe` ), lägger vi till dem direkt i`graphicsPath`, som vi kommer att använda senare för att rita gränsen.

## Steg 5: Rita gränsen

När vi har identifierat linjerna och rektanglarna som bildar gränsen måste vi faktiskt rita dem på Bitmap-objektet. Det är här som grafikobjektet kommer in.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- Vi skapar ett grafikobjekt baserat på bitmappen.
- SmoothingMode.HighQuality säkerställer att vi får en fin jämn bild.
- Slutligen använder vi DrawPath för att rita gränsen.

## Steg 6: Spara den extraherade gränsen

Nu när vi har extraherat gränsen är det dags att spara den som en bildfil. Detta kommer att spara gränsen som en PNG.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- Bitmappen sparas som en PNG-bild.
- Du kan nu öppna den här bilden för att se den extraherade kanten.

## Slutsats

Att extrahera ramar från en PDF-fil med Aspose.PDF för .NET kan tyckas vara knepigt till en början, men när du väl bryter ner det blir det enkelt. Genom att förstå ritoperatorerna i en PDF och använda de kraftfulla .NET-biblioteken kan du manipulera och extrahera grafiskt innehåll effektivt. Den här guiden ger dig en robust grund för att komma igång med PDF-manipulation!

## FAQ's

### Hur hanterar jag flera sidor i PDF-filen?  
 Du kan gå igenom varje sida i dokumentet genom att iterera över`doc.Pages` istället för hårdkodning`doc.Pages[1]`.

### Kan jag extrahera andra element, som text, med samma tillvägagångssätt?  
Ja, Aspose.PDF tillhandahåller rika API:er för att extrahera text, bilder och annat innehåll från PDF-filer.

### Hur ansöker jag om en licens för att undvika begränsningar?  
 Du kan[ansöka om en licens](https://purchase.aspose.com/temporary-license/) genom att ladda den genom`License` klass tillhandahållen av Aspose.

### Vad händer om min PDF inte har några gränser?  
Om din PDF-fil inte innehåller några synliga ramar kan det hända att grafikextraheringen inte ger något resultat. Se till att PDF-innehållet innehåller ritbara kanter.

### Kan jag spara utdata i andra format än PNG?  
 Ja, ändra helt enkelt`ImageFormat.Png` till ett annat format som stöds som t.ex`ImageFormat.Jpeg`.