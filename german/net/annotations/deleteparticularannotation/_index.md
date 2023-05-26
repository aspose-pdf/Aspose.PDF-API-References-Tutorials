---
title: Bestimmte Anmerkung löschen
linktitle: Bestimmte Anmerkung löschen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET eine bestimmte Anmerkung aus einem PDF-Dokument löschen.
type: docs
weight: 50
url: /de/net/annotations/deleteparticularannotation/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie Aspose.PDF für .NET verwenden, um mit C# eine bestimmte Anmerkung aus einer PDF-Datei zu löschen.

Befolgen Sie die folgenden Schritte, um zu zeigen, wie Sie bestimmte Anmerkungen mit Aspose.PDF für .NET löschen

## Schritt 1: Legen Sie den Verzeichnispfad fest

Deklarieren Sie eine Variable, die den Pfad zur PDF-Datei enthält, die die zu löschende Anmerkung enthält. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument

 Öffnen Sie die PDF-Datei mit`Document` Klasse in Aspose.PDF für .NET.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteParticularAnnotation.pdf");
```

## Schritt 3: Rufen Sie die Seite auf, um die jeweilige Anmerkung zu löschen

Löschen Sie die jeweilige Anmerkung, indem Sie ihren Index und den Index der Seite angeben, zu der sie gehört. In diesem Tutorial löschen wir die Anmerkung an Index 1 auf der zweiten Seite der PDF-Datei.

```csharp
pdfDocument.Pages[1].Annotations.Delete(1);
```
## Schritt 4: Speichern Sie das aktualisierte PDF-Dokument

Speichern Sie die aktualisierte PDF-Datei in einer neuen Datei mit einem anderen Namen.

```csharp
dataDir = dataDir + "DeleteParticularAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```

## Schritt 5: Zeigen Sie eine Meldung zum Löschen einer bestimmten Anmerkung an

Drucken Sie eine Meldung aus, die angibt, dass die jeweilige Anmerkung gelöscht und die aktualisierte PDF-Datei gespeichert wurde.

```csharp
Console.WriteLine("\nParticular annotation deleted successfully.\nFile saved at " + dataDir);
```

### Beispielquellcode zum Löschen einer bestimmten Anmerkung mit Aspose.PDF für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Dokument öffnen
	Document pdfDocument = new Document(dataDir + "DeleteParticularAnnotation.pdf");

	// Bestimmte Anmerkung löschen
	pdfDocument.Pages[1].Annotations.Delete(1);

	dataDir = dataDir + "DeleteParticularAnnotation_out.pdf";
	// Aktualisiertes Dokument speichern
	pdfDocument.Save(dataDir);

	Console.WriteLine("\nParticular annotation deleted successfully.\nFile saved at " + dataDir);

```
