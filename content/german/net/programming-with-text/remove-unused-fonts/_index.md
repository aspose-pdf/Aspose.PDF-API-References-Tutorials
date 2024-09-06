---
title: Entfernen Sie nicht verwendete Schriftarten in der PDF-Datei
linktitle: Entfernen Sie nicht verwendete Schriftarten in der PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET nicht verwendete Schriftarten aus PDF-Dateien entfernen.
type: docs
weight: 300
url: /de/net/programming-with-text/remove-unused-fonts/
---
In diesem Tutorial erklären wir, wie man mithilfe der Aspose.PDF-Bibliothek für .NET ungenutzte Schriftarten aus PDF-Dateien entfernt. Wir gehen Schritt für Schritt durch den Prozess des Ladens einer PDF-Datei, des Identifizierens und Entfernens ungenutzter Schriftarten und des Speicherns der aktualisierten PDF-Datei mithilfe des bereitgestellten C#-Quellcodes.

## Anforderungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF-Bibliothek für .NET ist installiert.
- Grundlegende Kenntnisse der C#-Programmierung.

## Schritt 1: Einrichten des Dokumentverzeichnisses

 Zuerst müssen Sie den Pfad zum Verzeichnis festlegen, in dem sich Ihre PDF-Dateien befinden. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu Ihren PDF-Dateien.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Quell-PDF

 Als nächstes laden wir das Quell-PDF-Dokument mit dem`Document` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Schritt 3: Identifizieren und Entfernen nicht verwendeter Schriftarten

 Wir schaffen eine`TextFragmentAbsorber` Objekt mit dem`TextEditOptions` Parametersatz auf`TextEditOptions.FontReplace.RemoveUnusedFonts` . Mit dieser Option können wir nicht verwendete Schriftarten im PDF-Dokument identifizieren und entfernen. Anschließend durchlaufen wir alle`TextFragments` und stellen Sie die Schriftart auf die gewünschte ein.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Schritt 4: Speichern Sie die aktualisierte PDF-Datei

Abschließend speichern wir das aktualisierte PDF-Dokument in der angegebenen Ausgabedatei.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Beispiel-Quellcode zum Entfernen nicht verwendeter Schriftarten mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// PDF-Quelldatei laden
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

In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET nicht verwendete Schriftarten aus einem PDF-Dokument entfernen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie ein PDF laden, nicht verwendete Schriftarten identifizieren und entfernen und das aktualisierte PDF speichern.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Nicht verwendete Schriftarten in PDF-Dateien entfernen“?

A: Das Tutorial „Nicht verwendete Schriftarten in PDF-Datei entfernen“ erklärt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET nicht verwendete Schriftarten aus einem PDF-Dokument entfernen. Das Tutorial führt Sie durch den Vorgang des Ladens einer PDF-Datei, des Identifizierens und Entfernens nicht verwendeter Schriftarten und des Speicherns der aktualisierten PDF-Datei.

#### F: Warum sollte ich nicht verwendete Schriftarten aus einem PDF-Dokument entfernen wollen?

A: Das Entfernen nicht verwendeter Schriftarten aus einem PDF-Dokument kann dazu beitragen, die Dateigröße zu verringern und die Leistung des Dokuments zu verbessern. Dies ist insbesondere dann nützlich, wenn Sie mit PDF-Dateien arbeiten, die eingebettete Schriftarten enthalten, die im Dokumentinhalt eigentlich nicht verwendet werden.

#### F: Wie richte ich das Dokumentverzeichnis ein?

A: So richten Sie das Dokumentverzeichnis ein:

1.  Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zum Verzeichnis, in dem sich Ihre PDF-Dateien befinden.

#### F: Wie entferne ich mithilfe der Aspose.PDF-Bibliothek nicht verwendete Schriftarten aus einem PDF-Dokument?

A: Das Tutorial führt Sie Schritt für Schritt durch den Vorgang:

1.  Öffnen Sie das PDF-Dokument mit dem`Document` Klasse.
2.  Erstellen Sie ein`TextFragmentAbsorber` Objekt mit`TextEditOptions` eingestellt auf`FontReplace.RemoveUnusedFonts`.
3. Akzeptieren Sie den Absorber, um nicht verwendete Schriftarten zu identifizieren und aus der PDF-Datei zu entfernen.
4.  Durchlaufen Sie alle`TextFragments` und stellen Sie die Schriftart auf die gewünschte ein.
5. Speichern Sie das aktualisierte PDF-Dokument.

####  F: Was ist der Zweck der`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 A: Die`TextEditOptions.FontReplace.RemoveUnusedFonts` Parameter weist den`TextFragmentAbsorber`um nicht verwendete Schriftarten zu identifizieren und aus dem PDF-Dokument zu entfernen.

#### F: Kann ich nicht verwendete Schriftarten durch eine Schriftart meiner Wahl ersetzen?

A: Ja, Sie können den Code ändern, um nicht verwendete Schriftarten durch eine Schriftart Ihrer Wahl zu ersetzen. Im bereitgestellten Beispielcode wird die Schriftart „Arial, Bold“ als Ersatz verwendet.

####  F: Wie funktioniert das`TextFragmentAbsorber` work to remove unused fonts?

 A: Die`TextFragmentAbsorber` ist konfiguriert mit dem`TextEditOptions.FontReplace.RemoveUnusedFonts` Parameter, der nicht verwendete Schriftarten innerhalb der Textfragmente des PDF identifiziert. Nach der Absorption können Sie durch die`TextFragments` und stellen Sie deren Schriftarten auf die gewünschten Ersatzschriftarten ein.

#### F: Was ist das erwartete Ergebnis der Ausführung des bereitgestellten Codes?

A: Indem Sie dem Lernprogramm folgen und den bereitgestellten C#-Code ausführen, entfernen Sie nicht verwendete Schriftarten aus dem PDF-Eingabedokument und speichern die aktualisierte Version als PDF-Ausgabedatei.

#### F: Kann ich den Code ändern, um Schriftarten nur von bestimmten Seiten oder Bereichen zu entfernen?

A: Der bereitgestellte Code konzentriert sich auf das Entfernen nicht verwendeter Schriftarten aus dem gesamten PDF-Dokument. Wenn Sie Schriftarten gezielt auf bestimmten Seiten oder in bestimmten Bereichen entfernen möchten, müssen Sie den Ansatz ändern und eine komplexere Logik verwenden, um nicht verwendete Schriftarten in diesen Bereichen zu identifizieren.