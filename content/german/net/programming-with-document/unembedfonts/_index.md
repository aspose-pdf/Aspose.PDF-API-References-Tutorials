---
title: Einbettung von Schriftarten aufheben und PDF-Dateien optimieren
linktitle: Einbettung von Schriftarten aufheben und PDF-Dateien optimieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in diesem Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.PDF für .NET die Einbettung von Schriftarten aufheben und PDF-Dateien optimieren.
type: docs
weight: 370
url: /de/net/programming-with-document/unembedfonts/
---
## Einführung

Im digitalen Zeitalter sind PDFs allgegenwärtig. Egal, ob Sie Berichte, Präsentationen oder eBooks teilen, das Portable Document Format (PDF) ist die erste Wahl, um die Integrität Ihrer Dokumente zu wahren. Da wir jedoch immer mehr PDFs erstellen und teilen, können die Dateigrößen ansteigen, was das Senden oder Speichern umständlich macht. Hier kommt Aspose.PDF für .NET ins Spiel und bietet leistungsstarke Tools zur Optimierung Ihrer PDF-Dateien. In diesem Tutorial erfahren Sie, wie Sie Schriftarten ausbetten und PDF-Dateien mit Aspose.PDF für .NET optimieren.

## Voraussetzungen

Bevor wir ins Detail gehen, stellen wir sicher, dass Sie alles haben, was Sie für den Einstieg brauchen:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Dies ist die IDE, die wir zum Schreiben und Ausführen unseres .NET-Codes verwenden.
2.  Aspose.PDF für .NET: Sie müssen die Aspose.PDF-Bibliothek herunterladen und installieren. Sie finden sie im[Downloadlink](https://releases.aspose.com/pdf/net/).
3. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, können Sie die von uns verwendeten Codeausschnitte besser verstehen.
4.  Eine PDF-Datei: Halten Sie eine PDF-Datei bereit, die Sie optimieren möchten. Sie können jede beliebige PDF-Datei verwenden, aber zur Veranschaulichung nennen wir sie`OptimizeDocument.pdf`.

## Pakete importieren

Um zu beginnen, müssen Sie die erforderlichen Pakete in Ihr C#-Projekt importieren. So können Sie das tun:

1. Öffnen Sie Ihr Projekt in Visual Studio.
2. Fügen Sie einen Verweis auf Aspose.PDF hinzu: Klicken Sie mit der rechten Maustaste auf Ihr Projekt im Solution Explorer, wählen Sie „NuGet-Pakete verwalten“ und suchen Sie nach`Aspose.PDF`. Installieren Sie das Paket.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nachdem wir nun alles eingerichtet haben, unterteilen wir den Optimierungsprozess in überschaubare Schritte.

## Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein

Als Erstes müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis definieren. Hier werden Ihre PDF-Dateien gespeichert. So geht's:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem sich Ihre PDF-Datei befindet. Dies ist wichtig, da das Programm wissen muss, wo sich die zu optimierende PDF-Datei befindet.

## Schritt 2: Öffnen Sie das PDF-Dokument

Nachdem wir nun unser Verzeichnis eingerichtet haben, ist es an der Zeit, das PDF-Dokument zu öffnen, das wir optimieren möchten. Hier ist der Code dafür:

```csharp
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 Diese Codezeile erzeugt eine neue`Document` Objekt, das Ihre PDF-Datei darstellt. Stellen Sie sicher, dass der Dateiname mit dem in Ihrem Verzeichnis übereinstimmt.

## Schritt 3: Optimierungsoptionen festlegen

Als nächstes müssen wir die Optimierungsoptionen angeben. In diesem Fall möchten wir die Einbettung von Schriftarten aufheben. So richten Sie das ein:

```csharp
// Option „UnembedFonts“ festlegen
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    UnembedFonts = true
};
```

 Durch die Einstellung`UnembedFonts` Zu`true`weisen wir Aspose.PDF an, das PDF durch Aufheben der Einbettung der Schriftarten zu optimieren. Dies kann die Dateigröße erheblich reduzieren, insbesondere wenn das PDF viele eingebettete Schriftarten enthält.

## Schritt 4: Optimieren Sie das PDF-Dokument

Nachdem wir unsere Optionen festgelegt haben, ist es an der Zeit, das PDF-Dokument zu optimieren. Hier ist der Code dazu:

```csharp
Console.WriteLine("Start");
// Optimieren Sie PDF-Dokumente mit OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

Dieser Codeausschnitt ruft den`OptimizeResources` Methode auf der`pdfDocument` Objekt und wenden Sie die zuvor definierten Optimierungsoptionen an. In der Konsole wird eine Meldung angezeigt, die angibt, dass der Optimierungsprozess gestartet wurde.

## Schritt 5: Speichern Sie das aktualisierte Dokument

Nachdem wir das PDF optimiert haben, müssen wir das aktualisierte Dokument speichern. So geht's:

```csharp
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
```

 Dieser Code speichert das optimierte PDF als`OptimizeDocument_out.pdf` im selben Verzeichnis. Sie können einen anderen Namen wählen, wenn Sie möchten. Wenn der Name jedoch ähnlich ist, können Sie die ursprüngliche und die optimierte Version leichter identifizieren.

## Schritt 6: Dateigrößen vergleichen

Schließlich ist es immer gut zu prüfen, wie viel Speicherplatz Sie gespart haben. So vergleichen Sie die ursprüngliche und die optimierte Dateigröße:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Dieser Code ruft die Dateigrößen der ursprünglichen und der optimierten PDF-Datei ab und gibt sie auf der Konsole aus. Es ist ein befriedigender Moment zu sehen, wie sehr Sie die Dateigröße reduziert haben!

## Abschluss

Und da haben Sie es! Sie haben erfolgreich eingebettete Schriftarten entfernt und eine PDF-Datei mit Aspose.PDF für .NET optimiert. Dieser Vorgang hilft nicht nur bei der Reduzierung der Dateigröße, sondern verbessert auch die Leistung Ihrer PDF-Dokumente. Egal, ob Sie Dateien per E-Mail freigeben oder in der Cloud speichern, eine kleinere Dateigröße kann einen großen Unterschied machen.

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler PDF-Dokumente programmgesteuert erstellen, bearbeiten und optimieren können.

### Kann ich Aspose.PDF kostenlos nutzen?
 Ja, Aspose bietet eine kostenlose Testversion an. Sie können sie hier herunterladen:[Hier](https://releases.aspose.com/).

### Wie erhalte ich Support für Aspose.PDF?
 Unterstützung erhalten Sie durch die[Aspose-Forum](https://forum.aspose.com/c/pdf/10).

### Welche Arten von Optimierungen kann ich an PDFs durchführen?
Sie können Schriftarten ausbetten, Bilder komprimieren, nicht verwendete Objekte entfernen und vieles mehr, um Ihre PDF-Dateien zu optimieren.

### Wo kann ich Aspose.PDF für .NET kaufen?
 Sie können eine Lizenz erwerben bei der[Aspose-Kaufseite](https://purchase.aspose.com/buy).