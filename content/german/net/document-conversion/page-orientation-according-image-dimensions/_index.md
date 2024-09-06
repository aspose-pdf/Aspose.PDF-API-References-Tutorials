---
title: Seitenausrichtung gemäß Bildabmessungen
linktitle: Seitenausrichtung gemäß Bildabmessungen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET PDFs erstellen und die Seitenausrichtung basierend auf den Bildabmessungen festlegen.
type: docs
weight: 80
url: /de/net/document-conversion/page-orientation-according-image-dimensions/
---
## Einführung

Willkommen in der Welt von Aspose.PDF für .NET! Wenn Sie PDF-Dokumente programmgesteuert erstellen, bearbeiten oder konvertieren möchten, sind Sie hier genau richtig. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Entwickler nahtlos mit PDF-Dateien arbeiten können. In dieser Anleitung führen wir Sie durch den Prozess zum Festlegen der Seitenausrichtung basierend auf den Bildabmessungen. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, dieses Tutorial vermittelt Ihnen das Wissen, das Sie für den Einstieg in Aspose.PDF benötigen.

## Voraussetzungen

Bevor wir uns in den Code vertiefen, stellen wir sicher, dass Sie alles haben, was Sie brauchen, um weiterzumachen:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Es ist die beste IDE für die .NET-Entwicklung.
2. .NET Framework: Diese Anleitung setzt voraus, dass Sie .NET Framework verwenden. Stellen Sie sicher, dass Sie die entsprechende Version installiert haben.
3.  Aspose.PDF für .NET: Sie können die Bibliothek herunterladen von der[Aspose-Website](https://releases.aspose.com/pdf/net/) Wenn Sie es erst einmal ausprobieren möchten, können Sie sich ein[Kostenlose Testversion](https://releases.aspose.com/).
4. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, verstehen Sie die Beispiele besser.

## Pakete importieren

Um zu beginnen, müssen Sie die erforderlichen Pakete importieren. So können Sie das tun:

1. Öffnen Sie Ihr Visual Studio-Projekt.
2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt und wählen Sie „NuGet-Pakete verwalten“ aus.
3.  Suchen nach`Aspose.PDF` und installieren Sie es.

Nachdem wir nun alles eingerichtet haben, wollen wir das Beispiel Schritt für Schritt aufschlüsseln.

## Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein

Als Erstes müssen Sie den Pfad zu Ihrem Dokumentverzeichnis angeben, in dem Ihre Bilder gespeichert sind. Hier sucht Aspose nach den JPG-Dateien.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad, in dem sich Ihre Bilder befinden. Dies ist wichtig, denn wenn Aspose Ihre Bilder nicht finden kann, kann es das PDF nicht erstellen.

## Schritt 2: Ein neues PDF-Dokument erstellen

Als Nächstes erstellen Sie ein neues PDF-Dokumentobjekt. Hier werden alle Ihre Bilder hinzugefügt.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Diese Zeile initialisiert eine neue Instanz des`Document` Klasse, die Ihre PDF-Datei darstellt.

## Schritt 3: Bilddateien abrufen

 Nun holen wir alle JPG-Dateien aus dem angegebenen Verzeichnis. Dies geschieht mit dem`Directory.GetFiles` Verfahren.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

Diese Zeile gibt Ihnen ein Array von Dateinamen, die dem JPG-Format entsprechen. Stellen Sie sicher, dass Ihr Verzeichnis einige JPG-Bilder enthält, damit dies funktioniert!

## Schritt 4: Durchlaufen Sie jedes Bild

Sie müssen jede Bilddatei durchlaufen und sie dem PDF-Dokument hinzufügen. So geht das:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
    // Erstellen eines Seitenobjekts
    Aspose.Pdf.Page page = doc.Pages.Add();
```

 In dieser Schleife erstellen Sie für jedes Bild eine neue Seite.`doc.Pages.Add()` Methode fügt Ihrem PDF-Dokument eine neue Seite hinzu.

## Schritt 5: Erstellen Sie ein Bildobjekt

 Für jedes Bild müssen Sie eine`Image` Objekt, das die Bilddaten enthalten wird.

```csharp
    Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
    image1.File = fileEntries[counter];
```

 Hier ordnen Sie die aktuelle Bilddatei dem`Image` Objekt. Dies ist wichtig, um das Bild zum PDF hinzuzufügen.

## Schritt 6: Bildabmessungen prüfen

Bevor Sie das Bild zum PDF hinzufügen, müssen Sie seine Abmessungen überprüfen, um die Seitenausrichtung zu bestimmen.

```csharp
    Bitmap myimage = new Bitmap(fileEntries[counter]);
    if (myimage.Width > page.PageInfo.Width)
        page.PageInfo.IsLandscape = true;
    else
        page.PageInfo.IsLandscape = false;
```

Dieser Codeausschnitt prüft, ob die Breite des Bildes größer als die Seitenbreite ist. Wenn dies der Fall ist, wird die Seitenausrichtung auf Querformat eingestellt, andernfalls bleibt sie im Hochformat.

## Schritt 7: Fügen Sie das Bild zum PDF hinzu

Nachdem Sie die Ausrichtung festgelegt haben, ist es an der Zeit, das Bild zum PDF-Dokument hinzuzufügen.

```csharp
    page.Paragraphs.Add(image1);
}
```

Diese Zeile fügt das Bild zur Absatzsammlung der aktuellen Seite hinzu. Es ist, als würde man ein Bild in einen Rahmen setzen!

## Schritt 8: Speichern Sie das PDF-Dokument

Abschließend müssen Sie das PDF-Dokument im angegebenen Verzeichnis speichern.

```csharp
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Diese Zeile speichert das Dokument unter dem Namen`SetPageOrientation_out.pdf`. Suchen Sie unbedingt in Ihrem Dokumentverzeichnis nach der neu erstellten PDF-Datei!

## Abschluss

Und da haben Sie es! Sie haben erfolgreich ein PDF-Dokument mit Aspose.PDF für .NET erstellt und die Seitenausrichtung basierend auf den Abmessungen der Bilder festgelegt. Diese leistungsstarke Bibliothek eröffnet Ihnen eine Welt voller Möglichkeiten für die Arbeit mit PDF-Dateien in Ihren Anwendungen. Egal, ob Sie Berichte, Rechnungen oder andere Dokumenttypen erstellen, Aspose.PDF bietet alles, was Sie brauchen.

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente programmgesteuert zu erstellen, zu bearbeiten und zu konvertieren.

### Wie installiere ich Aspose.PDF?
 Sie können Aspose.PDF über den NuGet Package Manager in Visual Studio installieren oder von der[Aspose-Website](https://releases.aspose.com/pdf/net/).

### Kann ich Aspose.PDF kostenlos nutzen?
 Ja, Aspose bietet eine[Kostenlose Testversion](https://releases.aspose.com/) damit Sie die Bibliothek vor dem Kauf testen können.

### Wo finde ich Unterstützung für Aspose.PDF?
Unterstützung finden Sie auf der[Aspose-Forum](https://forum.aspose.com/c/pdf/10).

### Welche Dateitypen kann ich mit Aspose in PDF konvertieren?
Aspose.PDF unterstützt eine Vielzahl von Dateiformaten, darunter Bilder, Word-Dokumente, Excel-Tabellen und mehr.