---
title: Fenster „Dokument abrufen“
linktitle: Fenster „Dokument abrufen“
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit der GetDocumentWindow-Funktion von Aspose.PDF für .NET Informationen zu den Fenstereigenschaften eines PDF-Dokuments abrufen.
type: docs
weight: 170
url: /de/net/programming-with-document/getdocumentwindow/
---
# Einführung

Arbeiten Sie mit PDFs und möchten mehr Kontrolle darüber, wie sie beim Öffnen angezeigt werden? Ob Sie die Menüleiste ausblenden oder die Fenstergröße an die erste Seite anpassen möchten, Aspose.PDF für .NET bietet Ihnen alle Tools, die Sie benötigen, um das Verhalten einer PDF-Datei beim Öffnen in einem Viewer anzupassen. In diesem Tutorial erklären wir Ihnen, wie Sie Dokumentfenstereinstellungen in Aspose.PDF für .NET abrufen und bearbeiten.


# Voraussetzungen

Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Aspose.PDF für .NET in Ihrer Entwicklungsumgebung installiert.
  - [Laden Sie Aspose.PDF für .NET herunter](https://releases.aspose.com/pdf/net/)
-  Eine gültige Lizenz für Aspose.PDF oder eine[Kostenlose Testversion](https://releases.aspose.com/) oder[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/).
- Grundlegende Kenntnisse von .NET und C#.
- Visual Studio oder eine andere geeignete IDE.

# Pakete importieren

Bevor Sie mit dem Schreiben von Code beginnen, müssen Sie die erforderlichen Pakete importieren. Öffnen Sie Ihr Projekt und fügen Sie oben in Ihrer C#-Datei den folgenden Namespace hinzu:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Dadurch erhalten Sie Zugriff auf alle Klassen und Methoden, die zum Bearbeiten von PDF-Dokumenten mit Aspose.PDF für .NET erforderlich sind.

 Lassen Sie uns nun den Prozess des Abrufens verschiedener Dokumentfenstereinstellungen aufschlüsseln. Für dieses Beispiel verwenden wir eine Beispiel-PDF-Datei mit dem Namen`GetDocumentWindow.pdf`.

## Schritt 1: Festlegen des Dokumentverzeichnispfads

Als Erstes müssen wir den Pfad zu unserer PDF-Datei definieren. Es ist wichtig, dass Sie den richtigen Dateipfad haben, um Fehler während der Ausführung zu vermeiden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen Sie hier`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre PDF-Datei befindet. Dies ist Ihr Arbeitsverzeichnis, aus dem Sie das PDF-Dokument laden.

## Schritt 2: Öffnen Sie das PDF-Dokument

Nachdem der Dateipfad festgelegt wurde, besteht der nächste Schritt darin, das PDF-Dokument mit Aspose.PDF zu öffnen. Dadurch wird das Dokument in den Speicher geladen und Sie können seine Eigenschaften abrufen.

```csharp
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

Mit dieser einfachen Codezeile haben Sie Ihre PDF-Datei erfolgreich in das`pdfDocument` -Objekt, das Ihnen nun den Zugriff auf alle seine Eigenschaften ermöglicht.

## Schritt 3: Fensterzentrierungsstatus abrufen

 Als nächstes prüfen wir, ob das Dokumentfenster beim Öffnen zentriert werden soll. Der Standardwert hierfür ist`false`.

```csharp
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
```

 Wenn die Ausgabe`true`, wird das Dokumentfenster in der Bildschirmmitte geöffnet. Andernfalls wird es an der Standardposition geöffnet.

## Schritt 4: Textrichtung prüfen

Ein weiterer wichtiger Aspekt des Erscheinungsbilds einer PDF-Datei ist die Textrichtung. Sie bestimmt, ob der Text von links nach rechts (L2R) oder von rechts nach links (R2L) gelesen wird. Sie können diese Information mit dem folgenden Code abrufen:

```csharp
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
```

 Die Ausgabe wird`L2R` für Text von links nach rechts und`R2L` für Text von rechts nach links. Diese Einstellung ist besonders nützlich für Dokumente in Sprachen wie Arabisch oder Hebräisch.

## Schritt 5: Dokumenttitel im Fenster anzeigen

Mit der nächsten Eigenschaft können Sie steuern, ob der Dokumenttitel oder der Dateiname in der Titelleiste des Fensters angezeigt werden soll. Standardmäßig ist dies auf`false`, d.h. der Dateiname wird angezeigt.

```csharp
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
```

Wenn Sie möchten, dass anstelle des Dateinamens der Titel des Dokuments angezeigt wird, muss diese Einstellung aktiviert werden.

## Schritt 6: Fenstergröße an die erste Seite anpassen

Manchmal möchten Sie vielleicht, dass das Dokumentfenster automatisch seine Größe an die erste Seite des PDFs anpasst, wenn es geöffnet wird. So können Sie überprüfen, ob diese Funktion aktiviert ist:

```csharp
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
```

 Standardmäßig ist dies eingestellt auf`false`, d. h. die Fenstergröße bleibt unabhängig von der Größe der ersten Seite unverändert.

## Schritt 7: Menüleiste ausblenden

Für ein konzentrierteres Leseerlebnis möchten Sie möglicherweise die Menüleiste der Viewer-Anwendung ausblenden. Sie können diese Einstellung mit der folgenden Zeile abrufen:

```csharp
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
```

 Dies wird zurückkehren`true` wenn die Menüleiste ausgeblendet ist und`false` ansonsten.

## Schritt 8: Ausblenden der Symbolleiste

Ebenso möchten Sie möglicherweise die Symbolleiste im PDF-Viewer ausblenden, um eine übersichtlichere Benutzeroberfläche zu erhalten. Diese Einstellung können Sie wie folgt abrufen:

```csharp
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
```

Wenn diese Einstellung aktiviert ist, wird die Symbolleiste beim Öffnen der PDF-Datei ausgeblendet.

## Schritt 9: Bildlaufleisten und UI-Elemente ausblenden

Wenn Sie nur den Seiteninhalt ohne zusätzliche Benutzeroberflächenelemente wie Bildlaufleisten anzeigen möchten, steuert diese Einstellung dieses Verhalten:

```csharp
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
```

 Bei Einstellung auf`true`, blendet der PDF-Viewer Bildlaufleisten und andere Elemente der Benutzeroberfläche aus, sodass nur der Dokumentinhalt angezeigt wird.

## Schritt 10: Nicht-Vollbild-Seitenmodus einstellen

 Sie können steuern, wie das Dokument beim Verlassen des Vollbildmodus angezeigt wird, indem Sie`NonFullScreenPageMode` -Eigenschaft. Diese Einstellung ist hilfreich, um zu definieren, wie der Benutzer im Nicht-Vollbildmodus mit dem Dokument interagieren soll.

```csharp
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
```

Die Ausgabe kann auf verschiedene Modi wie Miniaturansichten, Gliederungen oder Anhängefeld eingestellt werden.

## Schritt 11: Seitenlayout definieren

Mit dieser Einstellung können Sie das Layout der Dokumentseiten steuern. Sie können beispielsweise zwischen einer Einzelseitenansicht und einer fortlaufenden Spaltenansicht wählen:

```csharp
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
```

Dies gibt den Benutzern Flexibilität beim Lesen und Anzeigen des Dokumentinhalts.

## Schritt 12: Seitenmodus festlegen

 Schließlich`PageMode` Die Eigenschaft definiert, wie das Dokument beim Öffnen angezeigt werden soll. Zu den Optionen gehören die Anzeige von Miniaturansichten, der Wechsel in den Vollbildmodus oder die Anzeige des Anhangsfensters.

```csharp
Console.WriteLine("PageMode : {0}", pdfDocument.PageMode);
```

Sie können dies je nach Bedarf auf jeden Modus einstellen, der dem Zweck Ihres PDFs entspricht.

## Abschluss

Wie Sie sehen, bietet Aspose.PDF für .NET umfassende Tools zur Bearbeitung der Anzeige Ihrer PDF-Dokumente in verschiedenen PDF-Viewern. Ob Sie die Symbolleiste ausblenden, das Fenster zentrieren oder die Textrichtung steuern möchten, Aspose.PDF bietet die Flexibilität, das Anzeigeerlebnis des Benutzers zu verbessern.

# FAQs

### Kann ich die anfängliche Zoomstufe des PDFs anpassen?
Ja, Aspose.PDF ermöglicht Ihnen, die Zoomstufe beim Öffnen des Dokuments festzulegen.

### Wie kann ich die Fenstergröße eines PDF sperren?
 Sie können die`FitWindow` -Eigenschaft, um eine Größenänderung des Fensters zu verhindern.

### Unterstützt Aspose.PDF verschiedene Lesemodi?
Ja, es unterstützt verschiedene Modi wie Vollbild, Miniaturansichten und Anhänge.

### Ist es möglich, Bildlaufleisten im PDF-Viewer auszublenden?
 Natürlich können Sie Scrollleisten ausblenden, indem Sie die`HideWindowUI` Eigentum an`true`.

### Kann ich das Dokumentfenster beim Öffnen zentrieren?
 Ja, Sie können dies steuern, indem Sie die`CenterWindow` Eigentum.