---
title: Bildgröße in PDF-Datei festlegen
linktitle: Bildgröße in PDF-Datei festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET die Bildgröße in einer PDF-Datei festlegen. Diese Schritt-für-Schritt-Anleitung hilft Ihnen, die Größe von Bildern zu ändern, Seiteneigenschaften anzupassen und PDF-Dateien zu speichern.
type: docs
weight: 270
url: /de/net/programming-with-images/set-image-size/
---
## Einführung

Das Arbeiten mit PDFs ist eine häufige Anforderung für viele Anwendungen, und die Möglichkeit, Elemente in einer PDF-Datei zu bearbeiten, kann entscheidend sein. Egal, ob Sie einen Berichtsgenerator erstellen oder Ihrem PDF dynamische Inhalte hinzufügen, die Kontrolle der Bildgröße in Ihrem Dokument ist eine wesentliche Funktion. In diesem Tutorial zeigen wir Ihnen, wie Sie die Bildgröße in einer PDF-Datei mit Aspose.PDF für .NET festlegen. Diese leistungsstarke Bibliothek bietet umfassende Kontrolle über PDF-Inhalte, und wir werden sie Schritt für Schritt aufschlüsseln, um Ihnen zu zeigen, wie einfach das sein kann. Am Ende können Sie die Größe von Bildern sicher ändern und verstehen, wie diese Funktion Ihre PDF-Workflows verbessern kann.


## Voraussetzungen

Bevor wir uns in den Code vertiefen, müssen Sie einige Dinge vorbereitet haben, um diesem Tutorial folgen zu können.

