---
title: Textfeld
linktitle: Textfeld
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Textfeld in einem PDF-Dokument erstellen.
type: docs
weight: 290
url: /de/net/programming-with-forms/text-box/
---
In dieser Anleitung erklären wir Ihnen Schritt für Schritt, wie Sie mit der Aspose.PDF-Bibliothek für .NET ein Textfeld in einem PDF-Dokument erstellen. Wir zeigen Ihnen, wie Sie das Dokument öffnen, das Textfeld erstellen, seine Eigenschaften anpassen und das bearbeitete PDF speichern.

## Schritt 1: Konfigurieren des Dokumentenverzeichnisses

 Der erste Schritt besteht darin, das Dokumentverzeichnis zu konfigurieren, in dem sich die PDF-Datei befindet, an der Sie arbeiten möchten. Du kannst den ... benutzen`dataDir` Variable, um den Verzeichnispfad anzugeben.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

## Schritt 2: Öffnen des PDF-Dokuments

In diesem Schritt öffnen wir das PDF-Dokument mit`Document` Klasse von Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Stellen Sie sicher, dass die PDF-Datei im angegebenen Dokumentenverzeichnis vorhanden ist.

## Schritt 3: Erstellen des Textfeldes

 Wir erstellen ein Textfeld mit dem`TextBoxField` Klasse. Mit können Sie Positionskoordinaten und Feldgröße angeben`Rectangle` Klasse.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Passen Sie die Koordinaten, die Größe, den Teilnamen und den Textfeldwert nach Bedarf an.

## Schritt 4: Passen Sie die Eigenschaften des Textfelds an

In diesem Schritt passen wir die Textfeldeigenschaften wie Rahmen, Farbe usw. an.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Passen Sie die Textfeldeigenschaften nach Ihren Wünschen an.

## Schritt 5: Hinzufügen des Feldes zum Dokument

Nachdem wir nun das Textfeld erstellt und konfiguriert haben, können wir es dem PDF-Dokument hinzufügen.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Schritt 6: Speichern des geänderten PDF

 Schließlich können wir das geänderte PDF mit speichern`Save` Methode der`Document` Klasse.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Geben Sie unbedingt den vollständigen Pfad und Dateinamen für das bearbeitete PDF an.

### Beispielquellcode für Text Box mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// Erstellen Sie ein Feld
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
//TextBoxField.Border = neuer Rand(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Fügen Sie dem Dokument ein Feld hinzu
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Geändertes PDF speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Abschluss

In dieser Anleitung haben wir gelernt, wie man mit der Aspose.PDF-Bibliothek für .NET ein Textfeld in einem PDF-Dokument erstellt. Indem Sie die beschriebenen Schritte befolgen, können Sie die Eigenschaften des Textfelds anpassen und es nach Bedarf zum Dokument hinzufügen. Erkunden Sie die Funktionen von Aspose.PDF für .NET weiter, um die Möglichkeiten der Bearbeitung von PDF-Dateien zu erweitern.

### FAQs

#### F: Kann ich Aspose.PDF für .NET verwenden, um mehrere Textfelder in einem einzigen PDF-Dokument zu erstellen?

A: Ja, Sie können mit Aspose.PDF für .NET mehrere Textfelder in einem einzigen PDF-Dokument erstellen. Wiederholen Sie einfach den Vorgang des Erstellens und Anpassens von Textfeldern für jede gewünschte Stelle im Dokument.

#### F: Wie kann ich das Erscheinungsbild des Textfelds anpassen, z. B. Schriftgröße und Farbe?

A: Sie können das Erscheinungsbild des Textfelds anpassen, indem Sie seine Eigenschaften anpassen, z. B. Schriftgröße, Schriftstil, Farbe, Rahmenstil, Hintergrundfarbe und mehr. Im bereitgestellten Beispielquellcode werden die Rahmenbreite, das Rahmenstrichmuster und die Textfarbe angepasst.

#### F: Ist es möglich, den vom Benutzer eingegebenen Text aus dem erstellten Textfeld zu extrahieren?

A: Ja, Sie können den vom Benutzer eingegebenen Text aus dem erstellten Textfeld extrahieren. Nachdem Benutzer das Textfeld im PDF-Dokument ausgefüllt haben, können Sie den Feldwert mithilfe von Aspose.PDF für .NET programmgesteuert abrufen.

#### F: Kann ich Textfelder zu einem vorhandenen PDF-Dokument hinzufügen, ohne ein neues zu erstellen?

A: Ja, Sie können Textfelder zu einem vorhandenen PDF-Dokument hinzufügen, ohne ein neues zu erstellen. Aspose.PDF für .NET bietet die Möglichkeit, vorhandene PDF-Dokumente zu ändern, einschließlich des Hinzufügens von Textfeldern, Kontrollkästchen und anderen Formularelementen.

#### F: Unterstützt Aspose.PDF für .NET andere Arten von Formularfeldern, z. B. Kontrollkästchen und Optionsfelder?

A: Ja, Aspose.PDF für .NET unterstützt verschiedene Arten von Formularfeldern, darunter Kontrollkästchen, Optionsfelder, Dropdown-Listen und mehr. Sie können die Bibliothek verwenden, um mit verschiedenen Arten von Formularelementen in PDF-Dokumenten zu arbeiten.