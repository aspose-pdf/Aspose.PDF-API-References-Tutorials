---
title: Benutzerdefinierte Tabstopps in PDF-Dateien
linktitle: Benutzerdefinierte Tabstopps in PDF-Dateien
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET benutzerdefinierte Tabstopps in einer PDF-Datei erstellen.
type: docs
weight: 120
url: /de/net/programming-with-text/custom-tab-stops/
---

Dieses Tutorial führt Sie durch den Prozess der Erstellung benutzerdefinierter Tabstopps in einer PDF-Datei mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer auf Ihrem Computer installierter C#-Compiler.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Richten Sie das Projekt ein
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in der Sie benutzerdefinierte Tabstopps erstellen möchten, die folgenden using-Anweisungen am Anfang der Datei hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Schritt 3: Legen Sie das Dokumentverzeichnis fest
 Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Erstellen Sie eine neue Dokumentinstanz
 Instanziieren Sie eine neue`Document` Objekt durch Hinzufügen der folgenden Codezeile:

```csharp
Document _pdfdocument = new Document();
```

## Schritt 5: Fügen Sie dem Dokument eine Seite hinzu
 Fügen Sie mit dem eine neue Seite zum Dokument hinzu`Add` Methode der`Pages`Sammlung. Im bereitgestellten Code wird die neue Seite der Variablen zugewiesen`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Schritt 6: Erstellen Sie benutzerdefinierte Tabstopps
 Ein ... kreieren`TabStops` Objekt und fügen Sie ihm benutzerdefinierte Tabstopps hinzu. Legen Sie den Ausrichtungstyp und den Führungslinientyp für jeden Tabstopp fest.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## Schritt 7: Erstellen Sie Textfragmente mit Tabstopps
 Erstellen`TextFragment` Objekte und übergeben die benutzerdefinierten Tabstopps an sie. Verwenden Sie die Sonderzeichen`#$TAB` um die Tabstopps im Text anzuzeigen.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## Schritt 8: Speichern Sie das PDF-Dokument
 Speichern Sie das PDF-Dokument mit`Save` Methode der`Document` Objekt.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Beispielquellcode für benutzerdefinierte Tabstopps mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Abschluss
Sie haben mit Aspose.PDF für .NET erfolgreich ein PDF-Dokument mit benutzerdefinierten Tabstopps erstellt. Die resultierende PDF-Datei befindet sich nun im angegebenen Ausgabedateipfad.

### FAQs

#### F: Was ist der Schwerpunkt dieses Tutorials?

A: Der Schwerpunkt dieses Tutorials liegt darauf, Sie durch den Prozess der Erstellung benutzerdefinierter Tabstopps in einer PDF-Datei mithilfe der Aspose.PDF für .NET-Bibliothek zu führen. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte, um dies zu erreichen.

#### F: Welche Namespaces sollte ich für dieses Tutorial importieren?

A: Importieren Sie in der Codedatei, in der Sie benutzerdefinierte Tabstopps erstellen möchten, die folgenden Namespaces am Anfang der Datei:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### F: Wie lege ich das Dokumentenverzeichnis fest?

 A: Suchen Sie im Code die Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie erstelle ich eine neue Dokumentinstanz?

 A: In Schritt 4 instanziieren Sie eine neue`Document` Objekt mithilfe des bereitgestellten Codes.

#### F: Wie füge ich dem Dokument eine Seite hinzu?

 A: In Schritt 5 fügen Sie dem Dokument eine neue Seite hinzu`Add` Methode der`Pages` Sammlung.

#### F: Wie erstelle ich benutzerdefinierte Tabstopps?

 A: In Schritt 6 erstellen Sie eine`TabStops` Objekt und fügen Sie ihm benutzerdefinierte Tabstopps hinzu. Sie legen außerdem Ausrichtungs- und Führungstypen für jeden Tabstopp fest.

#### F: Wie erstelle ich Textfragmente mit Tabstopps?

 A: In Schritt 7 erstellen Sie`TextFragment` Objekte und übergeben die benutzerdefinierten Tabstopps an sie. Sie verwenden die Sonderzeichen`#$TAB` um die Tabstopps im Text anzuzeigen.

#### F: Wie speichere ich das PDF-Dokument?

 A: In Schritt 8 speichern Sie das PDF-Dokument mit`Save` Methode der`Document` Objekt.

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: Durch die Befolgung dieses Tutorials haben Sie gelernt, wie Sie mit Aspose.PDF für .NET ein PDF-Dokument mit benutzerdefinierten Tabstopps erstellen. Dies kann nützlich sein, um Text strukturiert zu organisieren und auszurichten.