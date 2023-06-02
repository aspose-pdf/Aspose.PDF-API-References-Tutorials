---
title: Einbettung von Schriftarten aufheben
linktitle: Einbettung von Schriftarten aufheben
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie Aspose.PDF für .NET verwenden, um nicht eingebettete Schriftarten zu erhalten und PDF-Dateien zu optimieren. Eine Schritt-für-Schritt-Anleitung.
type: docs
weight: 370
url: /de/net/programming-with-document/unembedfonts/
---
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die eine Vielzahl von Funktionen für die Arbeit mit PDF-Dokumenten bietet. Eine seiner Funktionen besteht darin, die Einbettung von Schriftarten aus einem PDF-Dokument aufzuheben. Dies kann nützlich sein, wenn Sie Schriftarten aus einem PDF-Dokument extrahieren und in anderen Anwendungen verwenden müssen.

Wir stellen eine Schritt-für-Schritt-Anleitung zur Verfügung, um den folgenden C#-Quellcode der Funktion zum Entfernen der Einbettung von Schriftarten von Aspose.PDF für .NET zu erläutern.

## Schritt 1: Legen Sie den Pfad zum Dokumentverzeichnis fest

Bevor wir beginnen, müssen wir den Pfad zu dem Verzeichnis festlegen, in dem sich unser PDF-Dokument befindet. Wir werden diesen Pfad in einer Variablen namens „dataDir“ speichern.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 2: Öffnen Sie das PDF-Dokument

Der erste Schritt besteht darin, das PDF-Dokument zu laden, das Sie dazu verwenden möchten`Document` Klasse von Aspose.PDF für .NET. Der folgende Codeausschnitt zeigt, wie das PDF-Dokument geladen wird:

```csharp
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Schritt 3: Legen Sie die UnembedFonts-Option fest

 Um die Einbettung von Schriftarten aus dem PDF-Dokument aufzuheben, müssen Sie Folgendes festlegen`UnembedFonts` Option zu`true` . Diese Option ist im verfügbar`OptimizationOptions` Klasse. Der folgende Codeausschnitt zeigt, wie man das festlegt`UnembedFonts` Möglichkeit:

```csharp
// Legen Sie die Option „UnembedFonts“ fest
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Schritt 4: Optimieren Sie das PDF-Dokument

 Nach dem Einstellen der`UnembedFonts` Mit dieser Option können Sie das PDF-Dokument optimieren`OptimizeResources` Methode der`Document` Klasse. Der folgende Codeausschnitt zeigt, wie Sie das PDF-Dokument optimieren:

```csharp
// Optimieren Sie PDF-Dokumente mit OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Schritt 5: Speichern Sie das aktualisierte Dokument

 Sobald das PDF-Dokument optimiert ist, können Sie das aktualisierte Dokument mit speichern`Save` Methode der`Document` Klasse. Der folgende Codeausschnitt zeigt, wie das aktualisierte Dokument gespeichert wird:

```csharp
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Schritt 6: Holen Sie sich das Original und die reduzierte Dateigröße

 Schließlich können Sie mit dem die ursprüngliche und reduzierte Dateigröße des PDF-Dokuments abrufen`FileInfo`Klasse von System.IO. Der folgende Codeausschnitt zeigt, wie man die ursprüngliche und reduzierte Dateigröße erhält:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Beispielquellcode für „Get Unembed Fonts“ mit Aspose.PDF für .NET

Hier ist der vollständige Beispielquellcode zum Abrufen nicht eingebetteter Schriftarten aus einem PDF-Dokument mit Aspose.PDF für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Legen Sie die Option „UnembedFonts“ fest
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
