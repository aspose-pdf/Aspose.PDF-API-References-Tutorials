---
title: Legen Sie die Dateiinformationen in der PDF-Datei fest
linktitle: Legen Sie die Dateiinformationen in der PDF-Datei fest
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET Dateiinformationen in einer PDF-Datei festlegen.
type: docs
weight: 310
url: /de/net/programming-with-document/setfileinfo/
---
Wenn Sie an einem Projekt arbeiten, das die Verwaltung von PDF-Dateien mit Aspose.PDF für .NET erfordert, ist eine der Funktionen, die Sie möglicherweise nutzen möchten, die Möglichkeit, Dateiinformationen für ein PDF-Dokument festzulegen. Die Dateiinformationen umfassen verschiedene Details wie Autor, Erstellungsdatum, Schlüsselwörter, Änderungsdatum, Betreff und Titel. Dieser Leitfaden führt Sie durch den Prozess des Festlegens von Dateiinformationen für ein PDF-Dokument mithilfe von C#-Quellcode mit Aspose.PDF für .NET.

## Schritt-für-Schritt-Anleitung zum Festlegen von Dateiinformationen mit Aspose.PDF für .NET

1. Erstellen Sie ein neues C#-Projekt in Ihrer Visual Studio-IDE.
2. Fügen Sie in Ihrem Projekt einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.
3. Erstellen Sie ein neues PDF-Dokumentobjekt, indem Sie den Pfad zu der PDF-Datei angeben, deren Dateiinformationen Sie ändern möchten.

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

### Beispielquellcode für Set File Info mit Aspose.PDF für .NET


```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Geben Sie Dokumentinformationen an
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

Zusammenfassend bietet Aspose.PDF für .NET eine einfache und effektive Möglichkeit, Dateiinformationen für PDF-Dokumente festzulegen. Indem Sie die oben genannten Schritte befolgen, können Sie mithilfe des C#-Quellcodes ganz einfach die gewünschten Dateiinformationswerte für Ihre PDF-Dokumente festlegen.

### FAQs zum Festlegen von Dateiinformationen in einer PDF-Datei

#### F: Kann ich zusätzliche Dateiinformationseigenschaften festlegen, die im Beispiel nicht erwähnt werden?

 A: Ja, Sie können mithilfe von zusätzliche Dateiinformationseigenschaften festlegen`DocumentInfo` Objekt in Aspose.PDF für .NET. Der`DocumentInfo`Die Klasse stellt verschiedene Eigenschaften bereit, mit denen Sie zusätzliche Informationen festlegen können, z. B. den Hersteller, die Version und benutzerdefinierte Eigenschaften.

#### F: Ist es möglich, die Dateiinformationen aus einem vorhandenen PDF-Dokument abzurufen?

 A: Ja, Sie können die Dateiinformationen mit Aspose.PDF für .NET aus einem vorhandenen PDF-Dokument abrufen. Dazu können Sie die verwenden`DocumentInfo` -Objekt, um auf die Dateiinformationseigenschaften zuzugreifen und die im PDF-Dokument gespeicherten Informationen zu lesen.

#### F: Ändert das Festlegen der Dateiinformationen das ursprüngliche PDF-Dokument?

A: Nein, das Festlegen der Dateiinformationen mit Aspose.PDF für .NET verändert das ursprüngliche PDF-Dokument nicht. Stattdessen wird ein neues PDF-Dokument mit den aktualisierten Dateiinformationen erstellt. Das ursprüngliche PDF-Dokument bleibt unverändert.