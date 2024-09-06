---
title: Tooltip zum Text in der PDF-Datei hinzufügen
linktitle: Tooltip zum Text in der PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Tooltips zu Texten in PDF-Dateien hinzufügen.
type: docs
weight: 90
url: /de/net/programming-with-text/add-tooltip-to-text/
---
Dieses Tutorial führt Sie durch den Prozess des Hinzufügens von Tooltips zu Text in PDF-Dateien mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die erforderlichen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer C#-Compiler muss auf Ihrem Computer installiert sein.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Einrichten des Projekts
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in der Sie dem Text Tooltips hinzufügen möchten, oben in der Datei die folgenden Using-Direktiven hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Schritt 3: Dokumentverzeichnis festlegen
 Suchen Sie im Code nach der Zeile, die besagt:`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den Pfad zum Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Erstellen Sie ein Beispieldokument mit Text
 Erstellen Sie ein neues`Document` Objekt und Seiten mit Textfragmenten hinzufügen. Im bereitgestellten Code werden dem Dokument zwei Textfragmente mit dem jeweiligen Tooltip-Text hinzugefügt.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Schritt 5: Öffnen Sie das Dokument und finden Sie die Textfragmente
 Laden Sie das erstellte Dokument mit dem`Document` Konstruktor und finden Sie die Textfragmente, die Tooltips benötigen, mit`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Schritt 6: Tooltips zu den Textfragmenten hinzufügen
 Durchlaufen Sie die extrahierten Textfragmente und erstellen Sie unsichtbare Schaltflächen an deren Positionen. Weisen Sie den gewünschten Tooltip-Text dem`AlternateName` Eigentum der`ButtonField`. Fügen Sie die Schaltflächenfelder zum Formular des Dokuments hinzu.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Schritt 7: Wiederholen Sie den Vorgang für weitere Textfragmente mit langen Tooltips
Wiederholen Sie die Schritte 5 und 6 für Textfragmente mit langen Tooltips. Passen Sie die Suchkriterien und den Tooltip-Text entsprechend an.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## Schritt 8: Speichern Sie das geänderte Dokument
 Speichern Sie das geänderte PDF-Dokument mit dem`Save` Methode der`Document` Objekt.

```csharp
document. Save(outputFile);
```

### Beispielquellcode zum Hinzufügen von Tooltips zu Text mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Beispieldokument mit Text erstellen
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Dokument mit Text öffnen
Document document = new Document(outputFile);
// Erstellen Sie ein TextAbsorber-Objekt, um alle Phrasen zu finden, die dem regulären Ausdruck entsprechen
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Akzeptieren Sie den Absorber für die Dokumentseiten
document.Pages.Accept(absorber);
// Holen Sie sich die extrahierten Textfragmente
TextFragmentCollection textFragments = absorber.TextFragments;
// Durchlaufen der Fragmente
foreach (TextFragment fragment in textFragments)
{
	// Unsichtbare Schaltfläche an der Textfragmentposition erstellen
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Der AlternateName-Wert wird von einer Viewer-Anwendung als Tooltip angezeigt
	field.AlternateName = "Tooltip for text.";
	// Schaltflächenfeld zum Dokument hinzufügen
	document.Form.Add(field);
}
// Als nächstes folgt ein Beispiel für einen sehr langen Tooltip
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Sehr langen Text einstellen
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// Dokument speichern
document.Save(outputFile);
```

## Abschluss
Sie haben mit Aspose.PDF für .NET erfolgreich Tooltips zum Text in einem PDF-Dokument hinzugefügt. Die resultierende PDF-Datei befindet sich jetzt im angegebenen Ausgabedateipfad.

## FAQs

#### F: Worauf liegt der Schwerpunkt dieses Tutorials?

A: In diesem Tutorial geht es darum, mithilfe der Bibliothek Aspose.PDF für .NET Tooltips zu Text in einer PDF-Datei hinzuzufügen. Der bereitgestellte C#-Quellcode zeigt die dazu erforderlichen Schritte.

#### F: Welche Namespaces müssen für dieses Tutorial importiert werden?

A: Importieren Sie in der Codedatei, in der Sie dem Text Tooltips hinzufügen möchten, am Anfang der Datei die folgenden Namespaces:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### F: Wie gebe ich das Dokumentverzeichnis an?

 A: Suchen Sie im Code die Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie kann ich ein Beispieldokument mit Text erstellen?

 A: In Schritt 4 erstellen Sie eine neue`Document` Objekt und Seiten mit Textfragmenten hinzufügen. Der bereitgestellte Code fügt zwei Textfragmente mit entsprechendem Tooltip-Text hinzu.

#### F: Wie öffne ich das Dokument und finde die Textfragmente?

 A: In Schritt 5 laden Sie das erstellte Dokument mit dem`Document` Konstruktor und suchen Sie die Textfragmente, die Tooltips benötigen, mithilfe der`TextFragmentAbsorber`.

#### F: Wie füge ich den Textfragmenten Tooltips hinzu?

 A: In Schritt 6 durchlaufen Sie die extrahierten Textfragmente und erstellen unsichtbare Schaltflächen an deren Positionen. Der Tooltip-Text wird dem`AlternateName` Eigentum der`ButtonField`das dem Formular des Dokuments hinzugefügt wird.

#### F: Wie wiederhole ich den Vorgang für weitere Textfragmente mit langen Tooltips?

A: Wiederholen Sie für Textfragmente mit langen Tooltips die Schritte 5 und 6. Ändern Sie die Suchkriterien und den Tooltip-Text entsprechend.

#### F: Wie speichere ich das geänderte Dokument?

 A: In Schritt 8 speichern Sie das geänderte PDF-Dokument mit dem`Save` Methode der`Document` Objekt.

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: In diesem Tutorial haben Sie gelernt, wie Sie Ihr PDF-Dokument verbessern können, indem Sie mit Aspose.PDF für .NET Tooltips zum Text hinzufügen. Dies kann den Lesern bei der Interaktion mit dem PDF-Inhalt wertvolle Zusatzinformationen liefern.