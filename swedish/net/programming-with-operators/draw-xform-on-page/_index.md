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

## Steg 3: Ställa in filsökvägar

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
//Följande kod använder GSave/GRestore-operatorerna
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
// Placera XForm vid koordinaterna x=100 och y=500
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
	// Lägg till bild till bildsamlingen av XForm-resurserna
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

den här handledningen lärde du dig hur du ritar ett XForm-formulär på en PDF-sida med Aspose.PDF för .NET. Genom att följa stegen som beskrivs kommer du att kunna lägga till och placera ett XForm-formulär på en befintlig sida, vilket ger mer flexibilitet till dina PDF-dokument.
