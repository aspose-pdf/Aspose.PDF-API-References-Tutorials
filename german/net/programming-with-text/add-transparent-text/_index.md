---
title: Fügen Sie transparenten Text hinzu
linktitle: Fügen Sie transparenten Text hinzu
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET transparenten Text zu einem PDF-Dokument hinzufügen.
type: docs
weight: 100
url: /de/net/programming-with-text/add-transparent-text/
---

Dieses Tutorial führt Sie durch den Prozess des Hinzufügens von transparentem Text zu einem PDF-Dokument mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer auf Ihrem Computer installierter C#-Compiler.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Richten Sie das Projekt ein
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in der Sie transparenten Text hinzufügen möchten, am Anfang der Datei die folgenden using-Anweisungen hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Schritt 3: Legen Sie das Dokumentverzeichnis fest
 Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Erstellen Sie eine neue Dokumentinstanz
 Instanziieren Sie eine neue`Document` Objekt durch Hinzufügen der folgenden Codezeile:

```csharp
Document doc = new Document();
```

## Schritt 5: Fügen Sie dem Dokument eine Seite hinzu
 Fügen Sie dem Dokument eine neue Seite hinzu, indem Sie verwenden`Add` Methode der`Pages` Sammlung. Im bereitgestellten Code wird die neue Seite der Variablen zugewiesen`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Schritt 6: Erstellen Sie ein Graph-Objekt
 Erstelle eine neue`Graph` Objekt mit einer bestimmten Breite und Höhe.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## Schritt 7: Erstellen Sie ein Rechteck mit Transparenz
 Erstellen Sie ein Rechteck mit bestimmten Abmessungen und stellen Sie dessen Füllfarbe mithilfe von auf eine transparente Farbe ein`Color.FromRgb` Methode.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## Schritt 8: Fügen Sie das Graph-Objekt zur Seite hinzu
 Ergänzen Sie die`Graph` Einspruch gegen die Absätze-Sammlung der Seite einlegen.

```csharp
page.Paragraphs.Add(canvas);
```

## Schritt 9: Position für das Graph-Objekt festlegen
 Stellen Sie die ein`IsChangePosition` Eigentum der`Graph` widersprechen`false` um zu verhindern, dass es seine Position verändert.

```csharp
canvas. IsChangePosition = false;
```

## Schritt 10: Erstellen Sie ein TextFragment mit Transparenz
 Ein ... kreieren`TextFragment` Objekt und setzen Sie dessen Inhalt auf den gewünschten Text. Stellen Sie die ein`ForegroundColor` Eigentum der`TextState` zu einer Farbe mit Transparenz mit dem`Color.FromArgb` Methode.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## Schritt 11: Speichern Sie das PDF-Dokument
 Speichern Sie das PDF-Dokument mit`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### Beispielquellcode für „Transparenten Text hinzufügen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentinstanz erstellen
Document doc = new Document();
// Erstellen Sie eine seitenweise Sammlung von PDF-Dateien
Aspose.Pdf.Page page = doc.Pages.Add();
// Erstellen Sie ein Diagrammobjekt
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Erstellen Sie eine rechteckige Instanz mit bestimmten Abmessungen
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// Erstellen Sie ein Farbobjekt aus dem Alpha-Farbkanal
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Fügen Sie der Formensammlung des Graph-Objekts ein Rechteck hinzu
canvas.Shapes.Add(rect);
// Diagrammobjekt zur Absatzsammlung des Seitenobjekts hinzufügen
page.Paragraphs.Add(canvas);
// Stellen Sie den Wert so ein, dass sich die Position des Diagrammobjekts nicht ändert
canvas.IsChangePosition = false;
// Erstellen Sie eine TextFragment-Instanz mit Beispielwert
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// Erstellen Sie ein Farbobjekt aus dem Alpha-Kanal
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// Legen Sie Farbinformationen für die Textinstanz fest
text.TextState.ForegroundColor = color;
// Fügen Sie Text zur Absatzsammlung der Seiteninstanz hinzu
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## Abschluss
Sie haben mit Aspose.PDF für .NET erfolgreich transparenten Text zu Ihrem PDF-Dokument hinzugefügt. Die resultierende PDF-Datei befindet sich nun im angegebenen Ausgabedateipfad.