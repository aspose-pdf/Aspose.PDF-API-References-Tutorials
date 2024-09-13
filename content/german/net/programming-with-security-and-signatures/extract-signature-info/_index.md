---
title: Signaturinformationen extrahieren
linktitle: Signaturinformationen extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET digitale Signaturen und Zertifikatsinformationen aus PDF-Dokumenten extrahieren. Eine vollständige Schritt-für-Schritt-Anleitung für C#-Entwickler.
type: docs
weight: 80
url: /de/net/programming-with-security-and-signatures/extract-signature-info/
---
## Einführung

In der heutigen digitalen Welt ist die Gewährleistung der Sicherheit und Integrität von Dokumenten von entscheidender Bedeutung. Eine der gängigen Methoden zum Sichern von PDFs ist das Hinzufügen einer digitalen Signatur. Das Abrufen und Überprüfen der Signaturdetails kann jedoch manchmal eine Herausforderung sein, insbesondere wenn Sie mit verschiedenen Zertifikaten arbeiten. In diesem Handbuch führen wir Sie durch den Prozess des Extrahierens von Signaturinformationen aus PDF-Dokumenten mit Aspose.PDF für .NET und machen die Aufgabe zu einem Kinderspiel. Sie erfahren, wie Sie auf Signaturfelder zugreifen, Zertifikatsinformationen extrahieren und in einer Datei speichern.

## Voraussetzungen

Bevor wir beginnen, stellen wir sicher, dass Sie alles für den Start bereit haben.

