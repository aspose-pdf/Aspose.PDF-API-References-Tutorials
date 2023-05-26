---
title: Entfernen Sie nicht verwendete Objekte
linktitle: Entfernen Sie nicht verwendete Objekte
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET ungenutzte Objekte aus PDF-Dokumenten entfernen.
type: docs
weight: 260
url: /de/net/programming-with-document/removeunusedobjects/
---
Wenn Sie nach einer Möglichkeit suchen, mithilfe von Aspose.PDF für .NET nicht verwendete Objekte in Ihren PDF-Dokumenten zu entfernen, sind Sie hier richtig. Diese Schritt-für-Schritt-Anleitung zeigt Ihnen, wie Sie den bereitgestellten C#-Quellcode verwenden, um diese Aufgabe auszuführen.

## Schritt 1: Legen Sie den Verzeichnispfad fest

Zuerst müssen Sie den Pfad zu Ihrem Dokumentverzeichnis festlegen, indem Sie „IHR DOKUMENTVERZEICHNIS“ durch den entsprechenden Pfad ersetzen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument

Als nächstes müssen Sie das PDF-Dokument öffnen, das Sie optimieren möchten, indem Sie den folgenden Code verwenden:

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Schritt 3: Legen Sie die Option „RemoveUnusedObjects“ fest

Um nicht verwendete Objekte in Ihrem PDF-Dokument zu entfernen, müssen Sie die Option RemoveUnusedObjects wie folgt auf „true“ setzen:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedObjects = true
};
```

## Schritt 4: Optimieren Sie das PDF-Dokument mit OptimizationOptions

Jetzt können Sie Ihr PDF-Dokument optimieren, indem Sie die OptimizeResources-Methode mit den gerade festgelegten Optimierungsoptionen verwenden:

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Schritt 5: Speichern Sie das aktualisierte Dokument

Abschließend können Sie das aktualisierte Dokument mit dem folgenden Code speichern:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

Das ist es! Sie haben mithilfe von Aspose.PDF für .NET erfolgreich nicht verwendete Objekte aus Ihrem PDF-Dokument entfernt.

### Beispielquellcode zum Entfernen nicht verwendeter Objekte mit Aspose.PDF für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Dokument öffnen
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	// Legen Sie die Option „RemoveUsedObject“ fest
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		RemoveUnusedObjects = true
	};
	// Optimieren Sie PDF-Dokumente mit OptimizationOptions
	pdfDocument.OptimizeResources(optimizeOptions);
	dataDir = dataDir + "OptimizeDocument_out.pdf";
	// Aktualisiertes Dokument speichern
	pdfDocument.Save(dataDir);

```
