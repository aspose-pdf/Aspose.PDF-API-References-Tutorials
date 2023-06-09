---
title: Tooltip zum Text hinzufügen
linktitle: Tooltip zum Text hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Tooltips zu Text in einem PDF-Dokument hinzufügen.
type: docs
weight: 90
url: /de/net/programming-with-text/add-tooltip-to-text/
---

Dieses Tutorial führt Sie durch den Prozess des Hinzufügens von Tooltips zu Text in einem PDF-Dokument mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer auf Ihrem Computer installierter C#-Compiler.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Richten Sie das Projekt ein
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in der Sie Tooltips zum Text hinzufügen möchten, am Anfang der Datei die folgenden using-Anweisungen hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Schritt 3: Legen Sie das Dokumentverzeichnis fest
 Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Erstellen Sie ein Beispieldokument mit Text
 Erstelle eine neue`Document` Objekt und fügen Sie Seiten mit Textfragmenten hinzu. Im bereitgestellten Code werden dem Dokument zwei Textfragmente mit dem jeweiligen Tooltip-Text hinzugefügt.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Schritt 5: Öffnen Sie das Dokument und suchen Sie die Textfragmente
 Laden Sie das erstellte Dokument mit`Document` Konstruktor und finden Sie die Textfragmente, die Tooltips benötigen`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Schritt 6: Fügen Sie Tooltips zu den Textfragmenten hinzu
 Durchlaufen Sie die extrahierten Textfragmente und erstellen Sie an ihren Positionen unsichtbare Schaltflächen. Weisen Sie dem den gewünschten Tooltip-Text zu`AlternateName` Eigentum der`ButtonField`. Fügen Sie die Schaltflächenfelder zum Formular des Dokuments hinzu.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Schritt 7: Wiederholen Sie diesen Vorgang für weitere Textfragmente mit langen Tooltips
Wiederholen Sie die Schritte 5 und 6 für Textfragmente mit langen Tooltips. Ändern Sie die Suchkriterien und den Tooltip-Text entsprechend.

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
 Speichern Sie das geänderte PDF-Dokument mit`Save` Methode der`Document` Objekt.

```csharp
document. Save(outputFile);
```

### Beispielquellcode für „Tooltip zu Text hinzufügen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Erstellen Sie ein Beispieldokument mit Text
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
// Durchlaufe die Fragmente
foreach (TextFragment fragment in textFragments)
{
	//Erstellen Sie eine unsichtbare Schaltfläche an der Position des Textfragments
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Der AlternateName-Wert wird von einer Viewer-Anwendung als Tooltip angezeigt
	field.AlternateName = "Tooltip for text.";
	// Fügen Sie dem Dokument ein Schaltflächenfeld hinzu
	document.Form.Add(field);
}
// Als nächstes folgen einige sehr lange Tooltips
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
Sie haben mit Aspose.PDF für .NET erfolgreich Tooltips zu Text in einem PDF-Dokument hinzugefügt. Die resultierende PDF-Datei befindet sich nun im angegebenen Ausgabedateipfad.