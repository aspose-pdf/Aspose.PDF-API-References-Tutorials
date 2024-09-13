---
title: Datums-/Zeitstempel zur PDF-Datei hinzufügen
linktitle: Datums-/Zeitstempel zur PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie Ihren PDF-Dateien mit Aspose.PDF für .NET einen Datums- und Zeitstempel hinzufügen. Perfekt zur Verbesserung der Dokumentauthentizität.
type: docs
weight: 10
url: /de/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
## Einführung

Wenn es um die Verwaltung von Dokumenten, insbesondere PDFs, geht, kann das Hinzufügen eines Datums- und Zeitstempels von entscheidender Bedeutung sein. Egal, ob Sie an juristischen Dokumenten, Projektberichten oder Rechnungen arbeiten, ein Zeitstempel verleiht nicht nur Authentizität, sondern liefert auch eine klare Aufzeichnung darüber, wann das Dokument erstellt oder geändert wurde. In dieser Anleitung führen wir Sie durch den Prozess des Hinzufügens eines Datums- und Zeitstempels zu einer PDF-Datei mithilfe der Aspose.PDF-Bibliothek für .NET. 

Dieser Artikel ist so konzipiert, dass er unkompliziert und leicht verständlich ist. Selbst wenn Sie neu in der Programmierung oder der Aspose.PDF-Bibliothek sind, können Sie diese Funktion problemlos implementieren. Tauchen Sie ein!

## Voraussetzungen

