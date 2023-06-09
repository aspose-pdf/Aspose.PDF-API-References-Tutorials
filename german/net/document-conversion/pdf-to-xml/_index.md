---
title: PDF zu XML
linktitle: PDF zu XML
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren von PDF in XML mit Aspose.PDF für .NET.
type: docs
weight: 210
url: /de/net/document-conversion/pdf-to-xml/
---

In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung einer PDF-Datei in das XML-Format mit Aspose.PDF für .NET. XML (eXtensible Markup Language) ist ein Datenformat zum Speichern und Austauschen strukturierter Informationen. Wenn Sie die folgenden Schritte ausführen, können Sie eine PDF-Datei in das XML-Format konvertieren.

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
Document doc = new Document(dataDir + "input.pdf");
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre PDF-Datei befindet.

## Schritt 2: Speichern der resultierenden XML-Datei
Jetzt speichern wir die konvertierte PDF-Datei im XML-Format. Verwenden Sie den folgenden Code:

```csharp
// Ausgabe als XML speichern
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

 Der obige Code speichert die konvertierte PDF-Datei im XML-Format unter dem Dateinamen`"PDFToXML_out.xml"`.

### Beispielquellcode für PDF zu XML mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
// Laden Sie die PDF-Quelldatei
Document doc = new Document(dataDir + "input.pdf");
// Speichern Sie die Ausgabe im XML-Format
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess der Konvertierung einer PDF-Datei in XML mit Aspose.PDF für .NET behandelt. Wenn Sie die oben beschriebenen Anweisungen befolgen, sollten Sie nun in der Lage sein, eine PDF-Datei in das XML-Format zu konvertieren. Diese Funktion ist nützlich, wenn Sie strukturierte Inhalte aus einer PDF-Datei extrahieren und zur späteren Verwendung in ein XML-Format verarbeiten möchten.