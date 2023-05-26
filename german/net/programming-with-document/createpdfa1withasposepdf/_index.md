---
title: Erstellen Sie PDF A1 mit Aspose PDF
linktitle: Erstellen Sie PDF A1 mit Aspose PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein PDF-A1-Dokument erstellen. Schritt-für-Schritt-Anleitung mit C#-Quellcode. PDFs effizient optimieren.
type: docs
weight: 90
url: /de/net/programming-with-document/createpdfa1withasposepdf/
---

In dieser Schritt-für-Schritt-Anleitung erklären wir Ihnen, wie Sie mit Aspose.PDF für .NET ein PDF-A1-Dokument erstellen. Wir stellen Ihnen den notwendigen C#-Quellcode und Anweisungen zur Durchführung dieser Aufgabe zur Verfügung.

## Schritt 1: Variablen definieren und Namespaces importieren

 Definieren Sie zunächst die Variable`dataDir` um das Verzeichnis darzustellen, in dem Ihre Dokumente gespeichert sind. Dies wird verwendet, um den Pfad der Ausgabedatei anzugeben.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Erstellen Sie als Nächstes eine neue Instanz von`Document` Klasse von Aspose.PDF.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Schritt 2: Inhalte zum PDF hinzufügen

In diesem Schritt fügen wir dem PDF-Dokument eine Seite hinzu und fügen ein Textfragment mit dem Text „Hello World!“ ein.

```csharp
pdf1.Pages.Add().Paragraphs.Add(new TextFragment("Hello World!"));
```

## Schritt 3: Speichern Sie die PDF-Datei in einem Speicherstream

Um das PDF in das PDF/A1-Format zu konvertieren, müssen wir es in einem Speicherstream speichern.

```csharp
MemoryStream ms = new MemoryStream();
pdf1.Save(ms);
```

## Schritt 4: Konvertieren Sie das PDF in das PDF/A1-Format

 Jetzt konvertieren wir das PDF mit in das PDF/A1-Format`Convert` Methode der`Document` Klasse. Wir übergeben einen neuen Speicherstream als Ausgabestream und geben den an`PdfFormat.PDF_A_1A` Format.

```csharp
pdf1.Convert(new MemoryStream(), PdfFormat.PDF_A_1A, ConvertErrorAction.Delete);
```

## Schritt 5: Speichern Sie das konvertierte PDF

Speichern Sie abschließend das konvertierte PDF im angegebenen Verzeichnis.

```csharp
pdf1.Save(dataDir + "CreatePdfA1_out.pdf");
```

### Beispielquellcode für „PDF A1 erstellen“ mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Fügen Sie dem PDF-Dokument eine Seite hinzu
pdf1.Pages.Add().Paragraphs.Add(new TextFragment("Hello World!"));
MemoryStream ms = new MemoryStream();
// Speichern Sie das Dokument
pdf1.Save(ms);
pdf1.Convert(new MemoryStream(), PdfFormat.PDF_A_1A, ConvertErrorAction.Delete);
pdf1.Save(dataDir + "CreatePdfA1_out.pdf");
```

Wenn Sie diese Schritte befolgen und den bereitgestellten Quellcode verwenden, können Sie mit Aspose.PDF für .NET ein PDF-A1-Dokument erstellen.

Denken Sie daran, das „IHR DOKUMENTVERZEICHNIS“ mit dem entsprechenden Verzeichnispfad anzupassen, in dem Sie die Ausgabedatei speichern möchten.


