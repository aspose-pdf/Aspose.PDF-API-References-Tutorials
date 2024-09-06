---
title: PDF-Formularfeld ausfüllen
linktitle: PDF-Formularfeld ausfüllen
second_title: Aspose.PDF für .NET API-Referenz
description: Füllen Sie Formularfelder in Ihren PDF-Dokumenten ganz einfach mit Aspose.PDF für .NET aus.
type: docs
weight: 80
url: /de/net/programming-with-forms/fill-form-field/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie ein Formularfeld mit Aspose.PDF für .NET ausfüllen. Wir erklären Ihnen den C#-Quellcode Schritt für Schritt, um Sie durch diesen Prozess zu führen.

## Schritt 1: Vorbereitung

Stellen Sie zunächst sicher, dass Sie die erforderlichen Bibliotheken importiert haben, und legen Sie den Pfad zum Dokumentverzeichnis fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

Öffnen Sie das vorhandene PDF-Dokument:

```csharp
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
```

## Schritt 3: Feld abrufen

Holen Sie sich das gewünschte Formularfeld (in diesem Beispiel verwenden wir das Feld „textbox1“):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Schritt 4: Ändern des Feldwertes

Ändern Sie den Feldwert mit dem gewünschten Wert:

```csharp
textBoxField.Value = "Value to fill in the field";
```

## Schritt 5: Speichern Sie das aktualisierte Dokument

Speichern Sie das aktualisierte PDF-Dokument:

```csharp
dataDir = dataDir + "FillFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode zum Ausfüllen von Formularfeldern mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "FillFormField.pdf");
// Holen Sie sich ein Feld
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Feldwert ändern
textBoxField.Value = "Value to be filled in the field";
dataDir = dataDir + "FillFormField_out.pdf";
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field filled successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man ein Formularfeld mit Aspose.PDF für .NET ausfüllt. Indem Sie diese Schritte befolgen, können Sie mit Aspose.PDF ganz einfach Formularfeldwerte in Ihren PDF-Dokumenten ändern.

### Häufig gestellte Fragen

#### F: Kann ich mit Aspose.PDF für .NET mehrere Formularfelder in einem PDF-Dokument ausfüllen?

A: Ja, Sie können mit Aspose.PDF für .NET mehrere Formularfelder in einem PDF-Dokument ausfüllen. Nach dem Öffnen des PDF-Dokuments können Sie jedes Formularfeld einzeln abrufen und seinen Wert nach Bedarf ändern.

#### F: Wie kann ich die Namen von Formularfeldern in einem PDF-Dokument finden?

 A: Um die Namen von Formularfeldern in einem PDF-Dokument zu finden, können Sie durch die`pdfDocument.Form.Fields` Sammlung. Jedes Formularfeld hat eine`FullName` Eigenschaft, die den eindeutigen Namen enthält. Sie können diese Namen verwenden, um bestimmte Formularfelder zu identifizieren und zu ändern.

#### F: Was ist, wenn das Formularfeld, das ich ausfüllen möchte, im PDF-Dokument nicht vorhanden ist?

 A: Wenn das Formularfeld, das Sie ausfüllen möchten, im PDF-Dokument nicht vorhanden ist, versuchen Sie, darauf zuzugreifen mit`pdfDocument.Form["fieldName"]`gibt null zurück. Daher ist es wichtig, sicherzustellen, dass das Formularfeld vorhanden ist, bevor Sie versuchen, es auszufüllen. Sie können bei Bedarf neue Formularfelder programmgesteuert mit Aspose.PDF für .NET hinzufügen.

#### F: Kann ich Formularfelder mit dynamischen Daten aus einer Datenbank oder einer anderen Datenquelle füllen?

A: Ja, Sie können Formularfelder mit dynamischen Daten aus einer Datenbank oder einer anderen Datenquelle füllen. Bevor Sie den Feldwert festlegen, rufen Sie die Daten aus der Quelle ab und verwenden Sie sie, um den Wert des Formularfelds entsprechend festzulegen.

#### F: Gibt es Einschränkungen beim Ausfüllen von Formularfeldern in XFA-basierten PDF-Dokumenten?

A: Das Ausfüllen von Formularfeldern in XFA-basierten (XML Forms Architecture) PDF-Dokumenten kann aufgrund der komplexen Struktur von XFA-Formularen einige Einschränkungen aufweisen. Aspose.PDF für .NET unterstützt zwar das Ausfüllen von Formularfeldern in XFA-Formularen, aber einige spezifische Formularfeldeigenschaften, die nur für XFA-Formulare gelten, werden in AcroForms möglicherweise nicht vollständig unterstützt.