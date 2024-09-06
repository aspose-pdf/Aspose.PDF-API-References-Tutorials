---
title: Textfeld
linktitle: Textfeld
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Textfeld in einem PDF-Dokument erstellen.
type: docs
weight: 290
url: /de/net/programming-with-forms/text-box/
---
In dieser Anleitung erklären wir Schritt für Schritt, wie Sie mit der Aspose.PDF-Bibliothek für .NET ein Textfeld in einem PDF-Dokument erstellen. Wir zeigen Ihnen, wie Sie das Dokument öffnen, das Textfeld erstellen, seine Eigenschaften anpassen und das bearbeitete PDF speichern.

## Schritt 1: Konfigurieren des Dokumentverzeichnisses

 Der erste Schritt besteht darin, das Dokumentverzeichnis zu konfigurieren, in dem sich die PDF-Datei befindet, die Sie bearbeiten möchten. Sie können das`dataDir` Variable zum Angeben des Verzeichnispfads.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Ersetzen Sie unbedingt`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 2: Öffnen des PDF-Dokuments

 In diesem Schritt öffnen wir das PDF-Dokument mit dem`Document` Klasse von Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Stellen Sie sicher, dass die PDF-Datei im angegebenen Dokumentenverzeichnis vorhanden ist.

## Schritt 3: Textfeld erstellen

 Wir erstellen ein Textfeld mit dem`TextBoxField` Klasse. Sie können Positionskoordinaten und Feldgröße angeben mit dem`Rectangle` Klasse.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Passen Sie die Koordinaten, die Größe, den Teilnamen und den Textfeldwert nach Bedarf an.

## Schritt 4: Textfeldeigenschaften anpassen

In diesem Schritt passen wir die Eigenschaften des Textfelds wie Rahmen, Farbe usw. an.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Passen Sie die Textfeldeigenschaften Ihren Wünschen an.

## Schritt 5: Hinzufügen des Feldes zum Dokument

Nachdem wir nun das Textfeld erstellt und konfiguriert haben, können wir es dem PDF-Dokument hinzufügen.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Schritt 6: Speichern der geänderten PDF

 Abschließend können wir das geänderte PDF speichern mit dem`Save` Methode der`Document` Klasse.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Geben Sie unbedingt den vollständigen Pfad und Dateinamen für die bearbeitete PDF-Datei an.

### Beispiel-Quellcode für Textfeld mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "TextField.pdf");
//Erstellen eines Felds
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
// TextBoxField.Border = neuer Rahmen(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Feld zum Dokument hinzufügen
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Modifiziertes PDF speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Abschluss

In dieser Anleitung haben wir gelernt, wie man mit der Aspose.PDF-Bibliothek für .NET ein Textfeld in einem PDF-Dokument erstellt. Indem Sie die beschriebenen Schritte befolgen, können Sie die Eigenschaften des Textfelds anpassen und es nach Bedarf zum Dokument hinzufügen. Erkunden Sie die Funktionen von Aspose.PDF für .NET weiter, um die Möglichkeiten zur Bearbeitung von PDF-Dateien zu erweitern.

### Häufig gestellte Fragen

#### F: Kann ich Aspose.PDF für .NET verwenden, um mehrere Textfelder in einem einzigen PDF-Dokument zu erstellen?

A: Ja, Sie können mit Aspose.PDF für .NET mehrere Textfelder in einem einzigen PDF-Dokument erstellen. Wiederholen Sie einfach den Vorgang zum Erstellen und Anpassen von Textfeldern für jede gewünschte Stelle im Dokument.

#### F: Wie kann ich das Erscheinungsbild des Textfelds, beispielsweise Schriftgröße und Farbe, anpassen?

A: Sie können das Erscheinungsbild des Textfelds anpassen, indem Sie dessen Eigenschaften wie Schriftgröße, Schriftstil, Farbe, Rahmenstil, Hintergrundfarbe und mehr anpassen. Im bereitgestellten Beispielquellcode werden Rahmenbreite, Rahmenstrichmuster und Textfarbe angepasst.

#### F: Ist es möglich, den vom Benutzer eingegebenen Text aus dem erstellten Textfeld zu extrahieren?

A: Ja, Sie können den vom Benutzer eingegebenen Text aus dem erstellten Textfeld extrahieren. Nachdem Benutzer das Textfeld im PDF-Dokument ausgefüllt haben, können Sie den Feldwert programmgesteuert mit Aspose.PDF für .NET abrufen.

#### F: Kann ich einem vorhandenen PDF-Dokument Textfelder hinzufügen, ohne ein neues zu erstellen?

A: Ja, Sie können einem vorhandenen PDF-Dokument Textfelder hinzufügen, ohne ein neues zu erstellen. Aspose.PDF für .NET bietet die Möglichkeit, vorhandene PDF-Dokumente zu ändern, einschließlich der Hinzufügung von Textfeldern, Kontrollkästchen und anderen Formularelementen.

#### F: Unterstützt Aspose.PDF für .NET andere Arten von Formularfeldern, wie z. B. Kontrollkästchen und Optionsfelder?

A: Ja, Aspose.PDF für .NET unterstützt verschiedene Arten von Formularfeldern, darunter Kontrollkästchen, Optionsfelder, Dropdown-Listen und mehr. Sie können die Bibliothek verwenden, um mit verschiedenen Arten von Formularelementen in PDF-Dokumenten zu arbeiten.