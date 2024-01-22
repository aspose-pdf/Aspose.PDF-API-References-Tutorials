---
title: Ersetzen Sie Schriftarten in einer PDF-Datei
linktitle: Ersetzen Sie Schriftarten in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie Schriftarten in einer PDF-Datei mit Aspose.PDF für .NET ersetzen.
type: docs
weight: 340
url: /de/net/programming-with-text/replace-fonts/
---
In diesem Tutorial erklären wir, wie Sie bestimmte Schriftarten in einer PDF-Datei mithilfe der Aspose.PDF-Bibliothek für .NET ersetzen. Wir werden Schritt für Schritt den Prozess des Ladens eines PDF-Dokuments, der Suche nach Textfragmenten, der Identifizierung der zu ersetzenden Schriftarten, dem Ersetzen der Schriftarten und dem Speichern der geänderten PDF-Datei mit dem bereitgestellten C#-Quellcode durchgehen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF für .NET-Bibliothek installiert.
- Ein grundlegendes Verständnis der C#-Programmierung.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein

 Zuerst müssen Sie den Pfad zu dem Verzeichnis festlegen, in dem sich die Eingabe-PDF-Datei befindet. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu Ihrer PDF-Datei.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das PDF-Dokument

 Als nächstes laden wir das PDF-Dokument mit`Document` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Schritt 3: Schriftarten suchen und ersetzen

 Wir erstellen eine`TextFragmentAbsorber`Objekt und legen Sie die Bearbeitungsoption fest, um nicht verwendete Schriftarten zu entfernen. Anschließend durchsuchen wir alle Seiten des PDF-Dokuments nach Textfragmenten.

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

### FAQs

#### F: Was ist der Zweck des Tutorials „Schriftarten in PDF-Dateien ersetzen“?

A: Das Tutorial „Schriftarten in PDF-Dateien ersetzen“ zeigt, wie Sie mit der Aspose.PDF-Bibliothek für .NET bestimmte Schriftarten in einem PDF-Dokument ersetzen. Es bietet eine Schritt-für-Schritt-Anleitung zum Laden eines PDF-Dokuments, zur Suche nach Textfragmenten, zur Identifizierung der zu ersetzenden Schriftarten, zum Ersetzen der Schriftarten und zum Speichern der geänderten PDF-Datei.

#### F: Warum sollte ich Schriftarten in einem PDF-Dokument ersetzen wollen?

A: Das Ersetzen von Schriftarten in einem PDF-Dokument kann erforderlich sein, wenn Sie das Erscheinungsbild des Textes standardisieren oder die Kompatibilität des Dokuments über verschiedene Geräte und Plattformen hinweg verbessern möchten. Dadurch können Sie eine konsistente Typografie und Formatierung sicherstellen.

#### F: Wie richte ich das Dokumentenverzeichnis ein?

A: So richten Sie das Dokumentenverzeichnis ein:

1.  Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu dem Verzeichnis, in dem sich Ihre Eingabe-PDF-Datei befindet.

#### F: Wie ersetze ich bestimmte Schriftarten in einem PDF-Dokument?

A: Das Tutorial führt Sie Schritt für Schritt durch den Prozess:

1.  Laden Sie das PDF-Dokument mit`Document` Klasse.
2.  Ein ... kreieren`TextFragmentAbsorber` Objekt und legen Sie die Bearbeitungsoption fest, um nicht verwendete Schriftarten zu entfernen. Akzeptieren Sie den Absorber für alle Seiten, um nach Textfragmenten zu suchen.
3. Gehen Sie die identifizierten Textfragmente durch. Wenn der Schriftartname eines Textfragments mit der Schriftart übereinstimmt, die Sie ersetzen möchten, ersetzen Sie ihn durch die neue Schriftart.

####  F: Was ist der Zweck der Verwendung?`TextFragmentAbsorber` with font replacement options?

 A: Die`TextFragmentAbsorber` Mit Optionen zum Ersetzen von Schriftarten können Sie Textfragmente finden und gleichzeitig nicht verwendete Schriftarten entfernen. Dies ist wichtig, um sicherzustellen, dass die ersetzten Schriftarten nicht als zusätzliche Ressourcen im PDF hinzugefügt werden.

#### F: Wie identifiziere ich bestimmte Schriftarten, die ersetzt werden sollen?

A: Durch Durchlaufen der vom Absorber identifizierten Textfragmente können Sie auf die Schriftartinformationen für jedes Textfragment zugreifen. Wenn der Schriftartname mit der Schriftart übereinstimmt, die Sie ersetzen möchten, können Sie die Ersetzung durchführen.

#### F: Was passiert, wenn die zu ersetzende Schriftart in einem Textfragment nicht gefunden wird?

A: Wenn die zu ersetzende Schriftart in einem Textfragment nicht gefunden wird, bleibt die Schriftart des Textfragments unverändert. Die Ersetzung erfolgt nur, wenn der Schriftartname übereinstimmt.

#### F: Gibt es eine Einschränkung beim Ersetzen von Schriftarten in diesem Tutorial?

A: Dieses Tutorial konzentriert sich auf das Ersetzen bestimmter Schriftarten in Textfragmenten. Wenn Sie Schriftarten in anderen Kontexten ersetzen müssen, beispielsweise in Anmerkungen oder Formularfeldern, müssen Sie den Ansatz entsprechend erweitern.

#### F: Was ist das erwartete Ergebnis der Ausführung des bereitgestellten Codes?

A: Indem Sie dem Tutorial folgen und den bereitgestellten C#-Code ausführen, ersetzen Sie bestimmte Schriftarten im PDF-Dokument. Die durch die von Ihnen festgelegten Kriterien identifizierten Schriftarten werden durch die von Ihnen angegebene neue Schriftart ersetzt.

#### F: Kann ich diesen Ansatz verwenden, um Schriftarten im gesamten PDF-Dokument zu ersetzen?

A: Ja, Sie können den Code anpassen, um Schriftarten im gesamten PDF-Dokument zu ersetzen, indem Sie alle Textfragmente durchlaufen und die Logik zum Ersetzen von Schriftarten anwenden.