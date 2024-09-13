---
title: Einrückung nachfolgender Zeilen in PDF-Datei hinzufügen
linktitle: Einrückung nachfolgender Zeilen in PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET dem Text in einer PDF-Datei Einrückungen für nachfolgende Zeilen hinzufügen.
type: docs
weight: 60
url: /de/net/programming-with-text/add-subsequent-lines-indent/
---
Dieses Tutorial führt Sie durch den Prozess zum Hinzufügen von Zeileneinzügen zu Text in PDF-Dateien mithilfe von Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die erforderlichen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer C#-Compiler muss auf Ihrem Computer installiert sein.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Einrichten des Projekts
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in der Sie nachfolgenden Zeilen Einrückungen hinzufügen möchten, am Anfang der Datei die folgende using-Direktive hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Schritt 3: Dokumentverzeichnis festlegen
 Suchen Sie im Code nach der Zeile, die besagt:`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den Pfad zum Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Neues Dokumentobjekt erstellen
 Instanziieren Sie ein neues`Document` -Objekt, indem Sie die folgende Codezeile hinzufügen:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Schritt 5: Dem Dokument eine Seite hinzufügen
 Fügen Sie dem Dokument eine neue Seite hinzu, indem Sie das`Add` Methode der`Pages` Sammlung. Im bereitgestellten Code wird die neue Seite der Variablen zugewiesen`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Schritt 6: Erstellen Sie ein TextFragment mit Einrückung nachfolgender Zeilen
 Instanziieren Sie einen`TextFragment` Objekt und geben Sie den gewünschten Text ein. Im bereitgestellten Code wird der Text der Variablen zugewiesen`text` . Dann initialisieren`TextFormattingOptions` für die`TextFragment` und geben Sie den`SubsequentLinesIndent` Wert.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Schritt 7: Fügen Sie das TextFragment zur Seite hinzu
 Fügen Sie den`TextFragment` Objekt zur Absatzsammlung der Seite.

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
 Speichern Sie das PDF-Dokument mit dem`Save` Methode der`Document` Objekt. Geben Sie den Ausgabedateipfad an.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Beispielquellcode zum Hinzufügen nachfolgender Zeileneinzüge mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Neues Dokumentobjekt erstellen
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
//Initialisieren Sie TextFormattingOptions für das Textfragment und geben Sie den Wert SubsequentLinesIndent an.
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
Sie haben mit Aspose.PDF für .NET erfolgreich nachfolgende Zeilen zum Text eingerückt. Die resultierende PDF-Datei befindet sich jetzt im angegebenen Ausgabedateipfad.

### Häufig gestellte Fragen

#### F: Worauf liegt der Schwerpunkt dieses Tutorials?

A: Dieses Tutorial bietet eine umfassende Anleitung zum Hinzufügen von Einzügen für nachfolgende Zeilen zu Text in einer PDF-Datei mithilfe der Aspose.PDF für .NET-Bibliothek. Es enthält C#-Quellcodebeispiele, um die hierfür erforderlichen Schritte zu veranschaulichen.

#### F: Welche Namespaces muss ich für dieses Tutorial importieren?

A: Importieren Sie in der Codedatei, in der Sie nachfolgende Zeilen einrücken möchten, am Anfang der Datei die folgenden Namespaces:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### F: Wie gebe ich das Dokumentverzeichnis an?

 A: Suchen Sie im Code die Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie erstelle ich ein Dokumentobjekt?

 A: In Schritt 4 instanziieren Sie eine neue`Document` Objekt mit der folgenden Codezeile:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### F: Wie füge ich dem Dokument eine Seite hinzu?

 A: In Schritt 5 fügen Sie dem Dokument eine neue Seite hinzu, indem Sie`Add` Methode der`Pages` Sammlung:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### F: Wie kann ich dem Text Einzüge für nachfolgende Zeilen hinzufügen?

 A: In Schritt 6 erstellen Sie eine`TextFragment` Objekt und weisen Sie ihm den gewünschten Text zu. Anschließend initialisieren Sie`TextFormattingOptions` für die`TextFragment` und geben Sie den`SubsequentLinesIndent` Wert:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### F: Wie füge ich das TextFragment zum PDF-Dokument hinzu?

 A: In Schritt 7 fügen Sie die`TextFragment` Objekt (`text`) zur Absatzsammlung der Seite:

```csharp
page.Paragraphs.Add(text);
```

#### F: Kann ich den Vorgang für weitere Zeilen wiederholen?

A: Ja, in Schritt 8 können Sie den Vorgang für weitere Zeilen mit demselben Einzug wiederholen, indem Sie neue`TextFragment` Objekte und fügt sie der Absatzsammlung der Seite hinzu.

#### F: Wie speichere ich das resultierende PDF-Dokument?

 A: Nachdem Sie den Text mit Einzug für nachfolgende Zeilen hinzugefügt haben, verwenden Sie die`Save` Methode der`Document` Objekt zum Speichern des PDF-Dokuments:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: In diesem Tutorial haben Sie erfolgreich gelernt, wie Sie die Lesbarkeit von Text in einem PDF-Dokument verbessern können, indem Sie mit Aspose.PDF für .NET Einrückungen für nachfolgende Zeilen hinzufügen. Diese Technik kann für verschiedene Arten von Dokumenten und Berichten nützlich sein.