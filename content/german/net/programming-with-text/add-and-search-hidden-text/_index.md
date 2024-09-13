---
title: Hinzufügen und Suchen von verstecktem Text in einer PDF-Datei
linktitle: Hinzufügen und Suchen von verstecktem Text in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Hinzufügen und Suchen von verstecktem Text in PDF-Dateien mit Aspose.PDF für .NET.
type: docs
weight: 20
url: /de/net/programming-with-text/add-and-search-hidden-text/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET versteckten Text in PDF-Dateien hinzufügen und suchen. Befolgen Sie diese Schritte, um diesen Vorgang problemlos durchzuführen.

## 1. Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder eine andere Entwicklungsumgebung installiert und konfiguriert.
- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET installiert. Sie können sie von der offiziellen Aspose-Website herunterladen.

## 2. Erstellen des PDF-Dokuments mit verstecktem Text

Verwenden Sie zunächst den folgenden Code, um ein neues PDF-Dokument mit verstecktem Text zu erstellen:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Erstellen eines Dokuments
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Texteigenschaft festlegen - unsichtbar
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Geben Sie unbedingt den gewünschten Pfad und Dateinamen für das PDF-Dokument an.

## 3. Suchen Sie nach Text im Dokument

Als nächstes suchen wir nach dem versteckten Text im PDF-Dokument. Verwenden Sie den folgenden Code:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
// Machen Sie etwas mit den Fragmenten
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Dadurch wird der versteckte Text auf der zweiten Seite des PDF-Dokuments durchsucht und die relevanten Informationen angezeigt.

### Beispielquellcode zum Hinzufügen und Suchen von verstecktem Text mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Dokument mit ausgeblendetem Text erstellen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Texteigenschaft festlegen - unsichtbar
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Text im Dokument suchen
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Machen Sie etwas mit Fragmenten
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich versteckten Text in einem PDF-Dokument hinzugefügt und gefunden. Sie können diese Methode jetzt auf Ihre eigenen Projekte anwenden, um versteckten Text in PDF-Dateien zu bearbeiten und zu suchen.

### Häufig gestellte Fragen

#### F: Was ist Aspose.PDF für .NET?

A: Aspose.PDF für .NET ist eine robuste Bibliothek, die Entwicklern das Erstellen, Bearbeiten und Transformieren von PDF-Dokumenten innerhalb von .NET-Anwendungen ermöglicht.

#### F: Kann versteckter Text zu Wasserzeichenzwecken verwendet werden?

A: Auf jeden Fall! Versteckter Text kann als wirksames Mittel zum Wasserzeichen von PDF-Dokumenten dienen und so eine zusätzliche Sicherheitsebene hinzufügen.

#### F: Ist es möglich, versteckten Text in einem PDF-Dokument anzuzeigen?

A: Ja, das Suchen und Anzeigen von verstecktem Text in einem PDF-Dokument ist mit den in diesem Tutorial beschriebenen Techniken möglich.

#### F: Welche anderen Funktionen bietet Aspose.PDF für .NET?

A: Über die versteckte Textbearbeitung hinaus bietet Aspose.PDF für .NET eine breite Palette an Funktionen, darunter PDF-Generierung, Konvertierung, Verschlüsselung und mehr.