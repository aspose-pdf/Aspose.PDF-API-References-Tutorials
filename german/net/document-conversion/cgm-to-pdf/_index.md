---
title: CGM zu PDF
linktitle: CGM zu PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Konvertieren Sie CGM-Dateien ganz einfach in PDF mit Aspose.PDF für .NET.
type: docs
weight: 20
url: /de/net/document-conversion/cgm-to-pdf/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch die Konvertierung von CGM in PDF mit Aspose.PDF für .NET. Wir erläutern den bereitgestellten C#-Quellcode und stellen Ihnen Schritt-für-Schritt-Anleitungen zur Verfügung, die Ihnen den Einstieg erleichtern.

## Einführung

Durch die Konvertierung einer CGM-Datei in PDF können Sie Ihre technischen Zeichnungen allgemein teilen und anzeigen. Mit Aspose.PDF für .NET können Sie diese Konvertierung ganz einfach durchführen und qualitativ hochwertige PDF-Dateien erhalten.

## Umgebungseinrichtung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung für die Arbeit mit Aspose.PDF für .NET konfiguriert haben. Folgen Sie den unteren Schritten:

1. Installieren Sie Visual Studio oder eine andere IDE, die mit der C#-Entwicklung kompatibel ist.
2. Erstellen Sie ein neues C#-Projekt.
3. Installieren Sie das Aspose.PDF für .NET-Paket über NuGet, um die erforderlichen Abhängigkeiten hinzuzufügen.

## Konvertieren Sie die CGM-Datei in PDF

Um eine CGM-Datei in PDF zu konvertieren, gehen Sie folgendermaßen vor:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instanziieren Sie ein LoadOption-Objekt mit CGMLoadOption
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Instanziieren Sie ein Document-Objekt
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Speichern Sie das resultierende PDF-Dokument
doc.Save(dataDir + "TECHDRAW_out.pdf");
```

 Stellen Sie sicher, dass Sie im obigen Code ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihre zu konvertierende CGM-Datei befindet. Dieser Code lädt die CGM-Datei mit`CgmLoadOptions` Klasse und erstellt dann ein PDF-Dokument mit der`Document` Objekt. Abschließend wird das resultierende PDF-Dokument gespeichert.

### Beispielquellcode für CGM zu PDF mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie das LoadOption-Objekt mit CGMLoadOption
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Dokumentobjekt instanziieren
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Speichern Sie das resultierende PDF-Dokument
doc.Save(dataDir+ "TECHDRAW_out.pdf");
```

## Abschluss

Herzlichen Glückwunsch! Jetzt wissen Sie, wie Sie mit Aspose.PDF für .NET eine CGM-Datei in PDF konvertieren. Wir haben jeden Schritt des Prozesses durchlaufen, von der Initialisierung der CGM-Ladeoptionen bis zum Speichern des resultierenden PDF-Dokuments. Nutzen Sie die bereitgestellten Codebeispiele, um diese Funktionalität in Ihre eigenen Projekte zu integrieren. Experimentieren Sie mit Aspose.PDF für .NET und entdecken Sie die erweiterten Möglichkeiten, die es für die Bearbeitung von PDF-Dateien bietet.
