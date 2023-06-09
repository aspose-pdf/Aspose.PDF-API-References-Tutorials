---
title: Deaktivieren Sie die Dateikomprimierung
linktitle: Deaktivieren Sie die Dateikomprimierung
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie die Dateikomprimierung in einer PDF-Datei mit Aspose.PDF für .NET deaktivieren. Schritt-für-Schritt-Anleitung für einfache Handhabung.
type: docs
weight: 30
url: /de/net/programming-with-attachments/disable-files-compression/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um die Dateikomprimierung in einer PDF-Datei mit Aspose.PDF für .NET zu deaktivieren.

Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen. Außerdem verfügen Sie über Grundkenntnisse der C#-Programmierung.

### Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Quellcode müssen Sie das Verzeichnis angeben, in dem sich die PDF-Datei befindet, in der Sie die Dateikomprimierung deaktivieren möchten. Ändern Sie die Variable „dataDir“ in das gewünschte Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Schritt 2: Öffnen Sie das vorhandene PDF-Dokument

Wir öffnen das vorhandene PDF-Dokument über den angegebenen Pfad.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Schritt 3: Einrichten der neuen Datei zum Hinzufügen als Anhang

Wir konfigurieren die neue Datei, die wir als Anhang hinzufügen möchten. In diesem Beispiel fügen wir eine Textdatei mit dem Namen „test_out.txt“ und der Beschreibung „Beispieltextdatei“ hinzu.

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### Schritt 4: Deaktivieren Sie die Dateikomprimierung

Wir deaktivieren die Dateikomprimierung, indem wir die Encoding-Eigenschaft des FileSpecification-Objekts auf FileEncoding.None setzen.

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### Schritt 5: Hinzufügen des Anhangs zur Anhangssammlung des Dokuments

Wir fügen den Anhang zur Anhangssammlung des Dokuments hinzu.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Schritt 6: Speichern Sie die neue Ausgabedatei

Abschließend speichern wir die resultierende neue PDF-Datei mit dem Namen „DisableFilesCompression_out.pdf“ im angegebenen Verzeichnis.

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### Beispielquellcode zum Deaktivieren der Dateikomprimierung mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Richten Sie eine neue Datei ein, die als Anhang hinzugefügt werden soll
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
// Geben Sie den Encoding-Profi an und setzen Sie ihn auf FileEncoding.None
fileSpecification.Encoding = FileEncoding.None;
// Anhang zur Anhangssammlung des Dokuments hinzufügen
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
// Neue Ausgabe speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie die Dateikomprimierung in einer PDF-Datei mit Aspose.PDF für .NET deaktivieren. Sie können dieses Wissen nun nutzen, um die Integrität angehängter Dateien ohne Komprimierung aufrechtzuerhalten.