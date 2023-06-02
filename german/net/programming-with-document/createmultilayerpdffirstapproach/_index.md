---
title: Erstellen Sie zunächst ein mehrschichtiges PDF
linktitle: Erstellen Sie zunächst ein mehrschichtiges PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mehrschichtige PDF-Dokumente mit dem ersten Ansatz mit Aspose.PDF für .NET erstellen. Fügen Sie Text, Bilder und mehr hinzu, um Ihre PDFs zu verbessern.
type: docs
weight: 70
url: /de/net/programming-with-document/createmultilayerpdffirstapproach/
---

In diesem Tutorial führen wir Sie durch den Prozess der Erstellung einer mehrschichtigen PDF-Datei mit dem ersten Ansatz mit Aspose.PDF für .NET. Mit diesem Ansatz können Sie Ihrem PDF-Dokument mehrere Ebenen hinzufügen. Befolgen Sie die nachstehende Schritt-für-Schritt-Anleitung:

## Schritt 1: Initialisieren Sie das PDF-Dokument

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```

## Schritt 2: Fügen Sie dem Dokument eine neue Seite hinzu

```csharp
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
```

## Schritt 3: Fügen Sie der Seite ein Textfragment hinzu

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);
```

## Schritt 4: Passen Sie das Textfragment an

```csharp
t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;
```

## Schritt 5: Fügen Sie der Seite ein Bild hinzu

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
```

## Schritt 6: Fügen Sie der Seite ein schwebendes Feld hinzu

```csharp
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);
```

## Schritt 7: Speichern Sie das resultierende PDF-Dokument

```csharp
pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

Glückwunsch! Sie haben mit dem ersten Ansatz mit Aspose.PDF für .NET erfolgreich ein mehrschichtiges PDF-Dokument erstellt.

### Beispielquellcode für den ersten Ansatz zum Erstellen mehrschichtiger PDFs mit Aspose.PDF für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);

t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;

Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);

pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

Jetzt können Sie mit dem ersten Ansatz mit Aspose.PDF für .NET mehrschichtige PDF-Dokumente erstellen.
