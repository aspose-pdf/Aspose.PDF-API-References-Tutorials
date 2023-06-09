---
title: Alle Anhänge löschen
linktitle: Alle Anhänge löschen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET alle Anhänge aus einer PDF-Datei entfernen. Schritt-für-Schritt-Anleitung für einfache Handhabung.
type: docs
weight: 20
url: /de/net/programming-with-attachments/delete-all-attachments/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um alle Anhänge aus einer PDF-Datei mit Aspose.PDF für .NET zu entfernen.

Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen. Außerdem verfügen Sie über Grundkenntnisse der C#-Programmierung.

### Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Quellcode müssen Sie das Verzeichnis angeben, in dem sich die PDF-Datei befindet, aus der Sie die Anhänge entfernen möchten. Ändern Sie die Variable „dataDir“ in das gewünschte Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Schritt 2: Öffnen Sie das vorhandene PDF-Dokument

Wir öffnen das vorhandene PDF-Dokument über den angegebenen Pfad.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
```

### Schritt 3: Entfernen Sie alle Anhänge

Wir entfernen alle Anhänge aus dem Dokument.

```csharp
pdfDocument.EmbeddedFiles.Delete();
```

### Schritt 4: Speichern Sie die aktualisierte Datei

Abschließend speichern wir die aktualisierte PDF-Datei mit dem Namen „DeleteAllAttachments_out.pdf“ im angegebenen Verzeichnis.

```csharp
pdfDocument.Save(dataDir + "DeleteAllAttachments_out.pdf");
```

### Beispielquellcode zum Löschen aller Anhänge mit Aspose.PDF für .NET 

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
// Löschen Sie alle Anhänge
pdfDocument.EmbeddedFiles.Delete();
dataDir = dataDir + "DeleteAllAttachments_out.pdf";
// Aktualisierte Datei speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll attachments deleted successfully.\nFile saved at " + dataDir);

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie mit Aspose.PDF für .NET alle Anhänge aus einer PDF-Datei entfernen. Mit diesem Wissen können Sie nun Ihre PDF-Dokumente bereinigen, indem Sie alle unerwünschten Anhänge entfernen.
