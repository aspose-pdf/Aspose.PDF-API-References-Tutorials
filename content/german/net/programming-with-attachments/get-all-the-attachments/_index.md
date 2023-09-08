---
title: Holen Sie sich alle Anhänge als PDF-Datei
linktitle: Holen Sie sich alle Anhänge als PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET alle Anhänge in eine PDF-Datei übertragen. Schritt-für-Schritt-Anleitung für einfache Handhabung.
type: docs
weight: 40
url: /de/net/programming-with-attachments/get-all-the-attachments/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um alle Anhänge mit Aspose.PDF für .NET in eine PDF-Datei zu übertragen.

Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen. Außerdem verfügen Sie über Grundkenntnisse der C#-Programmierung.

### Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Quellcode müssen Sie das Verzeichnis angeben, in dem sich die PDF-Datei befindet, aus der Sie die Anhänge beziehen möchten. Ändern Sie die Variable „dataDir“ in das gewünschte Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Schritt 2: Öffnen Sie das vorhandene PDF-Dokument

Wir öffnen das vorhandene PDF-Dokument über den angegebenen Pfad.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Schritt 3: Abrufen der Anhangssammlung

Wir erhalten die Sammlung von Anhängen aus dem Dokument.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### Schritt 4: Anhänge abrufen

Wir gehen die Sammlung durch, um alle Anhänge abzurufen und deren Informationen anzuzeigen. Wir speichern Anhänge auch in einzelnen Dateien.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Prüfen Sie, ob Objektparameter zusätzliche Informationen enthalten
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// Rufen Sie den Anhang ab und speichern Sie ihn in einer Datei
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Beispielquellcode für „Get Allthe Attachments“ mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Erhalten Sie eine Sammlung eingebetteter Dateien
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// Ermitteln Sie die Anzahl der eingebetteten Dateien
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// Gehen Sie die Sammlung durch, um alle Anhänge zu erhalten
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
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
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie mit Aspose.PDF für .NET alle Anhänge aus einer PDF-Datei abrufen. Mit diesem Wissen können Sie nun Anhänge aus Ihren PDF-Dateien extrahieren und bearbeiten.

## FAQs zum Abrufen aller Anhänge in einer PDF-Datei

#### F: Warum sollte ich alle Anhänge aus einem PDF-Dokument abrufen?

A: Durch das Abrufen von Anhängen können Sie auf zusätzliche in eine PDF-Datei eingebettete Dateien zugreifen und diese bearbeiten, was zum Archivieren, Teilen oder Weiterverarbeiten nützlich sein kann.

#### F: Welche Dateitypen können an ein PDF-Dokument angehängt werden?

A: PDF-Dokumente können eine Vielzahl an angehängten Dateien enthalten, darunter Bilder, Dokumente, Tabellenkalkulationen, Audiodateien und mehr.

#### F: Wie hilft mir dieses Tutorial beim Abrufen von Anhängen aus einer PDF-Datei mit Aspose.PDF für .NET?

A: Dieses Tutorial bietet Schritt-für-Schritt-Anleitungen und C#-Quellcode für den Zugriff und den Abruf aller Anhänge in einem PDF-Dokument.

#### F: Kann ich mit diesem Tutorial bestimmte Anhänge anstelle aller Anhänge abrufen?

A: Ja, Sie können den bereitgestellten Code ändern, um Anhänge entsprechend Ihren Anforderungen gezielt abzurufen.

#### F: Welche Informationen zu den einzelnen Anhängen kann ich mit diesem Tutorial erhalten?

A: In diesem Tutorial wird gezeigt, wie Sie Details wie den Namen, die Beschreibung, den MIME-Typ, das Erstellungsdatum, das Änderungsdatum und die Größe des Anhangs abrufen und anzeigen.

#### F: Wie werden die mit diesem Tutorial abgerufenen Anhänge gespeichert?

A: Das Tutorial führt Sie durch das Speichern jedes abgerufenen Anhangs als separate Datei im angegebenen Verzeichnis.

#### F: Kann ich dieses Wissen nutzen, um Anhänge aus passwortgeschützten PDF-Dateien zu extrahieren?

A: Ja, Sie können ähnliche Prinzipien anwenden, um Anhänge aus passwortgeschützten PDF-Dateien mit Aspose.PDF für .NET abzurufen.

#### F: Wie erleichtert Aspose.PDF für .NET das Abrufen von Anhängen?

A: Aspose.PDF für .NET bietet eine intuitive API, mit der Sie problemlos auf Anhänge in PDF-Dokumenten zugreifen und diese bearbeiten können.

#### F: Gibt es bestimmte Szenarien, in denen das Abrufen von Anhängen empfohlen wird?

A: Das Abrufen von Anhängen ist nützlich, wenn Sie auf in einer PDF-Datei eingebettete Dateien zugreifen müssen, z. B. zum Extrahieren von Bildern, Audiodateien oder zusätzlichen Dokumenten.