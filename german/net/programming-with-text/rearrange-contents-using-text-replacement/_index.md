---
title: Ordnen Sie Inhalte mithilfe von Textersetzung neu an
linktitle: Ordnen Sie Inhalte mithilfe von Textersetzung neu an
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie Inhalte in einem PDF-Dokument mithilfe von Textersetzung mit Aspose.PDF für .NET neu anordnen.
type: docs
weight: 270
url: /de/net/programming-with-text/rearrange-contents-using-text-replacement/
---

In diesem Tutorial erklären wir, wie Sie Inhalte in einem PDF-Dokument neu anordnen, indem Sie Textersetzung mit der Aspose.PDF-Bibliothek für .NET verwenden. Wir werden Schritt für Schritt den Prozess des Ladens einer PDF-Datei, der Suche nach bestimmten Textfragmenten, dem Ersetzen des Textes und dem Speichern der geänderten PDF-Datei mit dem bereitgestellten C#-Quellcode durchgehen.

## Anforderungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF für .NET-Bibliothek installiert.
- Ein grundlegendes Verständnis der C#-Programmierung.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein

 Zunächst müssen Sie den Pfad zu dem Verzeichnis festlegen, in dem sich Ihre PDF-Dateien befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu Ihren PDF-Dateien.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Quell-PDF

 Als nächstes laden wir das Quell-PDF-Dokument mit`Document` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## Schritt 3: Textfragmente suchen und ersetzen

 Wir erstellen ein`TextFragmentAbsorber` Objekt mit einem regulären Ausdruck, um nach bestimmten Textfragmenten zu suchen. Anschließend durchlaufen wir die Textfragmente, passen Schriftart, Größe und Farbe an und ersetzen den Text.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
doc.Pages.Accept(textFragmentAbsorber);

foreach(TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial");
     textFragment.TextState.FontSize = 12;
     textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
     textFragment.Text = "This is a Larger String for the Testing of this issue";
}
```

## Schritt 4: Speichern Sie das geänderte PDF

Abschließend speichern wir das geänderte PDF-Dokument in der angegebenen Ausgabedatei.

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### Beispielquellcode für „Inhalte mithilfe von Textersetzung neu anordnen“ mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laden Sie die PDF-Quelldatei
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	//Erstellen Sie ein TextFragment Absorber-Objekt mit regulärem Ausdruck
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// Ersetzen Sie jedes TextFragment
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// Legen Sie die Schriftart des zu ersetzenden Textfragments fest
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// Schriftgröße einstellen
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// Ersetzen Sie den Text durch eine Zeichenfolge, die größer als der Platzhalter ist
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// Speichern Sie das resultierende PDF
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie Inhalte in einem PDF-Dokument mithilfe der Textersetzung mit der Aspose.PDF-Bibliothek für .NET neu anordnen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie nach bestimmten Textfragmenten suchen, deren Darstellung anpassen und den Text in einem PDF-Dokument ersetzen.