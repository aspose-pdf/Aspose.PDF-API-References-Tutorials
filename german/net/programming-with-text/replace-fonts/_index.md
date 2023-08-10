---
title: Schriftarten ersetzen
linktitle: Schriftarten ersetzen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie Schriftarten in einem PDF-Dokument mit Aspose.PDF für .NET ersetzen.
type: docs
weight: 340
url: /de/net/programming-with-text/replace-fonts/
---

In diesem Tutorial erklären wir, wie Sie bestimmte Schriftarten in einem PDF-Dokument mithilfe der Aspose.PDF-Bibliothek für .NET ersetzen. Wir werden Schritt für Schritt den Prozess des Ladens eines PDF-Dokuments, der Suche nach Textfragmenten, der Identifizierung der zu ersetzenden Schriftarten, dem Ersetzen der Schriftarten und dem Speichern der geänderten PDF-Datei mit dem bereitgestellten C#-Quellcode durchgehen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF für .NET-Bibliothek installiert.
- Ein grundlegendes Verständnis der C#-Programmierung.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein

 Zuerst müssen Sie den Pfad zu dem Verzeichnis festlegen, in dem sich die Eingabe-PDF-Datei befindet. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir`Variable mit dem Pfad zu Ihrer PDF-Datei.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das PDF-Dokument

 Als nächstes laden wir das PDF-Dokument mit`Document` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Schritt 3: Schriftarten suchen und ersetzen

 Wir erstellen ein`TextFragmentAbsorber` Objekt und legen Sie die Bearbeitungsoption fest, um nicht verwendete Schriftarten zu entfernen. Anschließend durchsuchen wir alle Seiten des PDF-Dokuments nach Textfragmenten.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## Schritt 4: Schriftarten ersetzen

Wir durchlaufen alle vom Absorber identifizierten Textfragmente. Wenn der Schriftartname eines Textfragments mit der gewünschten zu ersetzenden Schriftart übereinstimmt, ersetzen wir ihn durch die neue Schriftart.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## Schritt 5: Speichern Sie das geänderte PDF

Abschließend speichern wir das geänderte PDF-Dokument in der angegebenen Ausgabedatei.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Beispielquellcode für das Ersetzen von Schriftarten mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laden Sie die PDF-Quelldatei
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Durchsuchen Sie Textfragmente und stellen Sie die Bearbeitungsoption so ein, dass nicht verwendete Schriftarten entfernt werden
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Akzeptieren Sie den Absorber für alle Seiten
	pdfDocument.Pages.Accept(absorber);
	// Durchlaufen Sie alle TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// Wenn der Schriftartname ArialMT lautet, ersetzen Sie den Schriftartnamen durch Arial
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	// Aktualisiertes Dokument speichern
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET bestimmte Schriftarten in einem PDF-Dokument ersetzen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie ein PDF-Dokument laden, nach Textfragmenten suchen, bestimmte Schriftarten identifizieren und ersetzen und das geänderte PDF speichern.