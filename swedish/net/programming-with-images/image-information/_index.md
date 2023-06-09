---
title: Bildinformation
linktitle: Bildinformation
second_title: Aspose.PDF för .NET API Referens
description: Extrahera bildinformation i en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 160
url: /sv/net/programming-with-images/image-information/
---

Den här guiden tar dig steg för steg hur du extraherar information om bilder i en PDF-fil med Aspose.PDF för .NET. Se till att du redan har konfigurerat din miljö och följ stegen nedan:

## Steg 1: Definiera dokumentkatalogen

 Se till att ställa in rätt dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med sökvägen till katalogen där ditt PDF-dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda käll-PDF-filen

 I det här steget kommer vi att ladda käll-PDF-filen med hjälp av`Document` klass av Aspose.PDF. Använd`Document` konstruktor och skicka sökvägen till PDF-dokumentet.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Steg 3: Ställ in standardupplösning

I det här steget kommer vi att ställa in standardupplösningen för bilder. I exemplet är standardupplösningen inställd på 72.

```csharp
int defaultResolution = 72;
```

## Steg 4: Initiera objekt och räknare

I det här steget kommer vi att initiera de objekt och räknare som behövs för att hämta bildinformationen.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Steg 5: Bläddra genom operatorerna på dokumentets första sida

I det här steget går vi igenom operatörerna på dokumentets första sida för att identifiera bildrelaterade operationer.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Steg 6: Hantera operatörer och extrahera bildinformation

I det här steget kommer vi att hantera de olika typerna av operatörer och extrahera informationen om bilderna.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Hantera GSave- och GRRestore-operationer för transformationer
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Hantera ConcatenateMatrix-operationen för transformationer
else if (opCtm != null)
{
     // Tillämpa transformationsmatrisen
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// Hantera Gör-operationen för bilder
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Hämta bilden
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Hämta bildens mått
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Beräkna upplösningen baserat på informationen ovan
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Visa bildinformation
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Exempel på källkod för bildinformation med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ladda käll-PDF-filen
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Definiera standardupplösningen för bilden
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Definiera arraylistobjekt som kommer att innehålla bildnamn
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Infoga ett objekt att stapla
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Få alla operatörer på första sidan av dokumentet
foreach (Operator op in doc.Pages[1].Contents)
{
	// Använd GSave/GRestore-operatorer för att återställa transformationerna till tidigare inställda
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Instantiera ConcatenateMatrix-objekt som det definierar aktuell transformationsmatris.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Skapa Gör-operator som drar objekt från resurser. Den ritar formulärobjekt och bildobjekt
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Spara föregående tillstånd och tryck aktuellt tillstånd till toppen av stacken
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Kasta bort nuvarande tillstånd och återställ föregående
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// Multiplicera nuvarande matris med tillståndsmatrisen
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// Om detta är en bildritningsoperator
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Skapa XImage-objekt för att hålla bilder av första pdf-sidan
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Få bildmått
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Få information om höjd och bredd på bilden
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Beräkna upplösning baserad på ovanstående information
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Visa information om dimension och upplösning för varje bild
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Slutsats

Grattis! Du har nu lärt dig hur du extraherar bildinformation i en PDF-fil med Aspose.PDF för .NET. Du kan använda denna information för olika bildbehandlingsuppgifter i dina applikationer.