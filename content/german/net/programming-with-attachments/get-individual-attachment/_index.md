---
title: Erhalten Sie einen individuellen Anhang als PDF-Datei
linktitle: Erhalten Sie einen individuellen Anhang als PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET einen individuellen Anhang in einer PDF-Datei erhalten.
type: docs
weight: 60
url: /de/net/programming-with-attachments/get-individual-attachment/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um mit Aspose.PDF für .NET einen individuellen Anhang einer PDF-Datei zu erhalten.

Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen. Außerdem verfügen Sie über Grundkenntnisse der C#-Programmierung.

### Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Quellcode müssen Sie das Verzeichnis angeben, in dem sich die PDF-Datei befindet, aus der Sie den einzelnen Anhang beziehen möchten. Ändern Sie die Variable „dataDir“ in das gewünschte Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Schritt 2: Öffnen Sie das vorhandene PDF-Dokument

Wir öffnen das vorhandene PDF-Dokument über den angegebenen Pfad.

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
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

### Schritt 5: Anhang abrufen und in einer Datei speichern

Wir rufen den Inhalt des Anhangs ab und speichern ihn in einer Textdatei. In diesem Beispiel wird die Datei unter dem Namen „test_out.txt“ gespeichert.

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### Beispielquellcode für „Get Individual Attachment“ mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
// Holen Sie sich eine bestimmte eingebettete Datei
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// Rufen Sie die Dateieigenschaften ab
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
//Überprüfen Sie, ob das Parameterobjekt die Parameter enthält
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
// Holen Sie sich den Anhang und schreiben Sie in eine Datei oder einen Stream
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie man mit Aspose.PDF für .NET einen einzelnen Anhang aus einer PDF-Datei erhält. Mit diesem Wissen können Sie nun Anhänge aus Ihren PDF-Dateien extrahieren und speichern.

### FAQs zum Abrufen individueller Anhänge in einer PDF-Datei

#### F: Was ist der Zweck, einen einzelnen Anhang aus einem PDF-Dokument zu erhalten?

A: Wenn Sie einen einzelnen Anhang erhalten, können Sie eine bestimmte eingebettete Datei in einer PDF-Datei extrahieren und speichern, was für die weitere Analyse oder Bearbeitung nützlich sein kann.

#### F: Wie kann ich von diesem Tutorial bei meinen PDF-bezogenen Aufgaben profitieren?

A: Dieses Tutorial bietet Schritt-für-Schritt-Anleitungen und C#-Quellcode zum Abrufen und Speichern eines bestimmten Anhangs aus einem PDF-Dokument mit Aspose.PDF für .NET.

#### F: Auf welche Anhangseigenschaften kann ich mit diesem Tutorial zugreifen?

A: Sie können auf Anhangseigenschaften wie Name, Beschreibung, MIME-Typ, Kontroll-Hash, Erstellungsdatum, Änderungsdatum und Größe des jeweiligen Anhangs zugreifen.

#### F: Kann ich den Code ändern, um andere Anhänge als den ersten Anhang abzurufen?

 A: Auf jeden Fall können Sie den Index anpassen (z. B.`pdfDocument.EmbeddedFiles[1]`), um Anhänge an verschiedenen Indizes innerhalb der PDF abzurufen.

#### F: Wie speichere ich den abgerufenen Anhang in einer Datei?

A: Dieses Tutorial stellt Code bereit, um den Inhalt des Anhangs abzurufen und ihn in einer Textdatei mit einem angegebenen Namen zu speichern.

#### F: Welche Bedeutung hat die Eigenschaft „Hash prüfen“ in Anhangsinformationen?

A: Die Eigenschaft „Check Hash“ stellt den Kontroll-Hash-Wert des Anhangs dar, der zur Überprüfung der Integrität des Anhangs verwendet werden kann.

#### F: Kann ich dieses Wissen erweitern, um Anhänge mit bestimmten Kriterien wie dem Dateityp zu extrahieren?

A: Ja, Sie können den Code erweitern, um Anhänge nach bestimmten Kriterien wie Dateityp oder anderen Eigenschaften zu filtern.

#### F: Wie vereinfacht Aspose.PDF für .NET das Extrahieren einzelner Anhänge?

A: Aspose.PDF für .NET bietet eine benutzerfreundliche API, die das Extrahieren und Bearbeiten von Anhängen in PDF-Dokumenten erleichtert.

#### F: Ist dieses Tutorial auch für passwortgeschützte PDF-Dateien relevant?

A: Ja, Sie können ähnliche Techniken anpassen, um mit Aspose.PDF für .NET einzelne Anhänge aus passwortgeschützten PDF-Dateien abzurufen.
