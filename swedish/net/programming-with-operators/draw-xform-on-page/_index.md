---
title: Rita XForm på sidan
linktitle: Rita XForm på sidan
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att rita ett XForm-formulär på en PDF-sida med Aspose.PDF för .NET. Lägg till och placera formuläret på sidan.
type: docs
weight: 10
url: /sv/net/programming-with-operators/draw-xform-on-page/
---
I den här handledningen kommer vi att ge dig en steg-för-steg-guide om hur du ritar ett XForm på en sida med Aspose.PDF för .NET. Aspose.PDF är ett kraftfullt bibliotek som låter dig skapa, manipulera och konvertera PDF-dokument programmatiskt. Med hjälp av operatorerna från Aspose.PDF kan du lägga till och placera ett XForm-formulär på en befintlig PDF-sida.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar på plats:

1. Visual Studio installerat med .NET framework.
2. Aspose.PDF-biblioteket för .NET.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt projekt i Visual Studio och lägg till en referens till Aspose.PDF för .NET-biblioteket. Du kan ladda ner biblioteket från Asposes officiella webbplats och installera det på din maskin.

## Steg 2: Importera de nödvändiga namnrymden

I din C#-kodfil, importera de namnutrymmen som krävs för att komma åt klasserna och metoderna som tillhandahålls av Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Steg 3: Ställ in filsökvägar

Definiera filsökvägarna för bakgrundsbilden, indata-PDF-filen och PDF-utdatafilen:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Var noga med att ange de faktiska filsökvägarna på din maskin.

## Steg 4: Ladda in PDF-filen

Använd följande kod för att ladda in PDF-filen:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// Följande kod använder GSave/GRestore-operatorerna
// Koden använder ContatenateMatrix-operatorn för att placera XForm
// Koden använder Do-operatorn för att rita XForm på sidan
// GSave/GRestore-operatörer omsluter befintligt innehåll
// detta görs för att få det ursprungliga grafiktillståndet i slutet av det befintliga innehållet
// annars kan det finnas oönskade transformationer kvar i slutet av kedjan av befintliga operatörer
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Lägg till GSave-operatör för att korrekt återställa grafiktillståndet efter nya kommandon
pageContents. Add(new GSave());

// Skapa XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Ställ in bildens bredd och höjd
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Ladda bilden i en ström
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Lägg till bilden i XForm-resursbildsamlingen
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Använda Do-operatorn: denna operator ritar bilden
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//Placera XForm vid koordinaterna x=100 och y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Rita XForm med Do-operatorn
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Placera XForm vid koordinaterna x=100 och y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Rita XForm med Do-operatorn
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Återställ grafikstatus med GRestore efter GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Var noga med att ange de faktiska filsökvägarna och justera sidnumret och XForm-positionerna efter behov.

### Exempel på källkod för Draw XForm On Page med Aspose.PDF för .NET
 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Provet visar
	// Användning av GSave/GRRestore-operatörer
	// ContatenateMatrix-operatoranvändning för att positionera xForm
	// Använd operatorn för att rita xForm på sidan
	// Slå in befintligt innehåll med GSave/GRestore-operatörspar
	// detta är för att få initialt grafiktillstånd vid och av befintligt innehåll
	// annars kan det finnas några oönskade omvandlingar i slutet av befintlig operatörskedja
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Lägg till operatören för att spara grafiktillstånd för att korrekt rensa grafiktillstånd efter nya kommandon
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Skapa xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Definiera bildens bredd och höjd
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Ladda bilden i stream
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//Lägg till bild till bildsamlingen av XForm-resurserna
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Använda Gör-operatorn: denna operator ritar en bild
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Placera form till x=100 y=500 koordinaterna
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Rita formuläret med Do-operatorn
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Placera form till x=100 y=300 koordinaterna
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Rita formuläret med Do-operatorn
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Återställ grafiktillstånd med GRestore efter GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Slutsats

I den här handledningen lärde du dig hur du ritar ett XForm-formulär på en PDF-sida med Aspose.PDF för .NET. Genom att följa stegen som beskrivs kommer du att kunna lägga till och placera ett XForm-formulär på en befintlig sida, vilket ger mer flexibilitet till dina PDF-dokument.

### Vanliga frågor för draw XForm på sidan

#### F: Vad är en XForm i Aspose.PDF?

S: En XForm är ett återanvändbart grafiskt objekt i ett PDF-dokument. Det låter dig definiera och rita komplex grafik, bilder eller text som kan återanvändas flera gånger på olika sidor.

#### F: Hur importerar jag de nödvändiga namnrymden för Aspose.PDF?

 S: I din C#-kodfil, använd`using` direktiv för att importera de nödvändiga namnområdena för att komma åt klasserna och metoderna som tillhandahålls av Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### F: Vad är syftet med GSave- och GRestore-operatörerna?

 A: Den`GSave` och`GRestore`operatorer i Aspose.PDF används för att spara och återställa grafiktillståndet. De hjälper till att säkerställa att transformationer och inställningar som tillämpas på ett avsnitt av innehållet inte påverkar efterföljande avsnitt.

#### F: Hur definierar jag en XForm med Aspose.PDF?

 S: För att skapa ett XForm, använd`XForm.CreateNewForm` metoden och lägg till den i`Resources.Forms` samling av en specifik sida. Du kan sedan lägga till innehåll till XForms`Contents` fast egendom.

#### F: Hur kan jag rita en bild i en XForm?

 S: Ladda bilden i en ström och lägg till den i`Resources.Images` samling av XForm. Använd`Do` operatör inom XForms`Contents` att rita bilden.

#### F: Hur placerar jag ett XForm på en PDF-sida?

 S: För att placera ett XForm på en sida, använd`ConcatenateMatrix` operatör inom sidans`Contents`. Justera matrisparametrarna för att specificera översättningen (positionen) och skalningen av XForm.

#### F: Kan jag rita flera XForms på samma sida?

 S: Ja, du kan rita flera XForms på samma sida genom att justera`ConcatenateMatrix`parametrar för att placera varje XForm vid olika koordinater.

#### F: Kan jag ändra innehållet i en XForm efter att den har skapats?

 S: Ja, du kan ändra innehållet i en XForm efter att den har skapats genom att lägga till ytterligare operatorer till dess`Contents` fast egendom.

#### F: Vad händer om jag utelämnar GSave- och GRestore-operatörerna?

S: Att utelämna GSave- och GRestore-operatorerna kan leda till att oönskade transformationer eller inställningar tillämpas på efterföljande innehåll. Att använda dem hjälper till att upprätthålla ett rent grafiktillstånd.

#### F: Kan jag återanvända XForms på olika sidor i PDF-dokumentet?

 S: Ja, du kan återanvända XForms på flera sidor genom att lägga till samma XForm till`Resources.Forms` samling av olika sidor.

#### F: Finns det en gräns för antalet XForms jag kan skapa?

S: Även om det inte finns någon strikt gräns för antalet XForms du kan skapa, kom ihåg att för många XForms kan påverka prestanda och minnesanvändning. Använd dem klokt.

#### F: Kan jag rotera en XForm eller tillämpa andra transformationer?

 A: Ja, du kan använda`ConcatenateMatrix`operatör för att tillämpa transformationer som rotation, skalning och translation till en XForm.
