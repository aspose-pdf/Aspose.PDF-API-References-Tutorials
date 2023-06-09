---
title: Wörter durchstreichen
linktitle: Wörter durchstreichen
second_title: Aspose.PDF für .NET API-Referenz
description: Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung von Aspose.PDF für die Funktion „Wörter durchstreichen“ in .NET, einschließlich Schritt-für-Schritt-Anleitung und Erklärungen
type: docs
weight: 150
url: /de/net/annotations/strikeoutwords/
---
Aspose.PDF für .NET ist eine Bibliothek zur Bearbeitung und Verarbeitung von PDF-Dokumenten, die verschiedene Funktionen zum Erstellen, Ändern und Konvertieren von PDF-Dateien bietet. Eine der nützlichen Funktionen von Aspose.PDF ist die Möglichkeit, mithilfe von C#-Quellcode Wörter oder Phrasen in einem PDF-Dokument durchzustreichen. In diesem Artikel stellen wir eine Schritt-für-Schritt-Anleitung zum Durchstreichen von Wörtern mit Aspose.PDF für .NET bereit.

## Schritt 1: Laden des PDF-Dokuments
Der erste Schritt besteht darin, das PDF-Dokument zu laden, das Sie ändern möchten. In diesem Tutorial laden wir ein PDF-Dokument mit dem Namen „input.pdf“ aus dem Ordner „IHR DOKUMENTVERZEICHNIS“. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Schritt 2: Suche nach Textfragmenten
Um bestimmte Wörter oder Ausdrücke im PDF-Dokument zu streichen, müssen Sie zunächst danach suchen. Aspose.PDF stellt eine TextFragmentAbsorber-Klasse bereit, mit der nach einem bestimmten Textfragment im PDF-Dokument gesucht werden kann.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

Im obigen Code suchen wir nach dem Textfragment „Estoque“ im PDF-Dokument. Sie können dies ändern, um nach jedem anderen Wort oder jeder anderen Phrase zu suchen, die Sie streichen möchten.

## Schritt 3: Durchstreichen der Textfragmente
Nachdem Sie die Textfragmente gefunden haben, besteht der nächste Schritt darin, sie zu streichen. Aspose.PDF stellt eine StrikeOutAnnotation-Klasse bereit, mit der eine durchgestrichene Anmerkung für das Textfragment erstellt werden kann. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

Im obigen Code erstellen wir für jedes gefundene Textfragment eine durchgestrichene Anmerkung. Wir legen auch die Deckkraft, den Rand und die Farbe der durchgestrichenen Anmerkung fest.

## Schritt 4: Speichern des geänderten PDF-Dokuments
Nachdem Sie die Textfragmente gestrichen haben, speichern Sie das geänderte Dokument.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Beispielquellcode für Strike Out Words mit Aspose.PDF für .NET


```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document document = new Document(dataDir + "input.pdf");

// Erstellen Sie eine TextFragment Absorber-Instanz, um ein bestimmtes Textfragment zu durchsuchen
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// Durchlaufen Sie Seiten eines PDF-Dokuments
for (int i = 1; i <= document.Pages.Count; i++)
{
	// Holen Sie sich die erste Seite des PDF-Dokuments
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Erstellen Sie eine Sammlung absorbierten Textes
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Iterieren Sie die obige Sammlung
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// Erhalten Sie rechteckige Abmessungen des TextFragment-Objekts
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// Instanziieren Sie die StrikeOut-Annotation-Instanz
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// Legen Sie die Deckkraft für die Anmerkung fest
	strikeOut.Opacity = .80f;
	// Legen Sie den Rahmen für die Anmerkungsinstanz fest
	strikeOut.Border = new Border(strikeOut);
	// Legen Sie die Farbe der Anmerkung fest
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// Anmerkung zur Anmerkungssammlung von TextFragment hinzufügen
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```
