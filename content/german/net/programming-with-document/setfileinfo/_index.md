---
title: Dateiinformationen in PDF-Datei festlegen
linktitle: Dateiinformationen in PDF-Datei festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET Dateiinformationen in einer PDF-Datei festlegen.
type: docs
weight: 310
url: /de/net/programming-with-document/setfileinfo/
---
Wenn Sie an einem Projekt arbeiten, bei dem PDF-Dateien mit Aspose.PDF für .NET verwaltet werden müssen, ist eine der Funktionen, die Sie möglicherweise nutzen möchten, die Möglichkeit, Dateiinformationen für ein PDF-Dokument festzulegen. Die Dateiinformationen umfassen verschiedene Details wie Autor, Erstellungsdatum, Schlüsselwörter, Änderungsdatum, Betreff und Titel. Diese Anleitung führt Sie durch den Prozess zum Festlegen von Dateiinformationen für ein PDF-Dokument mithilfe von C#-Quellcode mit Aspose.PDF für .NET.

## Schritt-für-Schritt-Anleitung zum Festlegen von Dateiinformationen mit Aspose.PDF für .NET

1. Erstellen Sie ein neues C#-Projekt in Ihrer Visual Studio IDE.
2. Fügen Sie in Ihrem Projekt einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu.
3. Erstellen Sie ein neues PDF-Dokumentobjekt, indem Sie den Pfad zur PDF-Datei angeben, für die Sie die Dateiinformationen ändern möchten.

## Schritt 1: Pfad zum Dokumentenverzeichnis festlegen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument

```csharp
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Schritt 3: Verwenden Sie das DocumentInfo-Objekt, um auf die Dateiinformationen des PDF-Dokuments zuzugreifen.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Schritt 4: Legen Sie die gewünschten Dateiinformationswerte mithilfe der Eigenschaften des DocumentInfo-Objekts fest.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Schritt 5: Speichern Sie das aktualisierte PDF-Dokument am angegebenen Speicherort.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Schritt 6: Überprüfen Sie, ob die Dateiinformationen erfolgreich aktualisiert wurden.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Sie haben mit Aspose.PDF für .NET erfolgreich Dateiinformationen für ein PDF-Dokument festgelegt.

### Beispielquellcode zum Festlegen von Dateiinformationen mit Aspose.PDF für .NET


```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Dokumentinformationen angeben
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Ausgabedokument speichern
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Abschluss

Zusammenfassend lässt sich sagen, dass Aspose.PDF für .NET eine einfache und effektive Möglichkeit bietet, Dateiinformationen für PDF-Dokumente festzulegen. Indem Sie die oben genannten Schritte befolgen, können Sie die gewünschten Dateiinformationswerte für Ihre PDF-Dokumente mithilfe von C#-Quellcode problemlos festlegen.

### FAQs zum Festlegen von Dateiinformationen in einer PDF-Datei

#### F: Kann ich zusätzliche Dateiinformationseigenschaften festlegen, die im Beispiel nicht erwähnt werden?

 A: Ja, Sie können zusätzliche Dateiinformationseigenschaften festlegen, indem Sie`DocumentInfo` Objekt in Aspose.PDF für .NET. Das`DocumentInfo`Die Klasse bietet verschiedene Eigenschaften, mit denen Sie zusätzliche Informationen wie Hersteller, Version und benutzerdefinierte Eigenschaften festlegen können.

#### F: Ist es möglich, die Dateiinformationen aus einem vorhandenen PDF-Dokument abzurufen?

 A: Ja, Sie können die Dateiinformationen aus einem vorhandenen PDF-Dokument mit Aspose.PDF für .NET abrufen. Dazu können Sie das`DocumentInfo` -Objekt, um auf die Dateiinformationseigenschaften zuzugreifen und die im PDF-Dokument gespeicherten Informationen zu lesen.

#### F: Wird durch das Festlegen der Dateiinformationen das ursprüngliche PDF-Dokument geändert?

A: Nein, das Festlegen der Dateiinformationen mit Aspose.PDF für .NET ändert das ursprüngliche PDF-Dokument nicht. Stattdessen wird ein neues PDF-Dokument mit den aktualisierten Dateiinformationen erstellt. Das ursprüngliche PDF-Dokument bleibt unverändert.