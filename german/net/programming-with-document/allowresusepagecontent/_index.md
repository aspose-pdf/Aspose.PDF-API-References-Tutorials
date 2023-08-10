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

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie die Funktion „Wiederverwendung von Seiteninhalten zulassen“ mit Aspose.PDF für .NET aktivieren. Indem Sie der bereitgestellten Schritt-für-Schritt-Anleitung folgen und den C#-Quellcode verwenden, können Sie Ihre PDF-Dokumente effektiv optimieren, indem Sie die Wiederverwendung von Seiteninhalten ermöglichen. Diese Optimierung führt zu kleineren PDF-Dateien, was zu schnelleren Ladezeiten und einer verbesserten Leistung bei der Verarbeitung großer PDF-Dokumente führen kann. Aspose.PDF für .NET bietet eine robuste und benutzerfreundliche Lösung zur PDF-Optimierung, mit der Sie problemlos effiziente und qualitativ hochwertige PDF-Dateien erstellen können.

### FAQs

#### F: Welchen Zweck hat die Aktivierung der Funktion „Wiederverwendung von Seiteninhalten zulassen“ in einem PDF-Dokument?

A: Durch die Aktivierung der Funktion „Wiederverwendung von Seiteninhalten zulassen“ in einem PDF-Dokument wird die Datei durch die Wiederverwendung von Seiteninhalten optimiert, wodurch die Dateigröße reduziert und die Gesamtleistung verbessert wird. Diese Optimierung führt zu kleineren PDF-Dateien, ohne dass die Qualität des Inhalts beeinträchtigt wird.

#### F: Wie funktioniert die Funktion „Wiederverwendung von Seiteninhalten zulassen“?

A: Wenn die Funktion „Wiederverwendung von Seiteninhalten zulassen“ aktiviert ist, werden identische Seitenobjekte im PDF-Dokument gemeinsam genutzt und wiederverwendet, anstatt bei jedem Vorkommen dupliziert zu werden. Durch die gemeinsame Nutzung von Seiteninhalten wird die Gesamtdateigröße erheblich reduziert.

#### F: Kann ich die Optimierung rückgängig machen und das Originaldokument wiederherstellen?

A: Nein, sobald die Optimierung mit „Wiederverwendung von Seiteninhalten zulassen“ durchgeführt und das PDF-Dokument gespeichert wird, sind die Änderungen dauerhaft. Es empfiehlt sich, vor der Optimierung eine Sicherungskopie des Originaldokuments anzufertigen.

#### F: Hat die Aktivierung dieser Funktion Auswirkungen auf das visuelle Erscheinungsbild oder den Inhalt des PDF-Dokuments?

A: Die Aktivierung der Funktion „Wiederverwendung von Seiteninhalten zulassen“ hat keinen Einfluss auf das visuelle Erscheinungsbild oder den Inhalt des PDF-Dokuments. Es optimiert lediglich die interne Struktur der Datei, um Redundanz zu reduzieren und die Effizienz zu steigern.

#### F: Ist Aspose.PDF für .NET eine zuverlässige Lösung für die PDF-Optimierung und -Bearbeitung?

A: Ja, Aspose.PDF für .NET ist eine zuverlässige und funktionsreiche Bibliothek zur PDF-Optimierung und -Bearbeitung. Es bietet umfangreiche Optionen zur Optimierung von PDF-Dateien, einschließlich der Reduzierung der Dateigröße, der Entfernung ungenutzter Ressourcen und der Verbesserung der Gesamtleistung.