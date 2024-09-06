---
title: Einbettung von Schriftarten aufheben und PDF-Dateien optimieren
linktitle: Einbettung von Schriftarten aufheben und PDF-Dateien optimieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Schriftarten entfernen und PDF-Dateien optimieren. Eine Schritt-für-Schritt-Anleitung.
type: docs
weight: 370
url: /de/net/programming-with-document/unembedfonts/
---
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die eine breite Palette von Funktionen für die Arbeit mit PDF-Dokumenten bietet. Eine ihrer Funktionen besteht darin, Schriftarten aus einem PDF-Dokument zu entfernen. Dies kann nützlich sein, wenn Sie Schriftarten aus einem PDF-Dokument extrahieren und in anderen Anwendungen verwenden müssen.

Wir stellen eine Schritt-für-Schritt-Anleitung bereit, um den folgenden C#-Quellcode der Funktion zum Aufheben der Einbettung von Schriftarten von Aspose.PDF für .NET zu erklären.

## Schritt 1: Pfad zum Dokumentverzeichnis festlegen

Bevor wir beginnen, müssen wir den Pfad zum Verzeichnis festlegen, in dem sich unser PDF-Dokument befindet. Wir speichern diesen Pfad in einer Variablen namens „dataDir“.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad zum Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 2: Öffnen Sie das PDF-Dokument

 Der erste Schritt besteht darin, das PDF-Dokument zu laden, das Sie dazu verwenden möchten.`Document` Klasse von Aspose.PDF für .NET. Der folgende Codeausschnitt zeigt, wie das PDF-Dokument geladen wird:

```csharp
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Schritt 3: Setzen Sie die Option UnembedFonts

 Um nicht eingebettete Schriftarten aus dem PDF-Dokument zu entfernen, müssen Sie die`UnembedFonts` Möglichkeit,`true` Diese Option ist verfügbar im`OptimizationOptions` Klasse. Der folgende Codeausschnitt zeigt, wie man die`UnembedFonts` Option:

```csharp
// Option „UnembedFonts“ festlegen
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Schritt 4: Optimieren Sie das PDF-Dokument

 Nach dem Einstellen der`UnembedFonts` können Sie das PDF-Dokument optimieren, indem Sie`OptimizeResources` Methode der`Document` Klasse. Der folgende Codeausschnitt zeigt, wie das PDF-Dokument optimiert wird:

```csharp
// Optimieren Sie PDF-Dokumente mit OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Schritt 5: Speichern Sie das aktualisierte Dokument

 Sobald das PDF-Dokument optimiert ist, können Sie das aktualisierte Dokument mit dem`Save` Methode der`Document`Klasse. Der folgende Codeausschnitt zeigt, wie das aktualisierte Dokument gespeichert wird:

```csharp
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Schritt 6: Holen Sie sich die ursprüngliche und reduzierte Dateigröße

 Schließlich können Sie die ursprüngliche und reduzierte Dateigröße des PDF-Dokuments abrufen mit dem`FileInfo` Klasse von System.IO. Der folgende Codeausschnitt zeigt, wie man die ursprüngliche und die reduzierte Dateigröße erhält:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Beispiel-Quellcode zum Abrufen nicht eingebetteter Schriftarten mit Aspose.PDF für .NET

Hier ist der vollständige Beispielquellcode zum Abrufen nicht eingebetteter Schriftarten aus einem PDF-Dokument mit Aspose.PDF für .NET:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Option „UnembedFonts“ festlegen
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
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
```

## Abschluss

In diesem Tutorial haben wir gezeigt, wie Sie mit Aspose.PDF für .NET Schriftarten aus einem PDF-Dokument entfernen. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie diese Funktion problemlos in Ihre C#-Anwendungen implementieren. Das Entfernen von Schriftarten kann von Vorteil sein, wenn Sie mit den extrahierten Schriftarten separat arbeiten oder eine konsistente Verwendung der Schriftarten auf verschiedenen Plattformen sicherstellen müssen.

## Häufig gestellte Fragen

#### F: Was ist der Zweck der Ausbettung von Schriftarten aus einem PDF-Dokument?

A: Durch das Aufheben der Einbettung von Schriftarten aus einem PDF-Dokument können Sie die eingebetteten Schriftarten extrahieren und in anderen Anwendungen verwenden. Dies kann nützlich sein, um eine konsistente Schriftartdarstellung sicherzustellen und das visuelle Erscheinungsbild des Dokuments beizubehalten.

#### F: Wie gebe ich den Pfad zum Dokumentverzeichnis im C#-Code an?

 A: Um den Pfad zum Dokumentverzeichnis anzugeben, ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code durch den tatsächlichen Pfad zum Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

####  F: Was bedeutet das`UnembedFonts` option do, and where is it set?

 A: Die`UnembedFonts` Option, verfügbar in der`OptimizationOptions` Klasse aktiviert oder deaktiviert das Ausbetten von Schriftarten aus dem PDF-Dokument. Um diese Option auf`true`, verwenden Sie den folgenden Code:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### F: Kann ich die während des Optimierungsprozesses vorgenommenen Änderungen rückgängig machen?

A: Aspose.PDF für .NET nimmt während der Optimierung keine dauerhaften Änderungen am ursprünglichen PDF-Dokument vor. Der Optimierungsprozess wird an einer Kopie des Dokuments durchgeführt, wobei das Original unverändert bleibt.

#### F: Wie kann ich die ursprüngliche und die reduzierte Dateigröße nach der Optimierung überprüfen?

 A: Sie können die`FileInfo` Klasse von`System.IO` um die ursprüngliche und reduzierte Dateigröße zu erhalten. Hier ist ein Beispiel-Codeausschnitt, um dies zu erreichen:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```