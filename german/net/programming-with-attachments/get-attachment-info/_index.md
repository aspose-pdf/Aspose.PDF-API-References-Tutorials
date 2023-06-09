---
title: Erhalten Sie Anhangsinformationen
linktitle: Erhalten Sie Anhangsinformationen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Informationen zu einem bestimmten Anhang in einer PDF-Datei abrufen. Schritt für Schritt Anleitung.
type: docs
weight: 50
url: /de/net/programming-with-attachments/get-attachment-info/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um mithilfe von Aspose.PDF für .NET Informationen zu einem bestimmten Anhang einer PDF-Datei zu erhalten.

Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen. Außerdem verfügen Sie über Grundkenntnisse der C#-Programmierung.

### Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Quellcode müssen Sie das Verzeichnis angeben, in dem sich die PDF-Datei befindet, aus der Sie die Anhangsinformationen beziehen möchten. Ändern Sie die Variable „dataDir“ in das gewünschte Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Schritt 2: Öffnen Sie das vorhandene PDF-Dokument

Wir öffnen das vorhandene PDF-Dokument über den angegebenen Pfad.

```csharp
Document pdfDocument = new Document(dataDir + "GetAttachmentInfo.pdf");
```

### Schritt 3: Erhalten eines bestimmten Anhangs

Wir rufen einen bestimmten Anhang aus der Anhangssammlung des Dokuments ab. In diesem Beispiel erhalten wir den ersten Anhang mit Index 1.

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### Schritt 4: Dateieigenschaften abrufen

Wir zeigen Anhangseigenschaften wie Name, Beschreibung, MIME-Typ, Kontroll-Hash, Erstellungsdatum, Änderungsdatum und Größe an.

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Prüfen Sie, ob Objektparameter zusätzliche Informationen enthalten
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### Beispielquellcode für „Anhangsinformationen abrufen“ mit Aspose.PDF für .NET
 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "GetAttachmentInfo.pdf");
// Holen Sie sich eine bestimmte eingebettete Datei
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// Rufen Sie die Dateieigenschaften ab
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
// Überprüfen Sie, ob das Parameterobjekt die Parameter enthält
if (fileSpecification.Params != null)
{
	Console.WriteLine("CheckSum: {0}",
	fileSpecification.Params.CheckSum);
	Console.WriteLine("Creation Date: {0}",
	fileSpecification.Params.CreationDate);
	Console.WriteLine("Modification Date: {0}",
	fileSpecification.Params.ModDate);
	Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie mit Aspose.PDF für .NET Informationen zu einem bestimmten Anhang einer PDF-Datei erhalten. Mit diesem Wissen können Sie nun Anhanginformationen aus Ihren PDF-Dateien extrahieren und anzeigen.
