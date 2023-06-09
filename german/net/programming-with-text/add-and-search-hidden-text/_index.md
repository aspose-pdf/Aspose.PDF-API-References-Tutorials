---
title: Versteckten Text hinzufügen und durchsuchen
linktitle: Versteckten Text hinzufügen und durchsuchen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Hinzufügen und Suchen von verstecktem Text in einem PDF-Dokument mit Aspose.PDF für .NET.
type: docs
weight: 20
url: /de/net/programming-with-text/add-and-search-hidden-text/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET versteckten Text in einem PDF-Dokument hinzufügen und durchsuchen. Befolgen Sie diese Schritte, um diesen Vorgang einfach durchzuführen.

## 1. Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder eine andere Entwicklungsumgebung installiert und konfiguriert.
- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET installiert. Sie können es von der offiziellen Website von Aspose herunterladen.

## 2. Erstellen des PDF-Dokuments mit verstecktem Text

Verwenden Sie zunächst den folgenden Code, um ein neues PDF-Dokument mit ausgeblendetem Text zu erstellen:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Erstellen Sie ein Dokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Texteigenschaft festlegen – unsichtbar
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Geben Sie unbedingt den gewünschten Pfad und Dateinamen für das PDF-Dokument an.

## 3. Suchen Sie nach Text im Dokument

Als nächstes durchsuchen wir den versteckten Text im PDF-Dokument. Verwenden Sie den folgenden Code:

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

### Beispielquellcode für das Hinzufügen und Suchen von verstecktem Text mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Erstellen Sie ein Dokument mit verstecktem Text
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Texteigenschaft festlegen – unsichtbar
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Suchen Sie nach Text im Dokument
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

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich versteckten Text in einem PDF-Dokument hinzugefügt und gefunden. Sie können diese Methode jetzt auf Ihre eigenen Projekte anwenden, um versteckten Text in PDF-Dateien zu bearbeiten und zu durchsuchen.