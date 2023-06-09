---
title: Konvertieren Sie den Bildstream in PDF
linktitle: Konvertieren Sie den Bildstream in PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Konvertieren Sie mit Aspose.PDF für .NET ganz einfach einen Bildstream in eine PDF-Datei.
type: docs
weight: 70
url: /de/net/programming-with-images/convert-image-stream-to-pdf/
---

In dieser Anleitung erfahren Sie Schritt für Schritt, wie Sie mit Aspose.PDF für .NET einen Bildstream in eine PDF-Datei konvertieren. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Bevor Sie beginnen, stellen Sie sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im Code den Pfad zu dem Verzeichnis ein, in dem sich Ihr Bild befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Instanziieren Sie ein Document-Objekt

 In diesem Schritt werden wir a instanziieren`Document` Objekt mit dem leeren Konstruktor des`Aspose.Pdf.Document` Klasse.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Schritt 3: Fügen Sie dem PDF-Dokument eine Seite hinzu

 Fügen Sie mit dem eine Seite zum PDF-Dokument hinzu`Add` Methode der`Pages` Gegenstand von`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## Schritt 4: Lesen Sie den Bildstream

 In diesem Schritt erstellen wir eine`FileStream` Objekt zum Lesen der Bilddatei aus dem Stream.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## Schritt 5: Lesen Sie das Bild in ein Byte-Array ein

 Lesen Sie das Bild aus dem Stream und speichern Sie es mithilfe von in einem Byte-Array`Read` Methode der`fs` Objekt.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## Schritt 6: Erstellen Sie ein MemoryStream-Objekt aus dem Byte-Array

 Ein ... kreieren`MemoryStream` Objekt aus dem Byte-Array, das das Bild enthält.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## Schritt 7: Erstellen Sie ein Bildobjekt

 In diesem Schritt erstellen wir eine`Image` Objekt mit der`Aspose.Pdf.Image` Klasse. Geben Sie den Stream des Bildes mit an`ImageStream` Eigentum und übergeben Sie die`ms` Objekt, das wir zuvor erstellt haben.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## Schritt 8: Fügen Sie das Image-Objekt zur Paragraphs-Sammlung hinzu

 Ergänzen Sie die`imageht` Einspruch gegen die`Paragraphs` Sammlung der`sec` Abschnitt.

```csharp
sec.Paragraphs.Add(imageht);
```

## Schritt 9: Speichern Sie das PDF-Dokument

 Speichern Sie das PDF-Dokument mit`Save` Methode der`pdf1` Objekt. Geben Sie den Ausgabepfad der PDF-Datei an.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## Schritt 10: Schließen Sie das MemoryStream-Objekt

 Schließe`ms` Objekt mit der`Close` Methode zur Freigabe der Ressourcen.

```csharp
ms. Close();
```

### Beispielquellcode für die Konvertierung von Bildstreams in PDF mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Instanziieren Sie eine Dokumentinstanz, indem Sie ihren leeren Konstruktor aufrufen
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Fügen Sie dem PDF-Dokument eine Seite hinzu
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// Erstellen Sie ein FileStream-Objekt, um die Bilddatei zu lesen
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// Lesen Sie das Bild in ein Byte-Array ein
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// Erstellen Sie ein MemoryStream-Objekt aus dem Bild-Byte-Array
MemoryStream ms = new MemoryStream(data);
// Erstellen Sie ein Bildobjekt
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// Geben Sie die Bildquelle als MemoryStream an
imageht.ImageStream = ms;
// Fügen Sie ein Bildobjekt zur Paragraphs-Sammlung des Abschnitts hinzu
sec.Paragraphs.Add(imageht);
// Speichern Sie das PDF
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// Schließen Sie das MemoryStream-Objekt
ms.Close();
```

## Abschluss

Herzlichen Glückwunsch! Sie haben einen Bildstream mit Aspose.PDF für .NET erfolgreich in eine PDF-Datei konvertiert. Die generierte PDF-Datei wird im angegebenen Verzeichnis gespeichert. Sie können diese PDF-Datei nun in Ihren Projekten oder Anwendungen verwenden.