---
title: Gesamten Text in PDF-Datei extrahieren
linktitle: Text AllIn PDF-Datei extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in diesem Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.PDF für .NET ganz einfach Text aus PDF-Dateien extrahieren.
type: docs
weight: 180
url: /de/net/programming-with-text/extract-text-all/
---
## Einführung

Im digitalen Zeitalter ist der Umgang mit PDF-Dokumenten zu einer alltäglichen Aufgabe geworden. Egal, ob Sie Entwickler sind und eine Anwendung zur Dokumentverarbeitung erstellen möchten, oder ein Geschäftsmann, der wichtige Daten extrahieren muss: Wenn Sie wissen, wie Sie effizient Text aus PDF-Dateien extrahieren, können Sie eine Menge Zeit und Energie sparen. In diesem Artikel werden wir uns mit der Verwendung der Aspose.PDF für .NET-Bibliothek befassen – einem leistungsstarken Tool, mit dem Sie schnell und einfach Text aus PDF-Dateien extrahieren können.

## Voraussetzungen

Bevor wir uns in die Einzelheiten der Textextraktion aus PDF-Dateien stürzen, müssen einige grundlegende Voraussetzungen erfüllt sein:

1. .NET Framework: Stellen Sie sicher, dass das .NET Framework auf Ihrem Entwicklungscomputer installiert ist. Aspose.PDF funktioniert nahtlos mit .NET, daher ist die neueste Version von Vorteil.
2. Aspose.PDF-Bibliothek: Sie benötigen die Aspose.PDF für .NET-Bibliothek, um PDF-Manipulationen durchzuführen. Sie können[Laden Sie es hier herunter](https://releases.aspose.com/pdf/net/).
3. Entwicklungsumgebung: Eine IDE wie Visual Studio wird dringend empfohlen. Sie bietet eine benutzerfreundliche Oberfläche zum Schreiben, Erstellen und Debuggen Ihres Codes.
4. Grundkenntnisse in C#: Wenn Sie mit der Programmiersprache C# vertraut sind, können Sie die Codeausschnitte, die wir gleich untersuchen werden, besser verstehen.

Nachdem wir nun unsere Voraussetzungen geklärt haben, importieren wir die erforderlichen Pakete!

## Pakete importieren

Um mit unserem Extraktionsprozess zu beginnen, müssen Sie zunächst die erforderlichen Namespaces in Ihr C#-Projekt importieren. So können Sie das tun:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Diese Namespaces bieten Zugriff auf die für PDF-Vorgänge erforderlichen Klassen und Methoden. 

Lassen Sie uns den Extraktionsprozess in leicht verständliche Schritte unterteilen. Am Ende dieser Anleitung können Sie problemlos Text aus jeder PDF-Datei extrahieren.

## Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein

Als erstes müssen Sie das Verzeichnis angeben, in dem sich Ihre PDF-Datei befindet. Dies ist wichtig, um die Datei zu finden, mit der Sie arbeiten möchten.

Codebeispiel:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen Sie in diesem Snippet einfach`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad, in dem sich Ihre PDF-Datei befindet. Wenn sich Ihre Datei beispielsweise in`C:\Documents` , würden Sie setzen`dataDir` zu diesem Pfad.

## Schritt 2: Öffnen Sie das PDF-Dokument

 Sobald Sie Ihr Verzeichnis festgelegt haben, müssen Sie das PDF-Dokument öffnen, aus dem Sie Text extrahieren möchten. Dies geschieht mit dem`Document` Klasse aus dem Aspose.PDF-Namespace.

Codebeispiel:

```csharp
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

 Achten Sie dabei darauf, dass der Dateiname`ExtractTextAll.pdf` ist richtig. Dies ist die Datei, mit der Sie arbeiten werden, um Text zu extrahieren.

## Schritt 3: Erstellen Sie ein Text Absorber-Objekt

 Der nächste Schritt besteht in der Erstellung eines`TextAbsorber` Objekt. Dies ist das magische Werkzeug, mit dem Sie den gesamten im PDF vorhandenen Text aufnehmen können.

Codebeispiel:

```csharp
// Erstellen Sie ein TextAbsorber-Objekt, um Text zu extrahieren
TextAbsorber textAbsorber = new TextAbsorber();
```

 Durch Initialisieren des`TextAbsorber`bereiten Sie die Extraktion des gesamten Textinhalts aus den PDF-Seiten vor.

## Schritt 4: Absorber für alle Seiten akzeptieren

Jetzt, da Ihr Textabsorber bereit ist, müssen Sie ihn auf allen Seiten des PDF-Dokuments funktionieren lassen. Dadurch wird sichergestellt, dass der Text von jeder einzelnen Seite erfasst wird.

Codebeispiel:

```csharp
// Akzeptieren Sie den Absorber für alle Seiten
pdfDocument.Pages.Accept(textAbsorber);
```

Mit diesem Schritt sagen Sie im Grunde: „Hey, Textabsorber, mach weiter und sammle den gesamten Text von jeder Seite dieses Dokuments!“

## Schritt 5: Den extrahierten Text abrufen

Sobald der Text aufgenommen wurde, ist es Zeit, ihn herauszuziehen. Sie können über eine einfache Eigenschaft auf den extrahierten Text zugreifen.

Codebeispiel:

```csharp
// Holen Sie sich den extrahierten Text
string extractedText = textAbsorber.Text;
```

 Nun die Variable`extractedText` enthält den gesamten Text aus Ihrem PDF. Wie cool ist das denn?

## Schritt 6: Den extrahierten Text in eine Datei schreiben

Abschließend möchten Sie den extrahierten Text wahrscheinlich in einer neuen Textdatei speichern, um später einfach darauf zugreifen zu können. So geht's.

Codebeispiel:

```csharp
// Erstellen Sie einen Writer und öffnen Sie die Datei
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Schreiben Sie eine Textzeile in die Datei
tw.WriteLine(extractedText);
// Schließen Sie den Stream
tw.Close();
```

 Dieser Code öffnet eine neue Datei namens`extracted-text.txt`schreibt den gesamten extrahierten Inhalt hinein und schließt dann die Datei. Wenn Sie jetzt den extrahierten Text sehen möchten, schauen Sie einfach in Ihr Dokumentverzeichnis!

## Abschluss

 Da haben Sie es! In nur wenigen einfachen Schritten können Sie mit Aspose.PDF für .NET Text aus jeder PDF-Datei extrahieren. Egal, ob Sie eine Anwendung zum Analysieren von Dokumenten erstellen oder nur ein paar Notizen aus einer PDF-Datei extrahieren möchten, Aspose.PDF bietet eine robuste, benutzerfreundliche API, die Ihnen das Leben erleichtert. Vergessen Sie nicht, sich die[Dokumentation](https://reference.aspose.com/pdf/net/) für weitere Funktionen und Möglichkeiten, die diese leistungsstarke Bibliothek bietet.

## Häufig gestellte Fragen

### Kann ich Aspose.PDF für .NET kostenlos nutzen?
 Ja, Aspose bietet eine kostenlose Testversion an. Sie können sie herunterladen[Hier](https://releases.aspose.com/).

### Was ist, wenn meine PDF Bilder und Grafiken enthält?
Aspose.PDF konzentriert sich auf die Textextraktion. Wenn Ihr PDF Bilder enthält, benötigen Sie möglicherweise einen anderen Ansatz, um diese zu verarbeiten.

### Ist eine temporäre Lizenz verfügbar?
 Auf jeden Fall! Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).

### Wo erhalte ich Support für Aspose.PDF?
 Support und Community-Diskussionen finden Sie auf der[Aspose-Forum](https://forum.aspose.com/c/pdf/10).

### In welchen Formaten kann ich den extrahierten Text speichern?
 Sie können den Text in verschiedenen Formaten speichern, beispielsweise`.txt`, `.docx`, oder sogar direkt in eine Datenbank.