1.  Aspose.PDF für .NET: Stellen Sie sicher, dass Sie die neueste Version der Aspose.PDF-Bibliothek installiert haben. Sie können[Laden Sie es hier herunter](https://releases.aspose.com/pdf/net/).
2. .NET Framework oder .NET Core: Stellen Sie sicher, dass Sie eine Arbeitsumgebung mit .NET Framework oder .NET Core eingerichtet haben.
3. Grundkenntnisse in C#: Wir verwenden C# als Programmiersprache, daher ist die Vertrautheit damit unerlässlich.
4. Beispielbild: Sie benötigen ein Beispielbild zum Einbetten in die PDF-Datei. Sie können jedes beliebige Bild verwenden, stellen Sie jedoch sicher, dass es in Ihrem Projektverzeichnis zugänglich ist.

## Pakete importieren

Um Aspose.PDF für .NET zu verwenden, müssen Sie zunächst die erforderlichen Namespaces importieren. Hier ist eine einfache Einrichtung:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nachdem wir nun die Grundlagen abgedeckt haben, fahren wir mit dem Erstellen und Ändern eines PDF-Dokuments fort.

## Schritt 1: Initialisieren Sie Ihr PDF-Dokument

 Als erstes müssen wir ein neues PDF-Dokument erstellen. Wir verwenden das`Document` Klasse von Aspose.PDF, um dies zu erreichen.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document-Objekt instanziieren
Document doc = new Document();
```
 
 Hier instantiieren wir ein`Document` Objekt, das unsere PDF-Datei darstellen wird. Wir geben auch das Verzeichnis an, in dem sich unsere Dateien befinden, mit dem`dataDir` Variable. Dies ist der Ausgangspunkt zum Erstellen einer beliebigen PDF-Datei mit Aspose.PDF.

## Schritt 2: Fügen Sie Ihrer PDF-Datei eine neue Seite hinzu

Sobald unser Dokument fertig ist, müssen wir eine Seite hinzufügen. Jedes PDF muss mindestens eine Seite haben, also fügen wir eine hinzu.

```csharp
// Seite zur Seitensammlung der PDF-Datei hinzufügen
Aspose.Pdf.Page page = doc.Pages.Add();
```
 
 Wir fügen dem Dokument eine neue Seite hinzu mit dem`Pages.Add()` Methode. Diese Seite dient als Leinwand, auf der wir unser Bild platzieren. Jede Seite in einer PDF-Datei ist im Wesentlichen eine leere Tafel, auf der Sie Text, Bilder oder andere Inhalte hinzufügen können.

## Schritt 3: Erstellen einer Image-Instanz

 Jetzt ist es an der Zeit, das Bild vorzubereiten, das wir in das PDF einfügen möchten. Aspose.PDF bietet eine`Image` Klasse zur Verarbeitung von Bildern.

```csharp
// Erstellen einer Imageinstanz
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```
 
 Wir erstellen eine neue Instanz des`Image` Klasse. Dieses Objekt enthält die Eigenschaften des Bildes, das wir dem PDF hinzufügen möchten. In den nächsten Schritten konfigurieren wir die Größe und den Typ des Bildes.

## Schritt 4: Bildgröße festlegen (Breite und Höhe)

Hier kommen wir zum Kern unseres Tutorials: Festlegen der Bildgröße. Aspose.PDF ermöglicht es Ihnen, die Breite und Höhe des Bildes in Punkten anzugeben.

```csharp
// Bildbreite und -höhe in Punkten festlegen
img.FixWidth = 100;
img.FixHeight = 100;
```
 
 Der`FixWidth` Und`FixHeight`Mit den Eigenschaften können Sie die genauen Abmessungen des Bildes in Punkten festlegen. In diesem Beispiel ändern wir die Größe des Bildes auf 100 x 100 Punkte. Sie können diese Werte Ihren Bedürfnissen entsprechend anpassen.

## Schritt 5: Bildtyp festlegen

Abhängig vom Bildformat, mit dem Sie arbeiten, müssen Sie möglicherweise den Bildtyp festlegen. Aspose.PDF unterstützt verschiedene Bildformate. Hier definieren wir den Dateityp.

```csharp
// Bildtyp als SVG festlegen
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
```
 
 In diesem Fall belassen wir den Dateityp als`Unknown` , wodurch die Bibliothek den Bildtyp automatisch erkennt. Wenn Sie den spezifischen Dateityp kennen, können Sie ihn festlegen (z. B.`ImageFileType.Jpeg` für JPEG-Bilder). Dieser Schritt stellt sicher, dass Aspose weiß, wie das Bild richtig zu verarbeiten ist.

## Schritt 6: Legen Sie den Pfad zu Ihrer Bilddatei fest

Jetzt müssen wir Aspose mitteilen, wo die Bilddatei zu finden ist. Stellen Sie sicher, dass Ihr Bild im angegebenen Verzeichnis zugänglich ist.

```csharp
// Pfad zur Quelldatei
img.File = dataDir + "aspose-logo.jpg";
```
 
 Hier legen wir den Dateipfad zum Bild fest. Das Bild befindet sich in diesem Fall im`dataDir` Ordner und hat den Namen`aspose-logo.jpg`Stellen Sie sicher, dass Sie dies durch den tatsächlichen Namen und Speicherort Ihrer Bilddatei ersetzen.

## Schritt 7: Fügen Sie das Bild zur Seite hinzu

Nachdem wir das Bild konfiguriert und den Dateipfad festgelegt haben, können wir das Bild nun zu unserer Seite hinzufügen.

```csharp
// Fügen Sie das Bild zur Absatzsammlung hinzu
page.Paragraphs.Add(img);
```
 
 Der`Paragraphs.Add()` Methode ermöglicht es uns, das Bild zur Seite hinzuzufügen. Denken Sie an die`Paragraphs` Sammlung als Liste von Elementen, die auf der PDF-Seite gerendert werden. Wir können dieser Sammlung mehrere Elemente hinzufügen, z. B. Bilder, Text und Formen.

## Schritt 8: Seiteneigenschaften anpassen

Um sicherzustellen, dass unser Bild gut passt, passen wir die Seitengröße an. Dadurch wird sichergestellt, dass die Seitenabmessungen mit dem von uns hinzugefügten Inhalt übereinstimmen.

```csharp
// Festlegen der Seiteneigenschaften
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```
 
Hier stellen wir die Seitenbreite und -höhe auf 800 Punkte ein. Dieser Schritt ist optional, stellt aber sicher, dass die Seite das skalierte Bild aufnehmen kann. Sie können diese Werte Ihren spezifischen Anforderungen entsprechend anpassen.

## Schritt 9: Speichern Sie das PDF

Nachdem wir abschließend die Bild- und Seiteneigenschaften konfiguriert haben, können wir das PDF speichern.

```csharp
//Speichern Sie die resultierende PDF-Datei
dataDir = dataDir + "SetImageSize_out.pdf";
doc.Save(dataDir);
```
 
 Wir speichern das geänderte Dokument als`SetImageSize_out.pdf` im selben Verzeichnis. Diese Datei enthält nun das von Ihnen hinzugefügte, skalierte Bild.

## Abschluss

In diesem Tutorial haben wir erläutert, wie Sie die Bildgröße in einer PDF-Datei mit Aspose.PDF für .NET festlegen. Wir haben das Erstellen eines Dokuments, das Hinzufügen einer Seite, das Konfigurieren eines Bilds und das Speichern des Ergebnisses durchgegangen. Diese Schritt-für-Schritt-Anleitung ist nur der Anfang dessen, was Sie mit Aspose.PDF für .NET tun können. Nachdem Sie nun gelernt haben, wie Sie die Größe von Bildern ändern, können Sie weitere Funktionen wie Textformatierung, Tabellenerstellung und sogar das Hinzufügen von Anmerkungen zu Ihrer PDF-Datei erkunden.

## Häufig gestellte Fragen

### Kann ich mit Aspose.PDF für .NET verschiedene Bildformate verwenden?  
Ja, Aspose.PDF unterstützt verschiedene Bildformate wie JPEG, PNG, BMP und SVG.

### Wie behalte ich das Seitenverhältnis des Bildes bei?  
 Sie können das Seitenverhältnis beibehalten, indem Sie entweder`FixWidth` oder`FixHeight` während die andere Dimension nicht festgelegt wird.

### Kann ich einer einzelnen PDF-Seite mehrere Bilder hinzufügen?  
Absolut! Wiederholen Sie einfach den Vorgang des Hinzufügens einer Bildinstanz und fügen Sie jede einzelne zur`Paragraphs` Sammlung.

### Ist es möglich, die Bildgröße in anderen Einheiten als Punkten einzustellen?  
Aspose.PDF arbeitet hauptsächlich mit Punkten, aber Sie können andere Einheiten wie Zoll oder Millimeter in Punkte umrechnen (1 Zoll = 72 Punkte).

### Wie positioniere ich ein Bild an einer bestimmten Stelle auf der Seite?  
 Sie können die`Image.LowerLeftX` Und`Image.LowerLeftY` Eigenschaften, um das Bild auf der Seite zu positionieren.