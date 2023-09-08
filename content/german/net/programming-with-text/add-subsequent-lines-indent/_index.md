---
title: Fügen Sie nachfolgende Zeileneinzüge in der PDF-Datei hinzu
linktitle: Fügen Sie nachfolgende Zeileneinzüge in der PDF-Datei hinzu
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET nachfolgende Zeileneinzüge zum Text in einer PDF-Datei hinzufügen.
type: docs
weight: 60
url: /de/net/programming-with-text/add-subsequent-lines-indent/
---
Dieses Tutorial führt Sie durch den Prozess des Hinzufügens nachfolgender Zeileneinzüge zum Text in einer PDF-Datei mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer auf Ihrem Computer installierter C#-Compiler.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Richten Sie das Projekt ein
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in der Sie nachfolgende Zeilen einrücken möchten, die folgende using-Anweisung am Anfang der Datei hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Schritt 3: Legen Sie das Dokumentverzeichnis fest
 Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Erstellen Sie ein neues Dokumentobjekt
 Instanziieren Sie eine neue`Document` Objekt durch Hinzufügen der folgenden Codezeile:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Schritt 5: Fügen Sie dem Dokument eine Seite hinzu
 Fügen Sie dem Dokument eine neue Seite hinzu, indem Sie verwenden`Add` Methode der`Pages`Sammlung. Im bereitgestellten Code wird die neue Seite der Variablen zugewiesen`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Schritt 6: Erstellen Sie ein TextFragment mit nachfolgendem Zeileneinzug
 Instanziieren Sie a`TextFragment` widersprechen und den gewünschten Text angeben. Im bereitgestellten Code wird der Text der Variablen zugewiesen`text` . Dann initialisieren`TextFormattingOptions` für die`TextFragment`und spezifizieren Sie die`SubsequentLinesIndent` Wert.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Schritt 7: Fügen Sie das TextFragment zur Seite hinzu
 Ergänzen Sie die`TextFragment` Einspruch gegen die Absätze-Sammlung der Seite einlegen.

```csharp
page.Paragraphs.Add(text);
```

## Schritt 8: Wiederholen Sie die Schritte 6 und 7 für weitere Zeilen
Um weitere Zeilen mit demselben Einzug hinzuzufügen, wiederholen Sie die Schritte 6 und 7 für jede Zeile. Aktualisieren Sie den Textinhalt nach Bedarf.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## Schritt 9: Speichern Sie das PDF-Dokument
 Speichern Sie das PDF-Dokument mit`Save` Methode der`Document` Objekt. Geben Sie den Pfad der Ausgabedatei an.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Beispielquellcode für das Hinzufügen nachfolgender Zeileneinzüge mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Neues Dokumentobjekt erstellen
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Initialisieren Sie TextFormattingOptions für das Textfragment und geben Sie den SubsequentLinesIndent-Wert an
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Abschluss
Sie haben mit Aspose.PDF für .NET erfolgreich den Einzug nachfolgender Zeilen in den Text eingefügt. Die resultierende PDF-Datei befindet sich nun im angegebenen Ausgabedateipfad.

### FAQs

#### F: Was ist der Schwerpunkt dieses Tutorials?

A: Dieses Tutorial bietet eine umfassende Anleitung zum Hinzufügen nachfolgender Zeileneinzüge zum Text in einer PDF-Datei mithilfe der Aspose.PDF für .NET-Bibliothek. Es enthält Beispiele für C#-Quellcode, um die dafür erforderlichen Schritte zu veranschaulichen.

#### F: Welche Namespaces muss ich für dieses Tutorial importieren?

A: Importieren Sie in der Codedatei, in der Sie nachfolgende Zeileneinzüge hinzufügen möchten, die folgenden Namespaces am Anfang der Datei:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### F: Wie lege ich das Dokumentenverzeichnis fest?

 A: Suchen Sie im Code nach der Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie erstelle ich ein Document-Objekt?

 A: In Schritt 4 instanziieren Sie eine neue`Document` Objekt mithilfe der folgenden Codezeile:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### F: Wie füge ich dem Dokument eine Seite hinzu?

 A: In Schritt 5 fügen Sie dem Dokument eine neue Seite hinzu`Add` Methode der`Pages` Sammlung:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### F: Wie kann ich dem Text nachfolgende Zeilen einrücken?

 A: In Schritt 6 erstellen Sie eine`TextFragment` Objekt und weisen Sie ihm den gewünschten Text zu. Anschließend führen Sie die Initialisierung durch`TextFormattingOptions` für die`TextFragment`und spezifizieren Sie die`SubsequentLinesIndent` Wert:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### F: Wie füge ich das TextFragment zum PDF-Dokument hinzu?

 A: In Schritt 7 fügen Sie das hinzu`TextFragment` Objekt (`text`) zur Absatzsammlung der Seite:

```csharp
page.Paragraphs.Add(text);
```

#### F: Kann ich den Vorgang für weitere Zeilen wiederholen?

 A: Ja, in Schritt 8 können Sie den Vorgang für weitere Zeilen mit demselben Einzug wiederholen, indem Sie neue erstellen`TextFragment` Objekte und fügt sie der Absatzsammlung der Seite hinzu.

#### F: Wie speichere ich das resultierende PDF-Dokument?

 A: Nachdem Sie den Text mit dem Einzug nachfolgender Zeilen hinzugefügt haben, verwenden Sie die`Save` Methode der`Document` Objekt zum Speichern des PDF-Dokuments:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: Durch die Befolgung dieses Tutorials haben Sie erfolgreich gelernt, wie Sie die Lesbarkeit von Text in einem PDF-Dokument verbessern, indem Sie mit Aspose.PDF für .NET nachfolgende Zeilen einrücken. Diese Technik kann für verschiedene Arten von Dokumenten und Berichten nützlich sein.