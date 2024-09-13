---
title: Passen Sie die Seitenzahlen beim Hinzufügen des Inhaltsverzeichnisses an
linktitle: Passen Sie die Seitenzahlen beim Hinzufügen des Inhaltsverzeichnisses an
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in diesem umfassenden Tutorial, wie Sie mit Aspose.PDF für .NET Seitenzahlen anpassen, während Sie Ihren PDF-Dokumenten ein Inhaltsverzeichnis hinzufügen.
type: docs
weight: 100
url: /de/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
## Einführung

In der Welt des Dokumentenmanagements sind PDFs unangefochtener König. Sie sind das Standardformat zum Teilen und Aufbewahren von Dokumenten auf verschiedenen Plattformen. Aber was passiert, wenn Sie Ihre PDF-Dokumente mit Funktionen wie einem Inhaltsverzeichnis (TOC) erweitern möchten? Hier kommt Aspose.PDF für .NET ins Spiel! Mit dieser leistungsstarken Bibliothek können Entwickler PDF-Dateien problemlos bearbeiten und Inhalte mühelos hinzufügen, ändern und anpassen. In diesem Tutorial erfahren Sie, wie Sie Seitenzahlen anpassen und gleichzeitig mit Aspose.PDF für .NET ein Inhaltsverzeichnis zu Ihren PDF-Dokumenten hinzufügen. Also, schnappen Sie sich Ihren Programmierhut und legen Sie los!

## Voraussetzungen

Bevor wir uns in den Code stürzen, müssen einige Dinge bereitstehen:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Dies wird unsere Entwicklungsumgebung sein.
2. Aspose.PDF für .NET: Sie müssen die Aspose.PDF-Bibliothek herunterladen und installieren. Sie finden sie[Hier](https://releases.aspose.com/pdf/net/).
3. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, verstehen Sie die Codeausschnitte besser.
4. Eine Beispiel-PDF-Datei: Halten Sie eine Beispiel-PDF-Datei bereit, mit der wir arbeiten können. Sie können eine einfache Datei erstellen oder eine vorhandene PDF-Datei herunterladen.

## Pakete importieren

Um zu beginnen, müssen wir die erforderlichen Pakete importieren. Öffnen Sie Ihr Visual Studio-Projekt und fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek hinzu. Sie können dies mithilfe des NuGet-Paket-Managers tun:

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt.
2. Wählen Sie „NuGet-Pakete verwalten“ aus.
3. Suchen Sie nach „Aspose.PDF“ und installieren Sie es.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Sobald Sie die Bibliothek installiert haben, können Sie mit dem Codieren beginnen!

## Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein

Als Erstes müssen wir unser Dokumentverzeichnis einrichten. Hier werden wir unsere Eingabe- und Ausgabe-PDF-Dateien speichern. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
```

Ersetzen Sie in diesem Snippet`YOUR DOCUMENT DIRECTORY` mit dem tatsächlichen Pfad, in dem sich Ihre PDF-Dateien befinden. Dies hilft uns, das vorhandene PDF zu laden und die geänderte Version zu speichern.

## Schritt 2: Laden Sie die vorhandene PDF-Datei

Nachdem wir nun unser Dokumentverzeichnis eingerichtet haben, laden wir die vorhandene PDF-Datei. 

```csharp
Document doc = new Document(inFile);
```

 Hier erstellen wir ein neues`Document` Objekt, indem wir den Eingabedateipfad übergeben. Dadurch können wir den PDF-Inhalt programmgesteuert bearbeiten.

## Schritt 3: Einfügen einer neuen Seite für das Inhaltsverzeichnis

Als Nächstes müssen wir in unserem PDF eine neue Seite erstellen, auf der das Inhaltsverzeichnis gespeichert wird.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

Diese Zeile fügt am Anfang des Dokuments eine neue Seite ein. Das Inhaltsverzeichnis wird auf dieser Seite angezeigt.

## Schritt 4: Inhaltsverzeichnisinformationen erstellen

Erstellen wir nun ein Objekt zur Darstellung der Inhaltsverzeichnisinformationen.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

 In diesem Schritt erstellen wir eine`TocInfo` Objekt und setzen seinen Titel auf "Inhaltsverzeichnis". Wir passen auch die Schriftgröße und den Stil an. Das`PageNumbersPrefix` ist auf „P“ eingestellt, wodurch den Seitenzahlen im Inhaltsverzeichnis ein Präfix vorangestellt wird.

## Schritt 5: Überschriften zum Inhaltsverzeichnis hinzufügen

Jetzt kommt der spaßige Teil! Wir durchlaufen die Seiten des Dokuments und fügen unserem Inhaltsverzeichnis Überschriften hinzu.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    heading2.DestinationPage = doc.Pages[i + 1];
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    segment2.Text = "Page " + i.ToString();
    tocPage.Paragraphs.Add(heading2);
}
```

 In dieser Schleife erstellen wir eine neue`Heading` Objekt für jede Seite. Wir legen die Zielseite für jede Überschrift fest und geben den anzuzeigenden Text an, nämlich „Seite X“, wobei X die Seitenzahl ist. Schließlich fügen wir die Überschrift zur Inhaltsverzeichnisseite hinzu.

## Schritt 6: Speichern Sie das aktualisierte Dokument

Nachdem wir alle erforderlichen Überschriften hinzugefügt haben, ist es an der Zeit, unser aktualisiertes Dokument zu speichern.

```csharp
doc.Save(outFile);
```

Diese Zeile speichert die geänderte PDF-Datei mit dem Inhaltsverzeichnis. Sie können nun die Ausgabedatei öffnen und Ihr angepasstes Inhaltsverzeichnis anzeigen!

## Abschluss

Und da haben Sie es! Sie haben erfolgreich Seitenzahlen angepasst, während Sie Ihrem PDF-Dokument mit Aspose.PDF für .NET ein Inhaltsverzeichnis hinzugefügt haben. Diese leistungsstarke Bibliothek erleichtert die Bearbeitung von PDF-Dateien und mit nur wenigen Codezeilen können Sie Ihre Dokumente erheblich verbessern. Egal, ob Sie Berichte, eBooks oder andere PDF-Dateien erstellen, ein Inhaltsverzeichnis kann die Navigation für Ihre Leser erheblich verbessern. Also, worauf warten Sie noch? Tauchen Sie ein in Aspose.PDF und beginnen Sie noch heute mit der Erstellung fantastischer PDFs!

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente programmgesteuert zu erstellen, zu bearbeiten und zu konvertieren.

### Kann ich Aspose.PDF kostenlos nutzen?
 Ja, Aspose bietet eine kostenlose Testversion an, mit der Sie die Funktionen der Bibliothek erkunden können. Sie können sie herunterladen[Hier](https://releases.aspose.com/).

### Wie erhalte ich Support für Aspose.PDF?
 Sie können Unterstützung erhalten, indem Sie das Aspose-Forum besuchen[Hier](https://forum.aspose.com/c/pdf/10).

### Ist eine temporäre Lizenz verfügbar?
 Ja, Sie können eine temporäre Lizenz für Aspose.PDF anfordern[Hier](https://purchase.aspose.com/temporary-license/).

### Wo kann ich Aspose.PDF für .NET kaufen?
 Sie können Aspose.PDF für .NET kaufen[Hier](https://purchase.aspose.com/buy).