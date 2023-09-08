---
title: Dokumentfenster abrufen
linktitle: Dokumentfenster abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie die GetDocumentWindow-Funktion von Aspose.PDF für .NET verwenden, um Informationen über die Fenstereigenschaften eines PDF-Dokuments abzurufen.
type: docs
weight: 170
url: /de/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF für .NET ist eine leistungsstarke PDF-Bearbeitungsbibliothek, mit der Entwickler PDF-Dateien in ihren .NET-Anwendungen erstellen, bearbeiten und konvertieren können. Eine der Funktionen dieser Bibliothek ist die Möglichkeit, Informationen über die Fenstereigenschaften eines Dokuments abzurufen. Dieses Tutorial führt Sie durch die Schritte zur Verwendung des`GetDocumentWindow` Funktion von Aspose.PDF für .NET zum Abrufen von Informationen über die Fenstereigenschaften eines PDF-Dokuments.

## Schritt 1: Installieren Sie Aspose.PDF für .NET

 Um Aspose.PDF für .NET in Ihren .NET-Anwendungen verwenden zu können, müssen Sie zunächst die Bibliothek installieren. Sie können die neueste Version der Bibliothek von herunterladen[Aspose.PDF für .NET-Downloadseite](https://releases.aspose.com/pdf/net).

Nachdem Sie die Bibliothek heruntergeladen haben, extrahieren Sie den Inhalt der ZIP-Datei in einen Ordner auf Ihrem Computer. Anschließend müssen Sie in Ihrem .NET-Projekt einen Verweis auf die Aspose.PDF für .NET-DLL hinzufügen.

## Schritt 2: Laden Sie das PDF-Dokument

Sobald Sie Aspose.PDF für .NET installiert und einen Verweis auf die DLL in Ihrem .NET-Projekt hinzugefügt haben, können Sie mit der Verwendung beginnen`GetDocumentWindow` Funktion zum Abrufen von Informationen über die Fenstereigenschaften eines PDF-Dokuments.

Der erste Schritt bei der Verwendung dieser Funktion besteht darin, das PDF-Dokument zu laden, zu dem Sie Informationen abrufen möchten. Dazu können Sie den folgenden Code verwenden:

```csharp
// Der Pfad zum PDF-Dokument
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Öffnen Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 Ersetzen Sie im obigen Code`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet. Dieser Code lädt das PDF-Dokument in ein`Document` Objekt, mit dem Sie dann Informationen über die Fenstereigenschaften des Dokuments abrufen können.

## Schritt 3: Rufen Sie die Fenstereigenschaften des Dokuments ab

Um Informationen zu den Fenstereigenschaften eines PDF-Dokuments abzurufen, können Sie den folgenden Code verwenden:

```csharp
// Rufen Sie die Fenstereigenschaften des Dokuments ab
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

Im obigen Code ruft jede Zeile eine andere Fenstereigenschaft des PDF-Dokuments ab und gibt sie an die Konsole aus. Sie können diesen Code anpassen, um nur die Eigenschaften abzurufen, an denen Sie interessiert sind.

### Beispielquellcode zum Abrufen des Dokumentfensters einer PDF-Datei mit Aspose.PDF für .NET 

 Hier ist der vollständige Quellcode zum Abrufen der Fenstereigenschaften eines PDF-Dokuments mithilfe von`GetDocumentWindow` Funktion von Aspose.PDF für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Erhalten Sie verschiedene Dokumenteigenschaften
// Position des Dokumentfensters – Standard: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Vorherrschende Lesereihenfolge; bestimmt die Position der Seite
// Wenn nebeneinander angezeigt – Standard: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Ob in der Titelleiste des Fensters der Dokumenttitel angezeigt werden soll
// Bei „false“ zeigt die Titelleiste den Namen der PDF-Datei an – Standard: „false“.
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Ob die Größe des Dokumentfensters an die Größe angepasst werden soll
// Erste angezeigte Seite – Standard: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Ob die Menüleiste der Viewer-Anwendung ausgeblendet werden soll – Standard: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//Ob die Symbolleiste der Viewer-Anwendung ausgeblendet werden soll – Standard: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Ob Benutzeroberflächenelemente wie Bildlaufleisten ausgeblendet werden sollen
// Und es werden nur die Seiteninhalte angezeigt – Standard: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Seitenmodus des Dokuments. So zeigen Sie das Dokument beim Verlassen des Vollbildmodus an.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// Das Seitenlayout, dh eine Seite, eine Spalte
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Wie das Dokument beim Öffnen angezeigt werden soll
// Dh Miniaturansichten, Vollbild anzeigen, Anhangsfenster anzeigen
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man Aspose.PDF für .NET verwendet, um Informationen über die Fenstereigenschaften eines PDF-Dokuments abzurufen. Indem Sie ein PDF-Dokument laden und auf seine Fenstereigenschaften zugreifen, können Sie Informationen darüber sammeln, wie das Dokument angezeigt werden soll, wenn es in einer Viewer-Anwendung geöffnet wird. Aspose.PDF für .NET bietet leistungsstarke Funktionen für die programmgesteuerte Arbeit mit PDF-Dateien und ist damit ein wertvolles Werkzeug für die PDF-Bearbeitung in .NET-Anwendungen.

### FAQs

#### F: Was ist der Zweck des Abrufens der Fenstereigenschaften eines PDF-Dokuments?

A: Durch das Abrufen der Fenstereigenschaften eines PDF-Dokuments können Sie Informationen darüber sammeln, wie das PDF-Dokument angezeigt werden soll, wenn es in einer Viewer-Anwendung geöffnet wird. Diese Eigenschaften steuern verschiedene Aspekte wie Fensterposition, Anzeigemodus und Sichtbarkeit von UI-Elementen.

#### F: Wie kann ich Aspose.PDF für .NET in meinem .NET-Projekt installieren?

 A: Um Aspose.PDF für .NET zu installieren, müssen Sie die Bibliothek von herunterladen[Aspose.PDF für .NET-Downloadseite](https://releases.aspose.com/pdf/net). Extrahieren Sie nach dem Herunterladen den Inhalt der ZIP-Datei und fügen Sie einen Verweis auf die Aspose.PDF für .NET-DLL in Ihrem .NET-Projekt hinzu.

#### F: Kann ich den Code anpassen, um nur bestimmte Fenstereigenschaften abzurufen?

A: Ja, Sie können den Code anpassen, um bestimmte Fenstereigenschaften abzurufen, indem Sie die Zeilen auskommentieren, die Sie nicht benötigen. Jede Zeile im Code entspricht einer bestimmten Fenstereigenschaft, sodass Sie Eigenschaften entsprechend Ihren Anforderungen einschließen oder ausschließen können.

#### F: Welche Arten von Fenstereigenschaften kann ich mit Aspose.PDF für .NET abrufen?

A: Mit Aspose.PDF für .NET können Sie verschiedene Fenstereigenschaften eines PDF-Dokuments abrufen, darunter das Zentrieren des Fensters, das Festlegen des Seitenlayouts, das Steuern der Anzeige von Symbolleisten und Menüleisten und mehr.