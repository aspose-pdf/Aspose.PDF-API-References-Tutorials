---
title: Linienbreite für lnk-Anmerkungen
linktitle: Linienbreite für lnk-Anmerkungen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET die Linienbreite von Tintenanmerkungen in einer PDF-Datei festlegen. Dieses ausführliche Tutorial führt Sie durch jeden Schritt und gewährleistet eine qualitativ hochwertige Ausgabe.
type: docs
weight: 110
url: /de/net/annotations/lnkannotationlinewidth/
---
## Einführung

Beim Arbeiten mit PDF-Dokumenten kann das Hinzufügen von Anmerkungen eine wirkungsvolle Möglichkeit sein, Informationen hervorzuheben oder Ihren Dateien interaktive Elemente hinzuzufügen. Eine solche Anmerkung ist die Tintenanmerkung, mit der Sie Freiformlinien in Ihr PDF zeichnen können. Aber was, wenn Sie das Erscheinungsbild dieser Linien, insbesondere die Linienbreite, anpassen müssen? In diesem Tutorial führen wir Sie durch den Prozess zum Festlegen der Linienbreite der Tintenanmerkung mit Aspose.PDF für .NET.

## Voraussetzungen

Bevor wir uns in den Code vertiefen, stellen wir sicher, dass Sie alles eingerichtet haben, um diesem Tutorial problemlos folgen zu können:

