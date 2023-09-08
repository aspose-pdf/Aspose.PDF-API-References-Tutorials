---
title: Erstellen Sie zunächst eine mehrschichtige PDF-Datei
linktitle: Erstellen Sie zunächst ein mehrschichtiges PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine mehrschichtige PDF-Datei mit dem ersten Ansatz erstellen. Fügen Sie Text, Bilder und mehr hinzu, um Ihre PDFs zu verbessern.
type: docs
weight: 70
url: /de/net/programming-with-document/createmultilayerpdffirstapproach/
---
In diesem Tutorial führen wir Sie durch den Prozess der Erstellung einer mehrschichtigen PDF-Datei mit dem ersten Ansatz mit Aspose.PDF für .NET. Mit diesem Ansatz können Sie Ihrer PDF-Datei mehrere Ebenen hinzufügen. Befolgen Sie die nachstehende Schritt-für-Schritt-Anleitung:

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

## Abschluss

In diesem Tutorial haben wir gezeigt, wie man mit dem ersten Ansatz mit Aspose.PDF für .NET ein mehrschichtiges PDF-Dokument erstellt. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Quellcode verwenden, können Sie ganz einfach mehrere Ebenen zu Ihren PDF-Dokumenten hinzufügen. Ebenen in einem PDF-Dokument bieten mehr Flexibilität und Interaktivität, sodass Sie dynamische und individuelle Inhalte erstellen können. Aspose.PDF für .NET bietet eine zuverlässige und effiziente Lösung für die Arbeit mit PDFs in .NET-Anwendungen und ermöglicht Ihnen die einfache Erstellung anspruchsvoller und interaktiver PDF-Dokumente.

### Häufig gestellte Fragen zum ersten Ansatz zum Erstellen einer mehrschichtigen PDF-Datei

#### F: Was ist ein mehrschichtiges PDF-Dokument?

A: Ein mehrschichtiges PDF-Dokument, auch als geschichtetes PDF bezeichnet, enthält mehrere Inhaltsebenen, deren Sichtbarkeit und Deckkraft individuell gesteuert werden können. Mithilfe von Ebenen in einem PDF-Dokument können Benutzer bestimmte Inhaltselemente gezielt ein- oder ausblenden.

#### F: Wie kann ich mit Aspose.PDF für .NET Ebenen zu einem PDF-Dokument hinzufügen?

A: Sie können mit Aspose.PDF für .NET Ebenen zu einem PDF-Dokument hinzufügen, indem Sie schwebende Felder erstellen und diesen Feldern Inhaltselemente wie Text und Bilder hinzufügen. Jedes schwebende Feld kann eine separate Ebene darstellen und Sie können deren Sichtbarkeit und Positionierung auf der Seite steuern.

#### F: Welche Vorteile bietet die Erstellung mehrschichtiger PDFs?

A: Das Erstellen mehrschichtiger PDFs erhöht die Flexibilität und Interaktivität des Dokuments. Mithilfe von Ebenen können Sie Inhaltselemente effektiv organisieren und verwalten, wodurch es einfacher wird, deren Anzeige zu steuern und interaktive Dokumente zu erstellen.

#### F: Kann ich einer einzelnen Seite im PDF-Dokument mehrere Ebenen hinzufügen?

A: Ja, Sie können einer einzelnen Seite im PDF-Dokument mehrere Ebenen hinzufügen, indem Sie mehrere schwebende Felder erstellen und positionieren. Jede schwebende Box kann eine separate Ebene darstellen, und Sie können jeder Box entsprechend Inhaltselemente hinzufügen.

#### F: Ist Aspose.PDF für .NET für professionelle Projekte mit mehrschichtigen PDFs geeignet?

A: Absolut, Aspose.PDF für .NET ist eine robuste und funktionsreiche Bibliothek, die in professionellen Projekten zur PDF-Bearbeitung, einschließlich der Erstellung mehrschichtiger PDFs, häufig verwendet wird. Es bietet umfassende Funktionalitäten für die Arbeit mit PDF-Dokumenten in .NET-Anwendungen.