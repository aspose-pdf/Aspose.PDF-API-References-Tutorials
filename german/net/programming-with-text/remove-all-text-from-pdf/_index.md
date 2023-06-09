---
title: Entfernen Sie den gesamten Text aus PDF
linktitle: Entfernen Sie den gesamten Text aus PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET den gesamten Text aus einem PDF-Dokument entfernen.
type: docs
weight: 290
url: /de/net/programming-with-text/remove-all-text-from-pdf/
---

 In diesem Tutorial erklären wir, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET den gesamten Text aus einem PDF-Dokument entfernen. Wir werden den Schritt-für-Schritt-Prozess zum Öffnen einer PDF-Datei mit a durchgehen`TextFragmentAbsorber` um den gesamten Text zu entfernen und das geänderte PDF mit dem bereitgestellten C#-Quellcode zu speichern.

## Anforderungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF für .NET-Bibliothek installiert.
- Ein grundlegendes Verständnis der C#-Programmierung.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein

 Zunächst müssen Sie den Pfad zu dem Verzeichnis festlegen, in dem sich Ihre PDF-Dateien befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu Ihren PDF-Dateien.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument

 Als nächstes öffnen wir das PDF-Dokument mit`Document` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Schritt 3: Entfernen Sie den gesamten Text

 Wir initialisieren a`TextFragmentAbsorber` Objekt und verwenden Sie es, um den gesamten absorbierten Text aus dem PDF-Dokument zu entfernen.

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## Schritt 4: Speichern Sie das geänderte PDF

Abschließend speichern wir das geänderte PDF-Dokument in der angegebenen Ausgabedatei.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Beispielquellcode für „Gesamten Text aus PDF entfernen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// TextFragmentAbsorber initiieren
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
// Entfernen Sie den gesamten absorbierten Text
absorber.RemoveAllText(pdfDocument);
// Speichern Sie das Dokument
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET den gesamten Text aus einem PDF-Dokument entfernen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie ein PDF öffnen und den gesamten Text mit a entfernen`TextFragmentAbsorber`, und speichern Sie das geänderte PDF.