Bevor wir beginnen, müssen einige Voraussetzungen erfüllt sein:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Hier schreiben und führen Sie Ihren Code aus.
2. Aspose.PDF für .NET: Sie müssen die Aspose.PDF-Bibliothek herunterladen und installieren. Die neueste Version finden Sie[Hier](https://releases.aspose.com/pdf/net/).
3. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, können Sie die Beispiele besser verstehen. Aber keine Sorge, wenn Sie gerade erst anfangen, wir erklären Ihnen alles Schritt für Schritt.
4.  Eine PDF-Datei: Halten Sie eine Beispiel-PDF-Datei bereit. Für unser Beispiel verwenden wir eine Datei mit dem Namen`AddTextStamp.pdf`.

Wenn diese Voraussetzungen erfüllt sind, können Sie mit dem Hinzufügen von Datums- und Zeitstempeln zu Ihren PDF-Dateien beginnen!

## Pakete importieren

Zunächst müssen Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren. Gehen Sie dazu wie folgt vor:

### Neues Projekt erstellen

1. Öffnen Sie Visual Studio: Starten Sie Ihre Visual Studio-Anwendung.
2. Neues Projekt erstellen: Wählen Sie auf dem Startbildschirm „Neues Projekt erstellen“ aus.
3. Konsolen-App auswählen: Wählen Sie „Konsolen-App (.NET Framework)“ aus der Liste der Projektvorlagen.
4.  Benennen Sie Ihr Projekt: Geben Sie Ihrem Projekt einen Namen, zum Beispiel`PDFDateTimeStamp`.

### Aspose.PDF-Referenz hinzufügen

1. Klicken Sie mit der rechten Maustaste auf „Referenzen“: Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Ordner „Referenzen“ Ihres Projekts.
2. Wählen Sie „Referenz hinzufügen“: Wählen Sie „Referenz hinzufügen“ aus dem Kontextmenü.
3. Suchen Sie nach Aspose.PDF: Navigieren Sie zu dem Speicherort, an dem Sie Aspose.PDF heruntergeladen haben, und wählen Sie es aus. Klicken Sie auf „OK“, um es Ihrem Projekt hinzuzufügen.

### Erforderliche Namespaces importieren

 Ganz oben auf Ihrer`Program.cs` Datei müssen Sie die folgenden Namespaces importieren:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Annotations;
```

Nachdem wir nun alles eingerichtet haben, unterteilen wir den Vorgang des Hinzufügens eines Datums- und Zeitstempels zu einer PDF-Datei in klare, überschaubare Schritte.

## Schritt 1: Dokumentverzeichnis festlegen

Zuerst müssen Sie das Verzeichnis angeben, in dem sich Ihre PDF-Datei befindet. Dies ist wichtig, da der Code in diesem Verzeichnis nach der PDF-Datei sucht.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ersetzen Sie es durch Ihren tatsächlichen Pfad.
```

 Ersetzen Sie unbedingt`YOUR DOCUMENT DIRECTORY` durch den tatsächlichen Pfad zu Ihrer PDF-Datei.

## Schritt 2: Öffnen Sie das PDF-Dokument

Als Nächstes öffnen Sie das PDF-Dokument, in dem Sie den Zeitstempel hinzufügen möchten. 

```csharp
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Diese Codezeile initialisiert den`Document` Klasse und lädt Ihre PDF-Datei in die`pdfDocument` Objekt.

## Schritt 3: Erstellen Sie den Datums-/Zeitstempel

Jetzt ist es an der Zeit, den Datums- und Zeitstempel zu generieren. Sie formatieren ihn so, dass er auf eine bestimmte Weise angezeigt wird. 

```csharp
string annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
```

 Hier,`DateTime.Now` ruft das aktuelle Datum und die Uhrzeit ab und`ToString` formatiert es in das gewünschte Format.

## Schritt 4: Erstellen Sie einen Textstempel

Wenn die Datums- und Uhrzeitzeichenfolge bereit ist, können Sie jetzt einen Textstempel erstellen, der Ihrer PDF-Datei hinzugefügt wird.

```csharp
// Textstempel erstellen
TextStamp textStamp = new TextStamp(annotationText);
```

 Diese Zeile erstellt eine neue Instanz von`TextStamp` unter Verwendung der formatierten Datums- und Uhrzeitzeichenfolge.

## Schritt 5: Eigenschaften des Stempels festlegen

Sie können das Aussehen und die Position des Stempels anpassen. So legen Sie seine Eigenschaften fest:

```csharp
// Eigenschaften des Stempels festlegen
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

In diesem Schritt legen wir die Ränder fest und richten den Stempel an der unteren rechten Ecke der PDF-Seite aus.

## Schritt 6: Stempel zum PDF hinzufügen

Jetzt ist es Zeit, Ihrem PDF-Dokument den Textstempel hinzuzufügen. 

```csharp
// Briefmarke zur Briefmarkensammlung hinzufügen
pdfDocument.Pages[1].AddStamp(textStamp);
```

Diese Zeile fügt den Stempel zur ersten Seite des PDFs hinzu. Sie können die Seitenzahl ändern, wenn Sie den Stempel auf einer anderen Seite platzieren möchten.

## Schritt 7: Erstellen Sie eine Freitextanmerkung (optional)

Wenn Sie dem Stempel eine Anmerkung hinzufügen möchten, können Sie eine`FreeTextAnnotation` wie folgt:

```csharp
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;
```

Dieser optionale Schritt erstellt eine Freitextanmerkung, die zusätzlichen Kontext oder Informationen zum Stempel liefern kann.

## Schritt 8: Konfigurieren des Anmerkungsrahmens

Wenn Sie den Rahmen Ihrer Anmerkung anpassen möchten, können Sie das auch tun:

```csharp
Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Dieser Codeausschnitt setzt die Rahmenbreite auf 0, macht sie unsichtbar und fügt die Anmerkung zum PDF hinzu.

## Schritt 9: Speichern Sie das PDF-Dokument

Abschließend müssen Sie das geänderte PDF-Dokument speichern. 

```csharp
dataDir = dataDir + "AddDateTimeStamp_out.pdf"; // Geben Sie den Namen der Ausgabedatei an
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);
```

Diese Zeile speichert das PDF mit dem hinzugefügten Zeitstempel in einer neuen Datei. Sie können das von Ihnen angegebene Verzeichnis überprüfen, um die Ausgabe anzuzeigen.

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich einen Datums- und Zeitstempel zu einer PDF-Datei hinzugefügt. Diese einfache, aber effektive Funktion kann Ihre Dokumente verbessern, sie professioneller gestalten und einen klaren Nachweis darüber liefern, wann sie erstellt oder geändert wurden. 

## Häufig gestellte Fragen

### Kann ich das Datumsformat im Zeitstempel anpassen?
 Ja, Sie können die`ToString`Methode, um das Datumsformat nach Ihren Wünschen zu ändern.

### Ist die Nutzung von Aspose.PDF kostenlos?
 Aspose.PDF bietet eine kostenlose Testversion an, aber für den vollen Funktionsumfang müssen Sie eine Lizenz erwerben. Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).

### Kann ich einem PDF mehrere Zeitstempel hinzufügen?
 Auf jeden Fall! Sie können mehrere`TextStamp` Instanzen und fügen Sie sie zu verschiedenen Seiten oder Positionen im PDF ein.

### Was ist, wenn ich Visual Studio nicht habe?
Sie können jede C#-IDE oder jeden Texteditor verwenden, zum Ausführen und Debuggen Ihres Projekts wird jedoch Visual Studio empfohlen.

### Wo finde ich weitere Beispiele zur Verwendung von Aspose.PDF?
 Weitere Beispiele und Tutorials finden Sie im[Aspose.PDF-Dokumentation](https://reference.aspose.com/pdf/net/).