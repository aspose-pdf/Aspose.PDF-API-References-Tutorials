---
title: Dateiinformationen in PDF-Datei festlegen
linktitle: Dateiinformationen in PDF-Datei festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET Dateiinformationen in PDF-Dokumenten festlegen. Verbessern Sie Ihre PDFs ganz einfach mit Metadaten.
type: docs
weight: 310
url: /de/net/programming-with-document/setfileinfo/
---
## Einführung

Wenn es um die Verwaltung von PDF-Dateien geht, ist die Kontrolle über die Dokumentmetadaten von entscheidender Bedeutung. Egal, ob Sie Autoreninformationen, Schlüsselwörter oder sogar eine Betreffzeile hinzufügen möchten, Aspose.PDF für .NET bietet eine nahtlose Möglichkeit, Dateiinformationen in Ihren PDF-Dokumenten festzulegen. Dieses Tutorial führt Sie Schritt für Schritt durch den Prozess und stellt sicher, dass Sie jeden Teil des Codes verstehen, während wir fortfahren. Also schnappen Sie sich Ihren Programmierhut und tauchen Sie ein in die Welt der PDF-Manipulation!

## Voraussetzungen

Bevor wir beginnen, müssen Sie einige Dinge vorbereitet haben:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Hier schreiben und führen Sie Ihren .NET-Code aus.
   
2.  Aspose.PDF für .NET: Sie müssen die Aspose.PDF-Bibliothek herunterladen und installieren. Sie erhalten sie von der[Aspose Downloads-Seite](https://releases.aspose.com/pdf/net/).

3. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, können Sie die von uns verwendeten Codeausschnitte besser verstehen.

4.  Eine PDF-Datei: Halten Sie eine Beispiel-PDF-Datei bereit, die Sie ändern möchten. In diesem Tutorial nennen wir sie`SetFileInfo.pdf`.

Sobald Sie alles eingerichtet haben, können wir mit dem Code loslegen!

## Pakete importieren

Um zu beginnen, müssen Sie die erforderlichen Pakete importieren, die Ihnen die Arbeit mit PDF-Dateien ermöglichen. Fügen Sie in Ihrem C#-Projekt oben in Ihrer Codedatei die folgenden using-Direktiven hinzu:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
```

Diese Namespaces bieten Zugriff auf die Klassen und Methoden, die zur effektiven Bearbeitung von PDF-Dokumenten erforderlich sind.

## Schritt 1: Definieren Sie das Dokumentverzeichnis

Als Erstes müssen Sie das Verzeichnis angeben, in dem sich Ihre PDF-Datei befindet. Dies ist wichtig, da Sie die Datei von diesem Pfad aus öffnen.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Erklärung: Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Ordner mit Ihrem`SetFileInfo.pdf`. Dadurch teilt Ihr Programm mit, wo es nach der PDF-Datei suchen soll.

## Schritt 2: Öffnen Sie das PDF-Dokument

 Öffnen Sie nun das PDF-Dokument, das Sie ändern möchten. Dies geschieht mit dem`Document` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

 Erklärung: Hier erstellen wir eine neue Instanz des`Document`Klasse und übergeben Sie den Pfad der PDF-Datei. Dadurch wird das Dokument in den Speicher geladen und ist zur Bearbeitung bereit.

## Schritt 3: Dokument-Info-Objekt erstellen

Nachdem wir das Dokument nun geöffnet haben, müssen wir ein Objekt erstellen, das die Dokumentinformationen enthält.

```csharp
// Dokumentinformationen angeben
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

 Erläuterung: Die`DocumentInfo` Mit der Klasse können wir verschiedene Metadateneigenschaften für das PDF festlegen. Dieses Objekt wird zum Speichern von Informationen wie Autor, Erstellungsdatum und mehr verwendet.

## Schritt 4: Dokument-Metadaten festlegen

 Mit dem`DocumentInfo` Objekt fertig, es ist an der Zeit, es mit den relevanten Metadaten zu füllen. Hier können Sie den Autor, das Erstellungsdatum, Schlüsselwörter, das Änderungsdatum, den Betreff und den Titel des Dokuments angeben.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

 Erklärung: Jede Zeile legt eine bestimmte Eigenschaft des Dokuments fest. Zum Beispiel:`docInfo.Author` setzt den Namen des Autors, während`docInfo.CreationDate` legt das Datum fest, an dem das Dokument erstellt wurde. Sie können diese Werte nach Bedarf anpassen.

## Schritt 5: Speichern Sie das Dokument

Nach dem Festlegen der gewünschten Metadaten besteht der nächste Schritt darin, das geänderte PDF zu speichern. Sie müssen einen neuen Pfad für die Ausgabedatei angeben.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
// Ausgabedokument speichern
pdfDocument.Save(dataDir);
```

 Erklärung: Hier hängen wir`_out.pdf` zum ursprünglichen Dateinamen, um eine neue Datei für das geänderte Dokument zu erstellen. Der`Save` Die Methode schreibt dann die Änderungen in diese neue Datei.

## Schritt 6: Bestätigen Sie die Änderungen

Abschließend sollten Sie immer bestätigen, dass die Informationen korrekt eingegeben wurden. Dies können Sie tun, indem Sie eine Erfolgsmeldung auf der Konsole ausgeben.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Erklärung: Diese Zeile gibt eine Meldung aus, die angibt, dass die Datei erfolgreich gespeichert wurde, zusammen mit dem Pfad zur neuen Datei. So können Sie einfach sicherstellen, dass alles nach Plan gelaufen ist.

## Abschluss

Das Festlegen von Dateiinformationen in PDF-Dokumenten mit Aspose.PDF für .NET ist ein unkomplizierter Vorgang, der die Benutzerfreundlichkeit Ihrer PDFs erheblich verbessern kann. Indem Sie diese Schritte befolgen, können Sie ganz einfach Metadaten wie Autor, Erstellungsdatum und mehr hinzufügen und so Ihre Dokumente informativer und professioneller gestalten. Egal, ob Sie Anwendungen entwickeln, die PDFs generieren, oder einfach Ihre Dokumente besser verwalten müssen, Aspose.PDF bietet die Tools, die Sie benötigen, um die Arbeit effizient zu erledigen.

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können.

### Kann ich Aspose.PDF kostenlos nutzen?
 Ja, Aspose bietet eine kostenlose Testversion an, mit der Sie die Bibliothek testen können. Besuchen Sie die[Seite „Kostenlose Testversion“](https://releases.aspose.com/) für weitere Informationen.

### Wo finde ich die Dokumentation?
 Die vollständige Dokumentation für Aspose.PDF finden Sie[Hier](https://reference.aspose.com/pdf/net/).

### Wie kaufe ich Aspose.PDF?
 Sie können die Lizenz für Aspose.PDF erwerben über die[Kaufseite](https://purchase.aspose.com/buy).

### Was ist, wenn ich Unterstützung brauche?
Wenn Sie Fragen haben oder Hilfe benötigen, besuchen Sie bitte die[Aspose Support Forum](https://forum.aspose.com/c/pdf/10).