---
title: XPS zu PDF
linktitle: XPS zu PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren von XPS-Dateien in PDF mit Aspose.PDF für .NET.
type: docs
weight: 350
url: /de/net/document-conversion/xps-to-pdf/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch die Konvertierung einer XPS-Datei in PDF mithilfe der Aspose.PDF-Bibliothek für .NET. Wir erläutern den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren. Am Ende dieses Tutorials werden Sie in der Lage sein, XPS-Dateien problemlos in PDF-Dokumente zu konvertieren.

## Schritt 1: Dokumentenverzeichnis festlegen
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem Pfad, in dem Sie Ihre Dateien gespeichert haben.

## Schritt 2: Instanziieren Sie das LoadOptions-Objekt mithilfe von XPS-Ladeoptionen
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
Erstellen Sie eine Instanz des LoadOptions-Objekts mithilfe von XPS-Ladeoptionen.

## Schritt 3: Erstellen Sie das Dokumentobjekt
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Erstellen Sie ein Dokumentobjekt, das die XPS-Eingabedatei und die Ladeoptionen angibt.

## Schritt 4: Speichern Sie das resultierende PDF-Dokument
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Speichern Sie das resultierende PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode für XPS in PDF mit Aspose.PDF für .NET

```csharp
try
{
	
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Instanziieren Sie das LoadOption-Objekt mithilfe der XPS-Ladeoption
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// Dokumentobjekt erstellen
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// Speichern Sie das resultierende PDF-Dokument
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man XPS-Dateien mithilfe der Aspose.PDF-Bibliothek für .NET in PDF konvertiert. Wenn Sie die bereitgestellten Schritte befolgen, können Sie diese Konvertierung problemlos in Ihren eigenen Anwendungen durchführen. Erhalten Sie genaue und professionelle Ergebnisse beim Konvertieren von XPS-Dateien in PDF.