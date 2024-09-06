---
title: Holen Sie sich die Seitenzahl des Lesezeichens in der PDF-Datei
linktitle: Holen Sie sich die Seitenzahl des Lesezeichens in der PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in diesem umfassenden Tutorial, wie Sie mit Aspose.PDF für .NET Lesezeichenseitenzahlen aus PDF-Dateien extrahieren.
type: docs
weight: 60
url: /de/net/programming-with-bookmarks/get-bookmark-page-number/
---
## Einführung

Im digitalen Zeitalter ist die effiziente Verwaltung von PDF-Dokumenten sowohl für den privaten als auch für den professionellen Gebrauch von entscheidender Bedeutung. Egal, ob Sie Entwickler sind und Ihre Anwendung verbessern möchten, oder ein Geschäftsmann, der seine Dokumente organisieren muss: Wenn Sie wissen, wie Sie PDFs bearbeiten, können Sie Zeit und Mühe sparen. Eine der wichtigsten Funktionen der PDF-Verwaltung ist die Möglichkeit, Lesezeichen und die entsprechenden Seitenzahlen zu extrahieren. In diesem Tutorial erfahren Sie, wie Sie dies mit Aspose.PDF für .NET erreichen können, einer leistungsstarken Bibliothek, die die PDF-Bearbeitung vereinfacht.

## Voraussetzungen

Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Dies wird Ihre Entwicklungsumgebung sein.
2.  Aspose.PDF für .NET: Sie benötigen die Aspose.PDF-Bibliothek. Sie können sie herunterladen von[Webseite](https://releases.aspose.com/pdf/net/).
3. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, verstehen Sie die Codeausschnitte besser.

## Pakete importieren

Um zu beginnen, müssen Sie die erforderlichen Pakete in Ihr C#-Projekt importieren. So können Sie das tun:

1. Öffnen Sie Ihr Visual Studio-Projekt.
2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt und wählen Sie „NuGet-Pakete verwalten“ aus.
3.  Suchen nach`Aspose.PDF` und installieren Sie die neueste Version.

Nachdem Sie nun alles eingerichtet haben, gehen wir den Vorgang zum Extrahieren der Lesezeichen-Seitenzahlen Schritt für Schritt durch.

## Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein

Bevor Sie Lesezeichen extrahieren können, müssen Sie den Pfad zu Ihrem PDF-Dokument angeben. Hier befindet sich Ihre PDF-Datei.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen Sie in diesem Schritt`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem Ihre PDF-Datei gespeichert ist. Dieser Pfad ist entscheidend, da er dem Programm mitteilt, wo es nach der PDF-Datei suchen soll, mit der Sie arbeiten möchten.

## Schritt 2: Erstellen Sie eine PdfBookmarkEditor-Instanz

 Als nächstes müssen Sie eine Instanz des`PdfBookmarkEditor`Klasse. Diese Klasse bietet Methoden zum Bearbeiten von Lesezeichen in PDF-Dateien.

```csharp
// PdfBookmarkEditor erstellen
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

 Hier instantiieren wir die`PdfBookmarkEditor`. Mit diesem Objekt können wir unsere PDF-Datei binden und Lesezeichen daraus extrahieren.

## Schritt 3: Öffnen Sie die PDF-Datei

 Nun ist es an der Zeit, die PDF-Datei an das`PdfBookmarkEditor` Instanz, die Sie gerade erstellt haben.

```csharp
// PDF-Datei öffnen
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 In dieser Zeile verwenden wir die`BindPdf` Methode zum Öffnen der PDF-Datei mit dem Namen`GetBookmarks.pdf`. Stellen Sie sicher, dass diese Datei im angegebenen Verzeichnis vorhanden ist. Andernfalls tritt ein Fehler auf.

## Schritt 4: Lesezeichen extrahieren

 Wenn die PDF-Datei geöffnet ist, können Sie nun die Lesezeichen mit dem`ExtractBookmarks` Verfahren.

```csharp
// Lesezeichen extrahieren
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

 Dieser Schritt ruft alle Lesezeichen aus der PDF-Datei ab und speichert sie in einer Variablen namens`bookmarks`. Diese Variable enthält alle Lesezeicheninformationen, die wir im nächsten Schritt verarbeiten werden.

## Schritt 5: Durch Lesezeichen iterieren

Nachdem Sie nun die Lesezeichen haben, können Sie diese durchlaufen, um ihre Titel und Seitenzahlen anzuzeigen.

```csharp
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
    string strLevelSeprator = string.Empty;
    for (int i = 1; i < bookmark.Level; i++)
    {
        strLevelSeprator += "----";
    }
    Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
    Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
    Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

In dieser Schleife durchlaufen wir jedes Lesezeichen. Für jedes Lesezeichen erstellen wir einen Zeichenfolgentrenner basierend auf seiner Ebene (um die Hierarchie der Lesezeichen visuell darzustellen). Dann drucken wir den Titel, die Seitenzahl und die mit jedem Lesezeichen verknüpfte Aktion auf der Konsole aus.

## Abschluss

Das Extrahieren von Lesezeichenseitenzahlen aus einer PDF-Datei mit Aspose.PDF für .NET ist ein unkomplizierter Vorgang. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie Lesezeichen in Ihren PDF-Dokumenten effizient verwalten. Egal, ob Sie eine Anwendung entwickeln oder einfach nur Ihre PDFs organisieren müssen, dieses Wissen wird Ihnen zweifellos nützlich sein.

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente programmgesteuert zu erstellen, zu bearbeiten und zu konvertieren.

### Kann ich Aspose.PDF kostenlos nutzen?
 Ja, Aspose bietet eine kostenlose Testversion an, mit der Sie die Bibliothek testen können. Sie können sie herunterladen[Hier](https://releases.aspose.com/).

### Wo finde ich die Dokumentation für Aspose.PDF?
 Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/pdf/net/).

### Wie erwerbe ich eine Lizenz für Aspose.PDF?
 Sie können eine Lizenz erwerben bei der[Kaufseite](https://purchase.aspose.com/buy).

### Was soll ich tun, wenn ich auf Probleme stoße?
 Wenn Sie auf Probleme stoßen, können Sie Hilfe suchen auf der[Aspose-Supportforum](https://forum.aspose.com/c/pdf/10).