1.  Aspose.PDF für .NET: Stellen Sie sicher, dass Sie die Aspose.PDF für .NET-Bibliothek installiert haben. Sie können sie von der[Download-Seite](https://releases.aspose.com/pdf/net/) oder installieren Sie es über den NuGet-Paket-Manager in Visual Studio.
2. Entwicklungsumgebung: Dieses Tutorial setzt voraus, dass Sie in einer .NET-Entwicklungsumgebung wie Visual Studio arbeiten.
3. Grundkenntnisse in C#: Grundlegende Kenntnisse in C# helfen Ihnen dabei, die Codierungsschritte zu befolgen.
4. PDF-Dokument: Verwenden Sie für dieses Tutorial entweder ein vorhandenes PDF-Dokument oder erstellen Sie ein neues.

## Erforderliche Namespaces importieren

Bevor Sie mit der Codierung beginnen, stellen Sie sicher, dass Sie die erforderlichen Namespaces in Ihr Projekt importieren:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

Diese Namespaces stellen die Klassen und Methoden bereit, die zum Bearbeiten von PDF-Dokumenten, zum Arbeiten mit Anmerkungen und zum Verarbeiten grafischer Elemente erforderlich sind.

Nachdem wir nun die Voraussetzungen geschaffen haben, können wir den Vorgang zum Festlegen der Linienbreite für Freihandanmerkungen in klare, überschaubare Schritte unterteilen.

## Schritt 1: Initialisieren Sie das PDF-Dokument

Zuerst müssen wir ein PDF-Dokument erstellen oder öffnen. Für dieses Tutorial erstellen wir ein neues PDF-Dokument von Grund auf.

```csharp
// Initialisieren des PDF-Dokuments
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Geben Sie Ihr Dokumentverzeichnis an
Document doc = new Document();
doc.Pages.Add(); // Fügen Sie dem Dokument eine leere Seite hinzu
```

 Hier initialisieren wir ein neues`Document` Objekt, das unsere PDF-Datei darstellt. Wir fügen diesem Dokument dann eine leere Seite hinzu, mit der wir arbeiten können.

## Schritt 2: Erstellen Sie die Freihandanmerkung

Als Nächstes erstellen wir die eigentliche Tintenanmerkung. Dazu müssen die Punkte definiert werden, aus denen die Tintenstriche bestehen.

```csharp
// Erstellen der Freihandanmerkung
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

 In diesem Schritt definieren wir die`LineInfo` Objekt, das die Koordinaten der Tintenstriche, ihre Sichtbarkeit, Farbe und anfängliche Linienbreite enthält. Das`VerticeCoordinate` Array enthält die X- und Y-Koordinaten jedes Punkts im Strich.

## Schritt 3: Koordinaten in Punkte umwandeln

Jetzt müssen wir diese Koordinaten in Punkte umwandeln, die von der Tintenanmerkung verwendet werden können.

```csharp
// Koordinaten in Punkte umwandeln
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

 Diese Schleife verarbeitet das Koordinatenarray und wandelt jedes Koordinatenpaar in ein`Point` Objekt, das dann zu unserem hinzugefügt wird`inkList`.

## Schritt 4: Fügen Sie der PDF-Seite die Tintenanmerkung hinzu

Wenn die Punkte bereit sind, können wir jetzt die Tintenanmerkung erstellen und sie der PDF-Seite hinzufügen.

```csharp
// Hinzufügen der Tintenanmerkung zur PDF-Seite
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

 In diesem Schritt initialisieren wir ein`InkAnnotation`Objekt, das die Seite, ein Begrenzungsrechteck und unsere Punkteliste angibt. Wir legen auch das Thema, den Titel und die Farbe der Anmerkung fest.

## Schritt 5: Den Rand der Anmerkung anpassen

Um das Erscheinungsbild unserer Anmerkung weiter anzupassen, ändern wir ihre Rahmeneigenschaften.

```csharp
// Anpassen des Rands der Anmerkung
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

 Hier erstellen wir eine`Border` Objekt für unsere Anmerkung und legen dessen Breite, Effekt, Strichmuster und Stil fest. Dieser Schritt stellt sicher, dass die Anmerkung auf der PDF-Seite optisch hervorsticht.

## Schritt 6: Speichern Sie das PDF-Dokument

Nachdem Sie alle erforderlichen Änderungen vorgenommen haben, können Sie das Dokument abschließend speichern.

```csharp
// Speichern Sie das PDF-Dokument
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

 Dieser Code speichert das geänderte PDF-Dokument mit der Tintenanmerkung im angegebenen Verzeichnis.`Console.WriteLine` Anweisung bestätigt die erfolgreiche Ausführung des Codes.

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich eine Tintenanmerkung in einem PDF-Dokument erstellt und angepasst. Dieses Tutorial behandelte den gesamten Prozess, vom Initialisieren des Dokuments bis zum Speichern der endgültigen Datei. Mit diesem Wissen können Sie die umfangreichen Funktionen von Aspose.PDF für .NET weiter erkunden und ähnliche Techniken auf andere Arten von Anmerkungen oder PDF-Manipulationen anwenden.

## Häufig gestellte Fragen

### Kann ich für verschiedene Teile der Tintenanmerkung unterschiedliche Farben verwenden?  
 Ja, Sie können mehrere erstellen`InkAnnotation` Objekte mit unterschiedlichen Farben und fügen Sie sie derselben oder unterschiedlichen Seiten Ihrer PDF-Datei hinzu.

### Wie ändere ich die Linienbreite dynamisch?  
 Sie können die`LineWidth` Eigentum der`LineInfo` Objekt, bevor die Koordinaten in Punkte umgewandelt werden.

### Ist es möglich, die Tintenanmerkung transparent zu machen?  
 Ja, Sie können die`Opacity` Eigentum der`InkAnnotation` Objekt, um es transparent zu machen.

### Kann ich derselben Seite mehrere Tintenanmerkungen hinzufügen?  
Auf jeden Fall! Sie können einer Seite beliebig viele Freihandanmerkungen hinzufügen, indem Sie den Vorgang wiederholen.

### Wie entferne ich eine Tintenanmerkung aus einer PDF?  
 Sie können eine Anmerkung entfernen, indem Sie auf`doc.Pages[1].Annotations.Delete(a1)` Methode, wobei`a1` ist Ihr Annotationsobjekt.