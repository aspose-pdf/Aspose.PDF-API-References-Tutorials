---
title: Bild in XImage-Sammlung speichern
linktitle: Bild in XImage-Sammlung speichern
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser vollständigen Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET Bilder in einer XImage-Sammlung speichern.
type: docs
weight: 290
url: /de/net/programming-with-images/store-image-in-ximage-collection/
---
## Einführung

Im heutigen digitalen Zeitalter ist die programmgesteuerte Handhabung und Bearbeitung von Dokumenten für viele Anwendungen unerlässlich. Aspose.PDF für .NET ermöglicht Entwicklern die mühelose Arbeit mit PDF-Dateien, verbessert Arbeitsabläufe und ermöglicht die Erstellung dynamischer Inhalte. In diesem Handbuch werden wir uns mit dem Prozess der Speicherung eines Bildes in der XImage-Sammlung befassen, einer wichtigen Funktion, mit der Sie visuelle Elemente direkt in Ihre PDFs einbetten können. Bereit, sich auf diese Reise zur Erstellung atemberaubender Inhalte zu begeben?

## Voraussetzungen

Bevor wir uns in den Code und die Prozesse vertiefen, müssen Sie sicherstellen, dass einige Dinge vorhanden sind:

- .NET-Umgebung: Auf Ihrem Computer sollte das .NET Framework installiert sein. Wählen Sie die entsprechende Version basierend auf den Anforderungen Ihres Projekts.
- Aspose.PDF für .NET: Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek haben. Sie können sie herunterladen von[Hier](https://releases.aspose.com/pdf/net/) oder starten Sie mit einer kostenlosen Testversion[Hier](https://releases.aspose.com/).
- Bilddatei: Sie benötigen außerdem eine Bilddatei (z. B. JPG oder PNG), die Sie im PDF speichern möchten. Für dieses Beispiel verwenden wir eine Datei namens „aspose-logo.jpg“.
- Grundlegende Kenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, können Sie problemlos mitmachen.

## Pakete importieren

Um Aspose.PDF für .NET zu verwenden, müssen Sie die erforderlichen Namespaces importieren. Dieser Schritt legt die Grundlage für die Nutzung aller von der Bibliothek angebotenen Funktionen.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Operators;
```

Durch das Importieren dieser Namespaces aktivieren Sie verschiedene Funktionen in Aspose.PDF, darunter Dokumenterstellung, Bildverarbeitung und mehr.

Lassen Sie uns dies in überschaubare Schritte aufteilen, damit Sie es leichter nachvollziehen können.

## Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein

Was müssen Sie als Erstes tun? Legen Sie fest, wo Ihre Dokumente gespeichert werden sollen. Sie sollten eine Variable einrichten, die den Pfad zu Ihrem Dokumentverzeichnis enthält. Dort wird Ihr PDF gespeichert.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ersetzen Sie es durch Ihr tatsächliches Dokumentverzeichnis.
```

## Schritt 2: Initialisieren Sie das Dokument

Jetzt ist es an der Zeit, ein neues PDF-Dokument zu erstellen. In diesem Schritt wird Ihr PDF zum Leben erweckt. 

```csharp
Aspose.Pdf.Document document = new Document();
```

Hier instanziieren wir ein neues Dokumentobjekt, das uns als Leinwand dienen wird.

## Schritt 3: Eine neue Seite hinzufügen

Jedes Meisterwerk braucht eine Leinwand, oder? In unserem Fall brauchen wir eine Seite, auf der wir innerhalb des Dokuments arbeiten können.

```csharp
document.Pages.Add();
Page page = document.Pages[1]; // Holen Sie sich die erste Seite.
```

Wir fügen unserem Dokument eine neue Seite hinzu. Jetzt bearbeiten wir diese Seite.

## Schritt 4: Laden Sie die Bilddatei

Als Nächstes müssen Sie das Bild in Ihr Programm laden. Dieser Schritt ist dem Öffnen eines Buches zum Lesen sehr ähnlich. Sie müssen auf den Inhalt zugreifen, bevor Sie ihn verwenden können.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open))
{
```

Diese Zeile öffnet die Bilddatei als Stream, wodurch wir sie bearbeiten und in das PDF einbetten können.

## Schritt 5: Fügen Sie das Bild zu den Seitenressourcen hinzu

Jetzt, da das Bild einsatzbereit ist, ist es an der Zeit, es zu den Seitenressourcen hinzuzufügen und dem PDF im Wesentlichen zu sagen: „Hey, ich habe ein cooles Bild, an das du dich erinnern sollst!“

```csharp
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

 Dieser Code übernimmt die schwere Arbeit, das Bild zum PDF hinzuzufügen und es einem`XImage` Variable, auf die wir später verweisen können.

## Schritt 6: Bereiten Sie das Zeichnen des Bildes vor

Jetzt kommt der spaßige Teil – das Positionieren des Bildes auf der Seite. Sie sollten die Koordinaten so festlegen, dass das Bild genau dort platziert wird, wo Sie es haben möchten.

```csharp
page.Contents.Add(new GSave());
```

Diese Zeile speichert den Grafikzustand zur späteren Wiederherstellung. Es ist, als ob wir einen Schnappschuss davon machen, wie die Dinge eingerichtet sind, bevor wir etwas ändern.

## Schritt 7: Bildposition und -größe festlegen

Legen Sie nun fest, wie groß und wo Sie Ihr Bild platzieren möchten:

```csharp
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
```

Dieser Codeblock legt die Abmessungen des Rechtecks fest, in das Ihr Bild passt, und gibt ihm damit im Wesentlichen einen Platz auf Ihrer Seite.

## Schritt 8: Erstellen einer Transformationsmatrix 

Um zu steuern, wie das Bild platziert wird, definieren wir eine Transformationsmatrix. Diese bestimmt, wie das Bild an den Zielkoordinaten erscheint.

```csharp
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

Stellen Sie sich das so vor, als würden Sie vor Ihrer Reise eine Karte entwerfen. So können Sie bestimmen, wie das Bild auf der Seite angezeigt wird.

## Schritt 9: Platzieren Sie das Bild auf der Seite

Jetzt ist es an der Zeit, dem PDF mitzuteilen, wo das Bild abgelegt werden soll.

```csharp
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
```

Hier fügen wir dem Inhaltsstrom des PDFs Befehle hinzu, die das Bild tatsächlich entsprechend der Matrix zeichnen, die wir gerade erstellt haben.

## Schritt 10: Speichern Sie das Dokument

Endlich können wir unser Meisterwerk speichern! Dies ist der Moment, in dem all Ihre harte Arbeit zu einem greifbaren Ergebnis zusammenkommt.

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Sie haben Aspose.PDF angewiesen, das Dokument unter dem angegebenen Dateinamen zu speichern. Wenn Sie diesen Code ausführen, finden Sie Ihre neu erstellte PDF-Datei mit Ihrem eingebetteten Bild im angegebenen Verzeichnis.

## Abschluss

Und da haben Sie es! Sie haben gelernt, wie Sie Aspose.PDF für .NET verwenden, um ein Bild Punkt für Punkt in der XImage-Sammlung zu speichern. Ist es nicht befriedigend zu sehen, wie Ihr Code Gestalt annimmt und etwas Nützliches generiert? Egal, ob Sie Anwendungen erstellen oder nur Berichte automatisieren möchten, dieser Leitfaden dient als großartige Grundlage. Denken Sie daran, dass die Leistungsfähigkeit von Aspose.PDF Sie bei einer Vielzahl von Aufgaben unterstützen kann, die über diese hinausgehen. Erkunden Sie also weiter!

## Häufig gestellte Fragen

### Welche Dateiformate werden für Bilder in Aspose.PDF unterstützt?
Aspose.PDF unterstützt verschiedene Bildformate, darunter JPG, PNG, BMP und GIF.

### Kann ich die Größe des Bildes beim Hinzufügen zum PDF ändern?
Ja, durch Anpassen der im Rechteck festgelegten Koordinaten können Sie die Größe des im PDF angezeigten Bildes verändern.

### Benötige ich eine Lizenz, um Aspose.PDF zu verwenden?
 Aspose bietet eine kostenlose Testversion und verschiedene Kaufoptionen. Sie finden sie[Hier](https://purchase.aspose.com/buy).

### Wie erhalte ich Unterstützung, wenn Probleme auftreten?
 Sie können Hilfe von der Aspose-Community anfordern[Hier](https://forum.aspose.com/c/pdf/10).

### Gibt es eine Möglichkeit, die dem PDF hinzugefügten Bilder zu komprimieren?
Ja, wenn Sie Bilder zum PDF hinzufügen, können Sie den Bildfiltertyp angeben, um Komprimierungsmethoden wie Flate zu verwenden.