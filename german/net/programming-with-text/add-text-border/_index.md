---
title: Textrahmen hinzufügen
linktitle: Textrahmen hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET einen Textrahmen zu einem PDF-Dokument hinzufügen.
type: docs
weight: 70
url: /de/net/programming-with-text/add-text-border/
---

Dieses Tutorial führt Sie durch den Prozess des Hinzufügens eines Textrahmens mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer auf Ihrem Computer installierter C#-Compiler.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Richten Sie das Projekt ein
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in der Sie den Textrahmen hinzufügen möchten, die folgende using-Anweisung oben in der Datei hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Schritt 3: Legen Sie das Dokumentverzeichnis fest
 Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Erstellen Sie ein neues Dokumentobjekt
 Instanziieren Sie eine neue`Document` Objekt durch Hinzufügen der folgenden Codezeile:

```csharp
Document pdfDocument = new Document();
```

## Schritt 5: Fügen Sie dem Dokument eine Seite hinzu
 Fügen Sie dem Dokument eine neue Seite hinzu, indem Sie verwenden`Add` Methode der`Pages` Sammlung. Im bereitgestellten Code wird die neue Seite der Variablen zugewiesen`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Schritt 6: Erstellen Sie ein TextFragment
 Ein ... kreieren`TextFragment` widersprechen und den gewünschten Text angeben. Legen Sie die Position des Textfragments mit fest`Position` Eigentum. Im bereitgestellten Code wird der Text auf „Haupttext“ gesetzt und bei (100, 600) auf der Seite positioniert.

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
 Um den Textrand zu aktivieren, legen Sie fest`DrawTextRectangleBorder` Eigenschaft des Textfragments`TextState` Zu`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Schritt 9: Fügen Sie das TextFragment zur Seite hinzu
 Benutzen Sie die`TextBuilder` Klasse, um das hinzuzufügen`TextFragment` Einspruch gegen die Seite erheben.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Schritt 10: Speichern Sie das PDF-Dokument
 Speichern Sie das PDF-Dokument mit`Save` Methode der`Document` Objekt. Geben Sie den Ausgabedateipfad an, den Sie in Schritt 3 festgelegt haben.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Beispielquellcode für „Textrahmen hinzufügen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Neues Dokumentobjekt erstellen
Document pdfDocument = new Document();
// Holen Sie sich eine bestimmte Seite
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Textfragment erstellen
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Texteigenschaften festlegen
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Legen Sie die Eigenschaft StrokingColor fest, um einen Rahmen (Strich) um das Textrechteck zu zeichnen
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Legen Sie den Eigenschaftswert „DrawTextRectangleBorder“ auf „true“ fest
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Speichern Sie das Dokument
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Abschluss
Sie haben mit Aspose.PDF für .NET erfolgreich einen Textrahmen zu Ihrem PDF-Dokument hinzugefügt. Die resultierende PDF-Datei befindet sich nun im angegebenen Ausgabedateipfad.