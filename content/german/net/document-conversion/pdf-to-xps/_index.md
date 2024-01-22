---
title: PDF zu XPS
linktitle: PDF zu XPS
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren von PDF in XPS mit Aspose.PDF für .NET.
type: docs
weight: 220
url: /de/net/document-conversion/pdf-to-xps/
---
In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung einer PDF-Datei in das XPS-Format (XML Paper Specification) mit Aspose.PDF für .NET. Das XPS-Format ist ein XML-basiertes Dateiformat, das zur elektronischen Darstellung von Dokumenten verwendet wird. Wenn Sie die folgenden Schritte ausführen, können Sie eine PDF-Datei in das XPS-Format konvertieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: Laden des PDF-Dokuments
In diesem Schritt laden wir die Quell-PDF-Datei mit Aspose.PDF für .NET. Befolgen Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Unbedingt austauschen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre PDF-Datei befindet.

## Schritt 2: XPS-Speicheroptionen instanziieren
Nach dem Laden der PDF-Datei instanziieren wir die XPS-Speicheroptionen. Verwenden Sie den folgenden Code:

```csharp
// Instanziieren Sie XPS-Speicheroptionen
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Schritt 3: Speichern der resultierenden XPS-Datei
Jetzt speichern wir die konvertierte PDF-Datei im XPS-Format. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie das XPS-Dokument
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 Der obige Code speichert die konvertierte PDF-Datei im XPS-Format unter dem Dateinamen`"PDFToXPS_out.xps"`.


### Beispielquellcode für PDF zu XPS mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF-Dokument laden
Document pdfDocument = new Document(dataDir + "input.pdf");

// Instanziieren Sie XPS-Speicheroptionen
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// Speichern Sie das XPS-Dokument
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess zum Konvertieren einer PDF-Datei in das XPS-Format mit Aspose.PDF für .NET behandelt. Wenn Sie die oben beschriebenen Anweisungen befolgen, sollten Sie nun in der Lage sein, eine PDF-Datei in das XPS-Format zu konvertieren. Diese Funktion ist nützlich, wenn Sie PDF-Dokumente im XPS-Format anzeigen oder drucken möchten.

### FAQs

#### F: Ist das XPS-Format für die plattformübergreifende Kompatibilität geeignet?

A: Das XPS-Format ist ein XML-basiertes Dateiformat, plattformunabhängig und kann auf verschiedenen Betriebssystemen und Geräten angezeigt werden. XPS-Dateien werden standardmäßig auf Windows-Plattformen unterstützt, und einige Anwendungen und Viewer von Drittanbietern sind möglicherweise für andere Plattformen verfügbar.

#### F: Kann Aspose.PDF für .NET bei der XPS-Konvertierung komplexe PDF-Dateien mit mehreren Seiten und Bildern verarbeiten?

A: Ja, Aspose.PDF für .NET kann während der XPS-Konvertierung komplexe PDF-Dateien mit mehreren Seiten und Bildern verarbeiten. Es behält das Layout, die Bilder und den Textinhalt der PDF-Datei bei der Konvertierung in das XPS-Format genau bei.

#### F: Ist es möglich, während des XPS-Konvertierungsprozesses zusätzliche Einstellungen oder Optionen festzulegen?

 A: Ja, Aspose.PDF für .NET bietet verschiedene Optionen und Einstellungen, die während des XPS-Konvertierungsprozesses angepasst werden können. Sie können die Bildkomprimierung, das Einbetten von Schriftarten und andere Einstellungen mithilfe von steuern`XpsSaveOptions` Klasse.

#### F: Können passwortgeschützte PDFs mit Aspose.PDF für .NET in das XPS-Format konvertiert werden?

 A: Ja, Aspose.PDF für .NET unterstützt die Konvertierung passwortgeschützter PDFs in das XPS-Format. Beim Laden einer passwortgeschützten PDF-Datei können Sie das Passwort mithilfe von angeben`Document` Klassenkonstruktor oder durch Festlegen der`Password` Eigenschaft vor dem Laden der PDF-Datei.