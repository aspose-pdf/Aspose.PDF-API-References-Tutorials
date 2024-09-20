---
title: Text aus Seitenbereich in PDF-Datei extrahieren
linktitle: Text aus Seitenbereich in PDF-Datei extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET Text aus einem bestimmten Bereich einer PDF-Datei extrahieren. Sammeln und speichern Sie effizient Text aus Ihren Dokumenten.
type: docs
weight: 190
url: /de/net/programming-with-text/extract-text-from-page-region/
---
## Einführung

Beim Arbeiten mit PDFs müssen häufig bestimmte Inhalte extrahiert werden, sei es das Abrufen von Daten aus Formularen, Tabellen oder bestimmten Abschnitten eines Dokuments. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.PDF für .NET Text aus einem bestimmten Bereich einer PDF-Datei extrahieren. Anstatt ein ganzes Dokument zu durchsuchen, ermitteln wir genau, wo sich der Text befindet, und extrahieren ihn effizient.

## Voraussetzungen

Bevor wir uns in den Code stürzen, stellen Sie sicher, dass Sie die folgenden Elemente eingerichtet haben:

1.  Aspose.PDF für .NET: Falls Sie es noch nicht getan haben, laden Sie die Bibliothek Aspose.PDF für .NET herunter und installieren Sie sie.[Laden Sie Aspose.PDF für .NET herunter](https://releases.aspose.com/pdf/net/).
2. IDE: Jede .NET-Entwicklungsumgebung wie Visual Studio.
3. .NET Framework: Stellen Sie sicher, dass Ihr Projekt mit dem entsprechenden .NET Framework eingerichtet ist.
4. PDF-Dokument: Ein Beispiel-PDF, aus dem wir Text extrahieren.

 Vergessen Sie nicht, dass Sie[Kostenlose Testversion erhalten](https://releases.aspose.com/) von Aspose.PDF oder verwenden Sie eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) für die volle Funktionalität.

## Erforderliche Pakete importieren

Um mit Aspose.PDF für .NET arbeiten zu können, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Diese Pakete bieten die erforderlichen Klassen und Methoden für die Handhabung von PDF-Dokumenten.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Schritt 1: Einrichten des Dokumentverzeichnisses und Laden der PDF

Der erste Schritt besteht darin, anzugeben, wo sich Ihre PDF-Datei befindet, und sie in Ihr Projekt zu laden. Sie können einen lokalen Verzeichnispfad zu der PDF-Datei verwenden, mit der Sie arbeiten möchten.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öffnen Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

 Dieser Schritt stellt sicher, dass die PDF-Datei richtig geladen und zur Bearbeitung bereit ist.`Document` Mit der Klasse aus der Aspose.PDF-Bibliothek können Sie die PDF-Datei bearbeiten.

## Schritt 2: Initialisieren Sie den Text Absorber für die Extraktion

 In diesem Schritt erstellen wir eine`TextAbsorber` Objekt, das dazu dient, Text aus einem PDF-Dokument zu extrahieren. Das`TextAbsorber` ist flexibel und kann angepasst werden, um den Fokus auf bestimmte Regionen oder Seiten zu legen.

```csharp
// Erstellen Sie ein TextAbsorber-Objekt zum Extrahieren von Text
TextAbsorber absorber = new TextAbsorber();
```

 Der`TextAbsorber`Klasse ist ein leistungsfähiges Tool, das den gesamten Text innerhalb der von Ihnen angegebenen Grenzen erfasst.

## Schritt 3: Definieren Sie den Bereich, aus dem Text extrahiert werden soll

Und hier geschieht die Magie. Anstatt Text von der gesamten Seite zu extrahieren, können wir die Extraktion auf einen bestimmten rechteckigen Bereich der Seite beschränken. Das ist perfekt, wenn Sie genau wissen, wo sich Ihr Inhalt befindet.

```csharp
// Beschränken Sie die Textextraktion auf einen bestimmten Bereich
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
```

 Der`Rectangle` Objekt können Sie die Koordinaten (in Punkten) des Bereichs definieren, aus dem Text extrahiert wird. Das`TextSearchOptions.LimitToPageBounds` stellt sicher, dass nur Text innerhalb des angegebenen Rechtecks extrahiert wird.

## Schritt 4: Akzeptieren Sie den Absorber auf der gewünschten Seite

 Nach dem Einrichten der Region ist der nächste Schritt die Annahme der`TextAbsorber` für die bestimmte Seite, aus der Sie Text extrahieren möchten. Hier konzentrieren wir uns auf die erste Seite der PDF-Datei.

```csharp
// Akzeptieren Sie den Absorber für die erste Seite
pdfDocument.Pages[1].Accept(absorber);
```

 Durch einen Anruf bei`Accept` Methode auf der Seite weisen wir Aspose.PDF an, den Absorber auszuführen und den Text aus der definierten Region zu sammeln.

## Schritt 5: Abrufen und Speichern des extrahierten Textes

 Sobald der Absorber seine Arbeit erledigt hat, ist es an der Zeit, den extrahierten Text zu sammeln und zu speichern. Dieser Schritt umfasst das Abrufen des Textes und das Schreiben in ein`.txt` Datei.

```csharp
// Holen Sie sich den extrahierten Text
string extractedText = absorber.Text;

// Erstellen Sie einen Writer, um den extrahierten Text zu speichern
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");

// Schreiben Sie den Text in die Datei
tw.WriteLine(extractedText);

// Schließen Sie den Stream
tw.Close();
```

 Hier die`TextWriter` Die Klasse wird verwendet, um den extrahierten Text in eine Textdatei zu schreiben. Dadurch wird sichergestellt, dass Ihr extrahierter Inhalt für die spätere Verwendung sicher gespeichert wird.

## Abschluss

 Das Extrahieren von Text aus einem bestimmten Bereich innerhalb eines PDF-Dokuments kann unglaublich nützlich sein, insbesondere beim Umgang mit strukturierten Inhalten wie Formularen oder Tabellen. Mit Aspose.PDF für .NET können Sie diese Aufgabe mit nur wenigen Codezeilen erledigen. Durch Definieren eines Bereichs, Initialisieren eines`TextAbsorber`, und indem Sie den extrahierten Text speichern, haben Sie die volle Kontrolle darüber, was aus Ihrer PDF-Datei extrahiert wird.

Unabhängig davon, ob Sie an einem kleinen Projekt arbeiten oder große Dokumente verwalten, bietet diese Methode eine effiziente Möglichkeit, relevante Daten aus Ihren PDF-Dateien zu extrahieren, ohne das gesamte Dokument durchkämmen zu müssen.

## Häufig gestellte Fragen

### Kann ich Text aus mehreren Seiten gleichzeitig extrahieren?
 Ja, durch Iteration durch die`Pages` Sammlung der`pdfDocument` können Sie die`TextAbsorber` auf mehrere Seiten.

### Was ist, wenn sich der Text in einem anderen Bereich des PDF befindet?
 Sie können ganz einfach die`Rectangle` Koordinaten, die mit der Region übereinstimmen, in der sich Ihr Text befindet.

### Funktioniert das mit gescannten PDFs?
Nein, gescannte PDFs benötigen OCR (Optical Character Recognition), um Bilder in Text umzuwandeln. Aspose.PDF bietet ebenfalls OCR-Funktionen.

### Gibt es eine Möglichkeit, Text basierend auf bestimmten Schlüsselwörtern zu extrahieren?
 Ja, Sie können`TextFragmentAbsorber` zur stichwortbasierten Textextraktion.

### Wie extrahiere ich Text aus einer verschlüsselten PDF-Datei?
Sie müssen zuerst die PDF-Datei durch Eingabe des richtigen Kennworts entschlüsseln und dann mit der Textextraktion fortfahren.