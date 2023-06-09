---
title: Anhang hinzufügen
linktitle: Anhang hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Anhänge zu Ihren PDF-Dateien hinzufügen. Schritt-für-Schritt-Anleitung für einfache Handhabung.
type: docs
weight: 10
url: /de/net/programming-with-attachments/add-attachment/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um mit Aspose.PDF für .NET einen Anhang zu einer PDF-Datei hinzuzufügen.

Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen. Außerdem verfügen Sie über Grundkenntnisse der C#-Programmierung.

### Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Quellcode müssen Sie das Verzeichnis angeben, in dem sich die PDF-Datei befindet, der Sie den Anhang hinzufügen möchten. Ändern Sie die Variable „dataDir“ in das gewünschte Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Schritt 2: Öffnen Sie das vorhandene PDF-Dokument

Wir öffnen das vorhandene PDF-Dokument über den angegebenen Pfad.

```csharp
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
```

### Schritt 3: Einrichten der neuen Datei zum Hinzufügen als Anhang

Wir konfigurieren die neue Datei, die wir als Anhang hinzufügen möchten. In diesem Beispiel fügen wir eine Textdatei mit dem Namen „test.txt“ und der Beschreibung „Beispieltextdatei“ hinzu.

```csharp
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
```

### Schritt 4: Hinzufügen des Anhangs zur Anhangssammlung des Dokuments

Wir fügen den Anhang zur Anhangssammlung des Dokuments hinzu.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Schritt 5: Speichern der neuen Ausgabedatei

Abschließend speichern wir die resultierende neue PDF-Datei mit dem Namen „AddAttachment_out.pdf“ im angegebenen Verzeichnis.

```csharp
pdfDocument.Save(dataDir + "AddAttachment_out.pdf");
```

### Beispielquellcode für „Anhang hinzufügen“ mit Aspose.PDF für .NET
 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
// Richten Sie eine neue Datei ein, die als Anhang hinzugefügt werden soll
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
// Anhang zur Anhangssammlung des Dokuments hinzufügen
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "AddAttachment_out.pdf";
// Neue Ausgabe speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nSample text file attached successfully.\nFile saved at " + dataDir);

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie man mit Aspose.PDF für .NET einen Anhang zu einer PDF-Datei hinzufügt. Dieses Wissen können Sie nun nutzen, um zusätzliche Dateien als Anhänge zu Ihren PDF-Dokumenten hinzuzufügen.
