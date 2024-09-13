---
title: Schriftarten in PDF-Datei ersetzen
linktitle: Schriftarten in PDF-Datei ersetzen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Schriftarten in PDF-Dateien ersetzen.
type: docs
weight: 340
url: /de/net/programming-with-text/replace-fonts/
---
In diesem Tutorial erklären wir, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET bestimmte Schriftarten in PDF-Dateien ersetzen. Wir gehen Schritt für Schritt durch den Prozess des Ladens eines PDF-Dokuments, der Suche nach Textfragmenten, der Identifizierung der zu ersetzenden Schriftarten, des Ersetzens der Schriftarten und des Speicherns der geänderten PDF-Datei mithilfe des bereitgestellten C#-Quellcodes.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF-Bibliothek für .NET ist installiert.
- Grundlegende Kenntnisse der C#-Programmierung.

## Schritt 1: Einrichten des Dokumentverzeichnisses

 Zuerst müssen Sie den Pfad zum Verzeichnis festlegen, in dem Sie die Eingabe-PDF-Datei haben. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu Ihrer PDF-Datei.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das PDF-Dokument

 Als nächstes laden wir das PDF-Dokument mit dem`Document` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Schritt 3: Schriftarten suchen und ersetzen

 Wir schaffen eine`TextFragmentAbsorber` Objekt und setzen Sie die Bearbeitungsoption, um nicht verwendete Schriftarten zu entfernen. Anschließend akzeptieren wir den Absorber für alle Seiten des PDF-Dokuments, um nach Textfragmenten zu suchen.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## Schritt 4: Schriftarten ersetzen

Wir durchlaufen alle vom Absorber identifizierten Textfragmente. Wenn der Schriftname eines Textfragments mit der gewünschten zu ersetzenden Schriftart übereinstimmt, ersetzen wir ihn durch die neue Schriftart.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## Schritt 5: Speichern Sie die geänderte PDF-Datei

Abschließend speichern wir das geänderte PDF-Dokument in der angegebenen Ausgabedatei.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Beispielquellcode zum Ersetzen von Schriftarten mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// PDF-Quelldatei laden
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Durchsuchen Sie Textfragmente und legen Sie die Bearbeitungsoption „Nicht verwendete Schriftarten entfernen“ fest.
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Akzeptieren Sie den Absorber für alle Seiten
	pdfDocument.Pages.Accept(absorber);
	// Durchlaufen Sie alle Textfragmente
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// Wenn der Schriftname ArialMT lautet, ersetzen Sie den Schriftnamen durch Arial
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

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Schriftarten in PDF-Dateien ersetzen“?

A: Das Tutorial „Schriftarten in PDF-Datei ersetzen“ zeigt, wie Sie die Aspose.PDF-Bibliothek für .NET verwenden, um bestimmte Schriftarten in einem PDF-Dokument zu ersetzen. Es enthält eine Schritt-für-Schritt-Anleitung zum Laden eines PDF-Dokuments, Suchen nach Textfragmenten, Identifizieren zu ersetzender Schriftarten, Ersetzen der Schriftarten und Speichern der geänderten PDF-Datei.

#### F: Warum sollte ich Schriftarten in einem PDF-Dokument ersetzen wollen?

A: Das Ersetzen von Schriftarten in einem PDF-Dokument kann erforderlich sein, wenn Sie das Erscheinungsbild des Textes standardisieren oder die Kompatibilität des Dokuments zwischen verschiedenen Geräten und Plattformen verbessern möchten. Dadurch können Sie eine einheitliche Typografie und Formatierung sicherstellen.

#### F: Wie richte ich das Dokumentverzeichnis ein?

A: So richten Sie das Dokumentverzeichnis ein:

1.  Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zum Verzeichnis, in dem sich Ihre Eingabe-PDF-Datei befindet.

#### F: Wie ersetze ich bestimmte Schriftarten in einem PDF-Dokument?

A: Das Tutorial führt Sie Schritt für Schritt durch den Vorgang:

1.  Laden Sie das PDF-Dokument mit dem`Document` Klasse.
2.  Erstellen Sie ein`TextFragmentAbsorber` Objekt und setzen Sie die Bearbeitungsoption, um nicht verwendete Schriftarten zu entfernen. Akzeptieren Sie den Absorber für alle Seiten, um nach Textfragmenten zu suchen.
3. Durchsuchen Sie die identifizierten Textfragmente. Wenn der Schriftname eines Textfragments mit der zu ersetzenden Schriftart übereinstimmt, ersetzen Sie ihn durch die neue Schriftart.

####  F: Was ist der Zweck der Verwendung`TextFragmentAbsorber` with font replacement options?

 A: Die`TextFragmentAbsorber` mit Optionen zum Ersetzen von Schriftarten können Sie Textfragmente lokalisieren und gleichzeitig nicht verwendete Schriftarten entfernen. Dies ist wichtig, um sicherzustellen, dass die ersetzten Schriftarten nicht als zusätzliche Ressourcen im PDF hinzugefügt werden.

#### F: Wie identifiziere ich bestimmte Schriftarten, die ersetzt werden sollen?

A: Indem Sie die vom Absorber identifizierten Textfragmente durchgehen, können Sie auf die Schriftartinformationen für jedes Textfragment zugreifen. Wenn der Schriftartname mit der Schriftart übereinstimmt, die Sie ersetzen möchten, können Sie den Austausch durchführen.

#### F: Was passiert, wenn die zu ersetzende Schriftart in einem Textfragment nicht gefunden wird?

A: Wenn die zu ersetzende Schriftart in einem Textfragment nicht gefunden wird, bleibt die Schriftart des Textfragments unverändert. Die Ersetzung erfolgt nur, wenn der Schriftartname übereinstimmt.

#### F: Gibt es eine Einschränkung beim Ersetzen von Schriftarten in diesem Tutorial?

A: In diesem Tutorial geht es hauptsächlich um das Ersetzen bestimmter Schriftarten in Textfragmenten. Wenn Sie Schriftarten in anderen Kontexten ersetzen müssen, z. B. in Anmerkungen oder Formularfeldern, müssen Sie den Ansatz entsprechend erweitern.

#### F: Was ist das erwartete Ergebnis der Ausführung des bereitgestellten Codes?

A: Indem Sie dem Tutorial folgen und den bereitgestellten C#-Code ausführen, ersetzen Sie bestimmte Schriftarten im PDF-Dokument. Die durch die von Ihnen festgelegten Kriterien identifizierten Schriftarten werden durch die von Ihnen angegebene neue Schriftart ersetzt.

#### F: Kann ich mit diesem Ansatz Schriftarten im gesamten PDF-Dokument ersetzen?

A: Ja, Sie können den Code anpassen, um Schriftarten im gesamten PDF-Dokument zu ersetzen, indem Sie alle Textfragmente durchlaufen und die Schriftartenersetzungslogik anwenden.