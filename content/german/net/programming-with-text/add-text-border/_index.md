---
title: Textrahmen in PDF-Datei hinzufügen
linktitle: Textrahmen in PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET einen Textrahmen in eine PDF-Datei einfügen.
type: docs
weight: 70
url: /de/net/programming-with-text/add-text-border/
---
Dieses Tutorial führt Sie durch den Prozess zum Hinzufügen eines Textrahmens in eine PDF-Datei mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die erforderlichen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer C#-Compiler muss auf Ihrem Computer installiert sein.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Einrichten des Projekts
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in der Sie den Textrahmen hinzufügen möchten, am Anfang der Datei die folgende using-Direktive hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Schritt 3: Dokumentverzeichnis festlegen
 Suchen Sie im Code nach der Zeile, die besagt:`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den Pfad zum Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Neues Dokumentobjekt erstellen
 Instanziieren Sie ein neues`Document` -Objekt, indem Sie die folgende Codezeile hinzufügen:

```csharp
Document pdfDocument = new Document();
```

## Schritt 5: Dem Dokument eine Seite hinzufügen
 Fügen Sie dem Dokument eine neue Seite hinzu, indem Sie das`Add` Methode der`Pages`Sammlung. Im bereitgestellten Code wird die neue Seite der Variablen zugewiesen`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Schritt 6: Erstellen Sie ein TextFragment
 Erstellen Sie ein`TextFragment` Objekt und geben Sie den gewünschten Text ein. Legen Sie die Position des Textfragments mit dem`Position` Eigenschaft. Im bereitgestellten Code wird der Text auf „Haupttext“ gesetzt und an (100, 600) auf der Seite positioniert.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Schritt 7: Texteigenschaften festlegen
Passen Sie die Texteigenschaften wie Schriftgröße, Schriftart, Hintergrundfarbe, Vordergrundfarbe usw. an. Im bereitgestellten Code werden Eigenschaften wie Schriftgröße, Schriftart, Hintergrundfarbe, Vordergrundfarbe und Strichfarbe für das Textfragment festgelegt.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Schritt 8: Textrahmen aktivieren
 Um den Textrahmen zu aktivieren, setzen Sie die`DrawTextRectangleBorder`Eigenschaft des Textfragments`TextState` Zu`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Schritt 9: Fügen Sie das TextFragment zur Seite hinzu
 Verwenden Sie die`TextBuilder` Klasse zum Hinzufügen der`TextFragment` Objekt zur Seite.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Schritt 10: Speichern Sie das PDF-Dokument
 Speichern Sie das PDF-Dokument mit dem`Save` Methode der`Document` Objekt. Geben Sie den Ausgabedateipfad an, den Sie in Schritt 3 festgelegt haben.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Beispielquellcode zum Hinzufügen eines Textrahmens mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Neues Dokumentobjekt erstellen
Document pdfDocument = new Document();
// Bestimmte Seite abrufen
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Textfragment erstellen
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Texteigenschaften festlegen
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Festlegen der StrokingColor-Eigenschaft zum Zeichnen eines Rahmens (Strichzeichnung) um ein Textrechteck
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Setzen Sie den Eigenschaftswert DrawTextRectangleBorder auf „true“
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Speichern des Dokuments
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Abschluss
Sie haben Ihrem PDF-Dokument mit Aspose.PDF für .NET erfolgreich einen Textrahmen hinzugefügt. Die resultierende PDF-Datei befindet sich jetzt im angegebenen Ausgabedateipfad.

### Häufig gestellte Fragen

#### F: Worauf liegt der Schwerpunkt dieses Tutorials?

A: Dieses Tutorial führt Sie durch den Prozess des Hinzufügens eines Textrahmens zu einer PDF-Datei mithilfe der Aspose.PDF für .NET-Bibliothek. Der bereitgestellte C#-Quellcode demonstriert die dafür erforderlichen Schritte.

#### F: Welche Namespaces muss ich für dieses Tutorial importieren?

A: Importieren Sie in der Codedatei, in der Sie den Textrahmen hinzufügen möchten, am Anfang der Datei die folgenden Namespaces:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### F: Wie gebe ich das Dokumentverzeichnis an?

 A: Suchen Sie im Code die Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie erstelle ich ein Dokumentobjekt?

 A: In Schritt 4 instanziieren Sie eine neue`Document` Objekt mit der folgenden Codezeile:

```csharp
Document pdfDocument = new Document();
```

#### F: Wie füge ich dem Dokument eine Seite hinzu?

 A: In Schritt 5 fügen Sie dem Dokument eine neue Seite hinzu, indem Sie`Add` Methode der`Pages` Sammlung:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### F: Wie erstelle ich ein TextFragment und lege seine Position fest?

 A: In Schritt 6 erstellen Sie eine`TextFragment`Objekt und legen Sie seine Position auf der Seite mit dem`Position` Eigentum:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### F: Wie kann ich die Texteigenschaften, einschließlich des Textrahmens, anpassen?

A: In Schritt 7 passen Sie verschiedene Texteigenschaften wie Schriftgröße, Schriftart, Hintergrundfarbe, Vordergrundfarbe und Textrand an:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### F: Wie füge ich das TextFragment zum PDF-Dokument hinzu?

 A: In Schritt 9 verwenden Sie die`TextBuilder` Klasse zum Hinzufügen der`TextFragment` Einspruch gegen die Seite erheben:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### F: Wie speichere ich das resultierende PDF-Dokument?

 A: Nachdem Sie den Text mit einem Rahmen hinzugefügt haben, verwenden Sie die`Save` Methode der`Document` Objekt zum Speichern des PDF-Dokuments:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: In diesem Tutorial haben Sie erfolgreich gelernt, wie Sie Ihr PDF-Dokument durch Hinzufügen eines Textrahmens mit Aspose.PDF für .NET verbessern können. Dies kann besonders nützlich sein, um bestimmte Textinhalte in Ihren PDF-Dateien hervorzuheben.