-  Aspose.PDF für .NET-Bibliothek: Wenn Sie es noch nicht haben, können Sie es von der[Aspose.PDF für .NET-Downloadseite](https://releases.aspose.com/pdf/net/). 
- .NET-Entwicklungsumgebung: Sie benötigen eine IDE wie Visual Studio.
- Grundlegende C#-Kenntnisse: Zum Verständnis der Codeausschnitte in diesem Tutorial sind Kenntnisse in C# hilfreich.
- PDF-Dokument mit digitaler Signatur: Stellen Sie zu Testzwecken sicher, dass Sie über eine PDF-Datei verfügen, die mindestens eine digitale Signatur enthält.

## Importieren erforderlicher Namespaces

Bevor Sie mit dem Code beginnen, müssen Sie die erforderlichen Namespaces importieren. Mit diesen Namespaces können Sie auf die Aspose.PDF-Funktionalität zugreifen und mit PDF-Dokumenten arbeiten.

```csharp
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using System;
```

Nachdem Sie nun die Grundlagen eingerichtet haben, fahren wir mit dem eigentlichen Vorgang fort: dem Extrahieren von Signaturinformationen aus einer PDF-Datei.

## Schritt 1: Einrichten des Dokumentverzeichnisses

 Bevor Sie an einem PDF-Dokument arbeiten, müssen Sie den Speicherort der zu verwendenden Datei angeben. Sie können ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad des Verzeichnisses, in dem Ihre PDFs gespeichert sind.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

Hier geben wir das Verzeichnis an, in dem sich die PDF-Datei befindet, sowie den Dateinamen selbst. Stellen Sie sicher, dass die Datei in diesem Verzeichnis vorhanden ist!

## Schritt 2: Laden des PDF-Dokuments

 Nachdem Sie nun Ihr Verzeichnis eingerichtet haben, besteht der nächste Schritt darin, das PDF-Dokument mit dem`Document` Klasse von Aspose.PDF.

```csharp
using (Document pdfDocument = new Document(input))
{
    // Hier das PDF verarbeiten.
}
```

 Diese Codezeile initialisiert eine`Document`Objekt, das die PDF-Datei darstellt. Das`using` Anweisung stellt sicher, dass die Ressourcen nach der Verarbeitung des Dokuments bereinigt werden.

## Schritt 3: Auf Formularfelder zugreifen

In diesem Schritt durchlaufen wir alle Formularfelder im PDF-Dokument. Da Signaturen normalerweise als Formularfelder gespeichert werden, hilft uns dieser Schritt dabei, die Signaturfelder zu identifizieren.

```csharp
foreach (Field field in pdfDocument.Form)
{
    // Signaturfelder hier identifizieren.
}
```

 Durch Iteration durch die`Form` Eigentum der`Document` Objekt können wir jedes Formularfeld untersuchen, um zu überprüfen, ob es ein Signaturfeld ist.

## Schritt 4: Signaturfelder identifizieren

 Nachdem Sie auf die Formularfelder zugegriffen haben, müssen Sie im nächsten Schritt feststellen, welche davon Signaturfelder sind. Dies können wir tun, indem wir jedes Feld in ein`SignatureField` Objekt.

```csharp
SignatureField sf = field as SignatureField;
if (sf != null)
{
    // Signaturinformationen extrahieren.
}
```

 Hier verwenden wir die`as` Schlüsselwort, um zu versuchen, jedes Formularfeld in ein`SignatureField`Wenn der Cast erfolgreich ist, wissen wir, dass das Feld eine Signatur ist.

## Schritt 5: Extrahieren des Zertifikats

Nachdem Sie nun das Signaturfeld identifiziert haben, besteht die nächste Aufgabe darin, das Zertifikat aus der Signatur zu extrahieren. Zertifikate enthalten wichtige Informationen über den Unterzeichner und die Gültigkeit der Signatur.

```csharp
Stream cerStream = sf.ExtractCertificate();
```

 Der`ExtractCertificate` Methode gibt einen`Stream` Objekt, das die Zertifikatsdaten enthält. Dieser Stream kann verwendet werden, um das Zertifikat zur weiteren Analyse oder Speicherung zu speichern.

## Schritt 6: Speichern des Zertifikats in einer Datei

 Nachdem Sie das Zertifikat extrahiert haben, müssen Sie es im letzten Schritt in einer Datei speichern. In diesem Fall speichern wir das Zertifikat als`.cer` Datei.

```csharp
if (cerStream != null)
{
    using (cerStream)
    {
        byte[] bytes = new byte[cerStream.Length];
        using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
        {
            cerStream.Read(bytes, 0, bytes.Length);
            fs.Write(bytes, 0, bytes.Length);
        }
    }
}
```

In diesem Codeblock führen wir Folgendes aus:

1. Überprüfen Sie, ob der Zertifikatsstrom nicht null ist.
2. Lesen Sie die Zertifikatsdaten in ein Byte-Array.
3.  Schreiben Sie das Byte-Array in ein`.cer` Datei im Dokumentverzeichnis.

## Abschluss

Das Extrahieren digitaler Signaturen und der zugehörigen Zertifikatsinformationen aus PDF-Dokumenten mit Aspose.PDF für .NET ist recht unkompliziert, wenn man es in einfache Schritte unterteilt. Egal, ob Sie Dokumente prüfen, Signaturen verifizieren oder einfach nur Zertifikate zur sicheren Aufbewahrung speichern, dieses Tutorial vermittelt Ihnen das Wissen, um dies effizient zu erledigen. Denken Sie daran, dass das Sichern und Verifizieren von Dokumenten in der heutigen digitalen Welt von entscheidender Bedeutung ist und die Verwendung von Tools wie Aspose.PDF für .NET die Handhabung erheblich vereinfacht.

## Häufig gestellte Fragen

### Kann ich mit Aspose.PDF für .NET mehrere Signaturen aus einer PDF extrahieren?
Ja, der Code durchläuft alle Formularfelder im Dokument und ermöglicht Ihnen, mehrere Signaturen zu extrahieren, falls welche vorhanden sind.

### Was passiert, wenn im PDF keine Signatur gefunden wird?
Wenn keine Signaturfelder vorhanden sind, überspringt der Code sie einfach, ohne einen Fehler zu verursachen.

### Kann ich mit diesem Ansatz die Gültigkeit einer Signatur überprüfen?
Sie können zwar das Zertifikat extrahieren, zur Überprüfung der Gültigkeit einer Signatur sind jedoch zusätzliche Schritte erforderlich, beispielsweise die Überprüfung der Vertrauenskette des Zertifikats.

### Ist es möglich, mit Aspose.PDF für .NET Daten aus anderen Formularfeldern zu extrahieren?
Ja, Aspose.PDF ermöglicht Ihnen den Zugriff auf und die Bearbeitung verschiedener Arten von Formularfeldern in einer PDF-Datei, nicht nur von Signaturfeldern.

### Wie kann ich die Details des extrahierten Zertifikats anzeigen?
 Sobald das Zertifikat als`.cer` Datei können Sie sie mit einem beliebigen Zertifikatsbetrachter öffnen oder zur weiteren Überprüfung in einen Systemzertifikatspeicher importieren.