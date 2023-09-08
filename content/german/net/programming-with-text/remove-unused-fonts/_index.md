---
title: Entfernen Sie nicht verwendete Schriftarten in der PDF-Datei
linktitle: Entfernen Sie nicht verwendete Schriftarten in der PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET nicht verwendete Schriftarten in einer PDF-Datei entfernen.
type: docs
weight: 300
url: /de/net/programming-with-text/remove-unused-fonts/
---
In diesem Tutorial erklären wir, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET nicht verwendete Schriftarten in einer PDF-Datei entfernen. Wir werden Schritt für Schritt den Prozess des Ladens einer PDF-Datei, der Identifizierung und Entfernung nicht verwendeter Schriftarten und der Speicherung der aktualisierten PDF-Datei mit dem bereitgestellten C#-Quellcode durchgehen.

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

### FAQs

#### F: Was ist der Zweck des Tutorials „Entfernen nicht verwendeter Schriftarten in PDF-Dateien“?

A: Das Tutorial „Entfernen nicht verwendeter Schriftarten in einer PDF-Datei“ erklärt, wie Sie mit der Aspose.PDF-Bibliothek für .NET nicht verwendete Schriftarten aus einem PDF-Dokument entfernen. Das Tutorial führt Sie durch den Prozess des Ladens einer PDF-Datei, des Identifizierens und Entfernens nicht verwendeter Schriftarten und des Speicherns der aktualisierten PDF-Datei.

#### F: Warum sollte ich nicht verwendete Schriftarten aus einem PDF-Dokument entfernen?

A: Das Entfernen nicht verwendeter Schriftarten aus einem PDF-Dokument kann dazu beitragen, die Dateigröße zu reduzieren und das Dokument für eine bessere Leistung zu optimieren. Dies ist besonders nützlich, wenn Sie mit PDFs arbeiten, die eingebettete Schriftarten enthalten, die im Inhalt des Dokuments nicht tatsächlich verwendet werden.

#### F: Wie richte ich das Dokumentenverzeichnis ein?

A: So richten Sie das Dokumentenverzeichnis ein:

1.  Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu dem Verzeichnis, in dem sich Ihre PDF-Dateien befinden.

#### F: Wie entferne ich mithilfe der Aspose.PDF-Bibliothek nicht verwendete Schriftarten aus einem PDF-Dokument?

A: Das Tutorial führt Sie Schritt für Schritt durch den Prozess:

1.  Öffnen Sie das PDF-Dokument mit`Document` Klasse.
2.  Ein ... kreieren`TextFragmentAbsorber` Objekt mit`TextEditOptions` einstellen`FontReplace.RemoveUnusedFonts`.
3. Akzeptieren Sie den Absorber, um nicht verwendete Schriftarten aus dem PDF zu identifizieren und zu entfernen.
4.  Alles durchlaufen`TextFragments` und stellen Sie die Schriftart auf die gewünschte Schriftart ein.
5. Speichern Sie das aktualisierte PDF-Dokument.

####  F: Was ist der Zweck des`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 A: Die`TextEditOptions.FontReplace.RemoveUnusedFonts` Parameter weist die an`TextFragmentAbsorber` um nicht verwendete Schriftarten aus dem PDF-Dokument zu identifizieren und zu entfernen.

#### F: Kann ich nicht verwendete Schriftarten durch eine Schriftart meiner Wahl ersetzen?

A: Ja, Sie können den Code ändern, um nicht verwendete Schriftarten durch eine Schriftart Ihrer Wahl zu ersetzen. Im bereitgestellten Beispielcode wird als Ersatz die Schriftart „Arial, Bold“ verwendet.

####  F: Wie funktioniert das?`TextFragmentAbsorber` work to remove unused fonts?

 A: Die`TextFragmentAbsorber` wird mit dem konfiguriert`TextEditOptions.FontReplace.RemoveUnusedFonts` Parameter, der nicht verwendete Schriftarten in den Textfragmenten der PDF identifiziert. Nach der Absorption können Sie die Schritte durchlaufen`TextFragments` und stellen Sie ihre Schriftarten auf die gewünschten Ersatzschriftarten ein.

#### F: Was ist das erwartete Ergebnis der Ausführung des bereitgestellten Codes?

A: Indem Sie dem Tutorial folgen und den bereitgestellten C#-Code ausführen, entfernen Sie nicht verwendete Schriftarten aus dem Eingabe-PDF-Dokument und speichern die aktualisierte Version als Ausgabe-PDF-Datei.

#### F: Kann ich den Code ändern, um Schriftarten nur von bestimmten Seiten oder Bereichen zu entfernen?

A: Der bereitgestellte Code konzentriert sich auf das Entfernen nicht verwendeter Schriftarten aus dem gesamten PDF-Dokument. Wenn Sie bestimmte Seiten oder Regionen für die Schriftartentfernung auswählen möchten, müssen Sie den Ansatz ändern und eine komplexere Logik verwenden, um nicht verwendete Schriftarten in diesen Bereichen zu identifizieren.