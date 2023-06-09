---
title: Entfernen Sie nicht verwendete Schriftarten
linktitle: Entfernen Sie nicht verwendete Schriftarten
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET nicht verwendete Schriftarten aus einem PDF-Dokument entfernen.
type: docs
weight: 300
url: /de/net/programming-with-text/remove-unused-fonts/
---

In diesem Tutorial erklären wir, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET nicht verwendete Schriftarten aus einem PDF-Dokument entfernen. Wir werden Schritt für Schritt den Prozess des Ladens einer PDF-Datei, der Identifizierung und Entfernung nicht verwendeter Schriftarten und der Speicherung der aktualisierten PDF-Datei mit dem bereitgestellten C#-Quellcode durchgehen.

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
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Schritt 3: Identifizieren und entfernen Sie nicht verwendete Schriftarten

 Wir erstellen ein`TextFragmentAbsorber` Objekt mit dem`TextEditOptions` Parameter eingestellt auf`TextEditOptions.FontReplace.RemoveUnusedFonts` . Mit dieser Option können wir nicht verwendete Schriftarten im PDF-Dokument identifizieren und entfernen. Wir durchlaufen dann alle`TextFragments` und stellen Sie die Schriftart auf die gewünschte Schriftart ein.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Schritt 4: Speichern Sie das aktualisierte PDF

Abschließend speichern wir das aktualisierte PDF-Dokument in der angegebenen Ausgabedatei.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Beispielquellcode zum Entfernen nicht verwendeter Schriftarten mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laden Sie die PDF-Quelldatei
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Durchlaufen Sie alle TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Aktualisiertes Dokument speichern
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET nicht verwendete Schriftarten aus einem PDF-Dokument entfernen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie eine PDF-Datei laden, nicht verwendete Schriftarten identifizieren und entfernen und die aktualisierte PDF-Datei speichern.