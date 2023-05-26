---
title: Erlauben Sie die Wiederverwendung von Seiteninhalten
linktitle: Erlauben Sie die Wiederverwendung von Seiteninhalten
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie PDFs optimieren, indem Sie die Funktion „Wiederverwendung von Seiteninhalten zulassen“ mit Aspose.PDF für .NET aktivieren. Reduzieren Sie die Dateigröße und verbessern Sie die Leistung.
type: docs
weight: 50
url: /de/net/programming-with-document/allowresusepagecontent/
---

In diesem Tutorial erklären wir, wie Sie die Funktion „Wiederverwendung von Seiteninhalt zulassen“ mit Aspose.PDF für .NET aktivieren. Diese Funktion optimiert das PDF-Dokument durch die Wiederverwendung von Seiteninhalten, reduziert die Dateigröße und verbessert die Leistung. Befolgen Sie die nachstehende Schritt-für-Schritt-Anleitung:

## Schritt 1: Laden Sie das PDF-Dokument

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Schritt 2: Legen Sie die Option AllowReusePageContent fest

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## Schritt 3: Optimieren Sie das PDF-Dokument

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Schritt 4: Speichern Sie das aktualisierte Dokument

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Schritt 5: Überprüfen Sie die Reduzierung der Dateigröße

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Glückwunsch! Sie haben die Wiederverwendung von Seiteninhalten in Ihrem PDF-Dokument erfolgreich zugelassen.

### Beispielquellcode zum Ermöglichen der Wiederverwendung von Seiteninhalten mit Aspose.PDF für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// Legen Sie die Option „AllowReusePageContent“ fest
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};

Console.WriteLine("Start");

// Optimieren Sie PDF-Dokumente mit OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("Finished");

var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

Jetzt können Sie Ihre PDF-Dokumente effektiv optimieren, indem Sie die Wiederverwendung von Seiteninhalten ermöglichen.
