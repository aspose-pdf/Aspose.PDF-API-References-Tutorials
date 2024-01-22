---
title: PDF zu PDFA3b
linktitle: PDF zu PDFA3b
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren von PDF in PDF/A-3b mit Aspose.PDF für .NET.
type: docs
weight: 150
url: /de/net/document-conversion/pdf-to-pdfa3b/
---
In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung einer PDF-Datei in das PDF/A-3b-Format mit Aspose.PDF für .NET. PDF/A-3b ist ein ISO-Standard zum Einbetten von Dateien und Daten in ein PDF-Dokument. Wenn Sie die folgenden Schritte ausführen, können Sie PDF-Dateien in das PDF/A-3b-Format konvertieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: Öffnen des Quell-PDF-Dokuments
In diesem Schritt öffnen wir die Quell-PDF-Datei mit Aspose.PDF für .NET. Befolgen Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öffnen Sie das Quell-PDF-Dokument
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Unbedingt austauschen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre PDF-Datei befindet.

## Schritt 2: Konvertieren in PDF/A-3b
Nach dem Öffnen der PDF-Datei können wir mit der Konvertierung in das PDF/A-3b-Format fortfahren. Verwenden Sie den folgenden Code:

```csharp
// Konvertieren Sie in das PDF/A-3b-Format
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

Der obige Code konvertiert die PDF-Datei in das PDF/A-3b-Format und beseitigt etwaige Konvertierungsfehler.

## Schritt 3: Speichern der resultierenden PDF/A-3b-Datei
Nachdem die Konvertierung abgeschlossen ist, müssen wir die resultierende PDF/A-3b-Datei speichern. Hier ist der letzte Schritt:

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Speichern Sie das Ausgabedokument
pdfDocument.Save(dataDir);
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem gewünschten Verzeichnis, in dem Sie die ausgegebene PDF/A-3b-Datei speichern möchten.

### Beispielquellcode für PDF zu PDFA3b mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Ausgabedokument speichern
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess der Konvertierung einer PDF-Datei in das PDF/A-3b-Format mit Aspose.PDF für .NET behandelt. Wenn Sie die oben beschriebenen Anweisungen befolgen, sollten Sie nun in der Lage sein, PDF-Dateien in das PDF/A-3b-Format zu konvertieren. Diese Funktion ist nützlich, wenn Sie zusätzliche Dateien und Daten in ein PDF-Dokument einbetten möchten, das dem PDF/A-3b-Standard entspricht.

### FAQs

#### F: Was ist PDF/A-3b und wie unterscheidet es sich von anderen PDF/A-Standards?

A: PDF/A-3b ist ein ISO-Standard, der die Einbettung von Dateien und Daten in ein PDF-Dokument ermöglicht, wodurch es in sich geschlossen wird und eine langfristige Aufbewahrung gewährleistet. Im Gegensatz zu anderen PDF/A-Standards wie PDF/A-1 und PDF/A-2 ermöglicht PDF/A-3b die Einbindung zusätzlicher Dateien und Daten in das PDF-Dokument. Durch diese Funktion eignet es sich für die Archivierung und den Austausch komplexer und interaktiver Dokumente.

#### F: Kann ich mehrere Dateien und Daten in ein PDF/A-3b-Dokument einfügen?

A: Ja, einer der Hauptvorteile von PDF/A-3b ist die Möglichkeit, mehrere Dateien und Daten in das PDF-Dokument einzubinden. Sie können verschiedene Dateitypen wie XML, Tabellenkalkulationen, Bilder oder andere PDF-Dateien zusammen mit dem Haupt-PDF-Inhalt einbetten. Dadurch wird das PDF/A-3b-Dokument zu einem in sich geschlossenen Paket, das alle notwendigen Elemente enthält.

#### F: Was passiert, wenn beim Konvertierungsprozess von PDF in PDF/A-3b Fehler auftreten?

 A: Beim Konvertieren einer PDF-Datei in das PDF/A-3b-Format mit Aspose.PDF für .NET haben Sie die Kontrolle darüber, wie Fehler behandelt werden. Der`Convert` Methode`ConvertErrorAction` Der Parameter bestimmt die Aktion, die bei Fehlern ausgeführt werden soll. Im bereitgestellten Codebeispiel ist die`ConvertErrorAction.Delete` Der Parameter wird verwendet, was bedeutet, dass bei der Konvertierung auftretende Fehler zum Löschen der fehlerhaften Seiten führen.

#### F: Ist PDF/A-3b für die Langzeitarchivierung von Dokumenten geeignet?

A: Ja, PDF/A-3b ist speziell für die Langzeitarchivierung elektronischer Dokumente konzipiert. Durch die Einbettung zusätzlicher Dateien und Daten wird sichergestellt, dass alle erforderlichen Komponenten im PDF-Dokument selbst enthalten sind, wodurch das Risiko von Informationsverlusten oder externen Abhängigkeiten im Laufe der Zeit verringert wird. Diese Funktion eignet sich für die Archivierung von Dokumenten, die eine langfristige Zugänglichkeit und Konsistenz gewährleistet.