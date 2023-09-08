---
title: XML zu PDFBildpfad festlegen
linktitle: XML zu PDFBildpfad festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Festlegen des Pfads eines Bildes beim Konvertieren von XML in PDF mit Aspose.PDF für .NET.
type: docs
weight: 340
url: /de/net/document-conversion/xml-to-pdfset-image-path/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch die Festlegung des Pfads eines Bildes beim Konvertieren einer XML-Datei in PDF mithilfe der Aspose.PDF-Bibliothek für .NET. Wir erläutern den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren. Am Ende dieses Tutorials können Sie beim Konvertieren von XML in PDF ganz einfach den Pfad eines Bildes angeben.

## Schritt 1: Dateipfade festlegen
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string inXml = dataDir + "input.xml";
string inFile = dataDir + "aspose-logo.jpg";
string outFile = dataDir + "output_out.pdf";
```
 Definieren Sie die Pfade der XML-Eingabedateien, des zu verwendenden Bildes und der PDF-Ausgabedatei. Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem Pfad, in dem Sie Ihre Dateien gespeichert haben.

## Schritt 2: Instanziieren Sie ein Document-Objekt
```csharp
Document doc = new Document();
```
Erstellen Sie eine Instanz des Document-Objekts.

## Schritt 3: Verknüpfen Sie die XML-Quelldatei
```csharp
doc. BindXml(inXml);
```
Verknüpft die XML-Quelldatei mit dem Dokument.

## Schritt 4: Bildpfad festlegen
```csharp
Image image = (Image)doc.GetObjectById("testImg");
image.File = inFile;
```
Rufen Sie mithilfe seiner ID die Bildobjektreferenz aus dem XML ab und legen Sie den Pfad des zu verwendenden Bilds fest.

## Schritt 5: Speichern Sie die resultierende PDF-Datei
```csharp
doc.Save(outFile);
```
Speichern Sie die resultierende PDF-Datei im angegebenen Verzeichnis.

### Beispielquellcode für XML to PDFSet Image Path mit Aspose.PDF für .NET

```csharp
try
{
	
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string inXml = dataDir + "input.xml";
	string inFile = dataDir + "aspose-logo.jpg";
	string outFile = dataDir + "output_out.pdf";
	Document doc = new Document();
	doc.BindXml(inXml);
	Image image = (Image)doc.GetObjectById("testImg");
	image.File = inFile;
	doc.Save(outFile);
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man den Pfad eines Bildes beim Konvertieren von XML in PDF mithilfe der Aspose.PDF-Bibliothek für .NET festlegt. Indem Sie die bereitgestellten Schritte befolgen, können Sie den Bildpfad ganz einfach in Ihren eigenen XML-zu-PDF-Konvertierungen angeben.

### FAQs

#### F: Wozu dient das Festlegen des Bildpfads beim Konvertieren von XML in PDF?

A: Beim Konvertieren von XML in PDF können Sie durch Festlegen des Bildpfads den Speicherort eines Bilds angeben, auf das im XML verwiesen wird. Dadurch wird sichergestellt, dass das Bild im resultierenden PDF-Dokument korrekt angezeigt wird.

#### F: Kann ich Bilder aus verschiedenen Verzeichnissen verwenden?

 A: Ja, Sie können Bilder aus verschiedenen Verzeichnissen verwenden, indem Sie für jedes Bild den richtigen Dateipfad angeben. Im bereitgestellten Code ist die`inFile` Die Variable enthält den Pfad zur Bilddatei und Sie können sie aktualisieren, um auf Bilder in verschiedenen Verzeichnissen zu verweisen.

#### F: Kann ich Bilder von einer Remote-URL verwenden?

A: Ja, Sie können Bilder von einer Remote-URL verwenden, indem Sie die URL anstelle eines lokalen Dateipfads angeben. Stellen Sie sicher, dass Ihre Anwendung über einen Internetzugang verfügt, um das Bild von der Remote-URL abzurufen.

#### F: Welches Format sollte die XML-Eingabedatei haben?

A: Die XML-Eingabedatei sollte eine Struktur haben, die über eine ID auf das Bild verweist. Im bereitgestellten Code wird die ID „testImg“ verwendet, um auf das Bild zu verweisen.

#### F: Kann ich dem PDF mehrere Bilder hinzufügen?

A: Ja, Sie können dem PDF mehrere Bilder hinzufügen, indem Sie sie in der XML-Datei mit unterschiedlichen IDs referenzieren und die Dateipfade entsprechend festlegen.