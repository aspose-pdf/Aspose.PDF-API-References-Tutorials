---
title: LNK-Anmerkung hinzufügen
linktitle: LNK-Anmerkung hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser ansprechenden Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET Tintenanmerkungen zu PDF-Dateien hinzufügen.
type: docs
weight: 20
url: /de/net/annotations/addlnkannotation/
---
## Einführung

Willkommen in der Welt der PDF-Bearbeitung mit Aspose.PDF für .NET! Wenn Sie Ihre PDF-Dokumente verbessern möchten, sei es für den professionellen Einsatz, persönliche Projekte oder irgendetwas dazwischen, sind Sie hier richtig. Heute werden wir uns mit einer spezifischen, aber praktischen Funktion von Aspose.PDF befassen: dem Hinzufügen einer Tintenanmerkung zu Ihren PDF-Dateien. Diese Funktion kann unglaublich nützlich sein, wenn Sie Ihren Dokumenten handschriftliche Notizen oder Unterschriften hinzufügen möchten, um sie interaktiver und ansprechender zu gestalten.

## Voraussetzungen

Bevor wir uns in die Zauberei der Codierung stürzen, stellen wir sicher, dass Sie alles haben, was Sie für den Einstieg benötigen:

1. .NET Framework: Stellen Sie sicher, dass .NET auf Ihrem Computer installiert ist. Diese Bibliothek funktioniert nahtlos mit verschiedenen Versionen von .NET, einschließlich .NET Core.
2.  Aspose.PDF-Bibliothek: Sie müssen die Aspose.PDF-Bibliothek für .NET heruntergeladen und in Ihrem Projekt referenziert haben. Wenn Sie dies noch nicht getan haben, können Sie die neueste Version von der[Downloadlink](https://releases.aspose.com/pdf/net/).
3. Ein Code-Editor: Sie können einen beliebigen Code-Editor verwenden, aber Visual Studio wird aufgrund seiner Benutzerfreundlichkeit mit .NET-Anwendungen dringend empfohlen.
4. Grundlegende Kenntnisse in C#: Gute Kenntnisse in C# helfen Ihnen, problemlos durch die Codierungsbeispiele zu navigieren.
5. Einrichten Ihrer Entwicklungsumgebung: Stellen Sie sicher, dass Ihre IDE für die Verarbeitung von .NET-Projekten eingerichtet ist und dass Sie in Ihrem Projekt korrekt auf die Aspose.PDF-Bibliothek verwiesen haben. 

Wenn diese Voraussetzungen erfüllt sind, können Sie mit dem Hinzufügen von Tintenanmerkungen zu Ihren PDFs beginnen!

## Pakete importieren

Bevor wir mit dem Programmieren beginnen, importieren wir die erforderlichen Pakete. Fügen Sie oben in Ihrer C#-Datei die folgenden using-Anweisungen hinzu:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using System;
using System.Collections;
using System.Collections.Generic;
```

Dadurch erhalten Sie Zugriff auf alle Klassen und Methoden, die Sie zum Arbeiten mit PDF-Anmerkungen benötigen.

Nachdem wir nun alles vorbereitet haben, ist es an der Zeit, die Ärmel hochzukrempeln und an die Sache heranzugehen! Wir werden jeden Schritt aufschlüsseln, um sicherzustellen, dass Sie genau verstehen, wie Sie eine Tintenanmerkung erstellen und zu Ihrem PDF-Dokument hinzufügen.

## Schritt 1: Dokument und Verzeichnis festlegen

Als Erstes möchten Sie Ihr Dokument und den Pfad einrichten, unter dem Sie Ihre Ausgabedatei speichern möchten. 

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
```
 Wir definieren eine Variable`dataDir` , das auf das Verzeichnis verweist, in dem die resultierende PDF-Datei gespeichert wird.`Document` Anschließend wird das Objekt instanziiert und ein neues PDF-Dokument zur Bearbeitung erstellt.

## Schritt 2: Fügen Sie Ihrem Dokument eine Seite hinzu

Als Nächstes möchten Sie Ihrem neu erstellten Dokument eine Seite hinzufügen.

```csharp
Page pdfPage = doc.Pages.Add();
```
Hier fügen wir unserem Dokument eine neue Seite hinzu. Jedes PDF benötigt mindestens eine Seite, daher ist dieser Schritt unerlässlich.

## Schritt 3: Definieren Sie das Zeichenrechteck

Bevor Sie etwas zeichnen können, müssen Sie festlegen, wo auf der Seite Sie Ihre Tintenanmerkung platzieren möchten.

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
```
 Hier erstellen wir eine`Rectangle` Objekt, das den Bereich auf der Seite angibt, in dem wir unsere Tintenanmerkung hinzufügen. Wir legen die Abmessungen so fest, dass sie auf die gesamte Seite passen, beginnend bei (0,0).

## Schritt 4: Bereiten Sie die Tintenpunkte vor

Jetzt kommt der spaßige Teil – das Definieren der Punkte, aus denen Ihre Tintenanmerkung besteht. 

```csharp
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
```
Dieser Codeblock erstellt eine Liste von Punktarrays, wobei jedes Array eine Reihe von Punkten für Ihren Tintenstrich darstellt. Hier definieren wir drei Punkte, die ein Dreieck bilden. Sie können die Koordinaten an Ihr Design anpassen.

## Schritt 5: Erstellen Sie die Freihandanmerkung

Nachdem Sie Ihre Punkte definiert haben, ist es Zeit, die eigentliche Tintenanmerkung zu erstellen.

```csharp
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList)
{
    Title = "XXX",
    Color = Aspose.Pdf.Color.LightBlue,
    CapStyle = CapStyle.Rounded
};
```
 Wir instantiieren die`InkAnnotation`Objekt, wobei wir die Seite, das Rechteck und die Tintenpunkte übergeben. Zusätzlich setzen wir einige Eigenschaften wie`Title`, `Color` , Und`CapStyle`. Passen Sie diese an Ihre Bedürfnisse an!

## Schritt 6: Rahmen und Deckkraft festlegen

Sie möchten, dass Ihre Anmerkung auffällt? Dann verleihen wir ihr etwas Stil.

```csharp
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
```
Hier fügen wir der Anmerkung einen Rahmen mit einer bestimmten Breite hinzu und legen seine Deckkraft fest, sodass er halbtransparent wird.

## Schritt 7: Hinzufügen der Anmerkung zur Seite

Nachdem Ihre Anmerkung nun vorbereitet ist, ist es an der Zeit, sie der PDF-Seite hinzuzufügen.

```csharp
pdfPage.Annotations.Add(ia);
```
Diese Zeile fügt die zuvor erstellte Tintenanmerkung zur Anmerkungssammlung der Seite hinzu. 

## Schritt 8: Speichern Sie das Dokument

Zum Schluss speichern wir unser geändertes Dokument.

```csharp
dataDir = dataDir + "AddInkAnnotation_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation added successfully.\nFile saved at " + dataDir);
```
 Wir modifizieren unsere`dataDir` um den Ausgabedateinamen einzuschließen und das Dokument zu speichern. Eine Bestätigungsmeldung wird auf der Konsole ausgegeben, um Sie darüber zu informieren, dass alles reibungslos gelaufen ist.

## Abschluss

Und da haben Sie es! Sie haben Ihrem PDF-Dokument mit Aspose.PDF für .NET erfolgreich eine Tintenanmerkung hinzugefügt. Diese einfache, aber effektive Funktion kann Ihre Dokumente verbessern und interaktiv machen. Egal, ob Sie Unterschriften, Notizen oder Kritzeleien hinzufügen, Tintenanmerkungen bieten eine einzigartige Möglichkeit, den Inhalt zu bereichern.

## Häufig gestellte Fragen

### Was ist Aspose.PDF?
Aspose.PDF ist eine Bibliothek zum Erstellen, Bearbeiten und Konvertieren von PDF-Dokumenten in .NET-Anwendungen.

### Kann ich Aspose.PDF kostenlos nutzen?
 Ja! Aspose bietet eine kostenlose Testversion zur Evaluierung ihrer Produkte an. Sie können sie herunterladen[Hier](https://releases.aspose.com/).

### Ist es möglich, mehrere Tintenanmerkungen hinzuzufügen?
 Auf jeden Fall! Sie können mehrere`InkAnnotation` Objekte und fügen Sie sie der Seite Ihres Dokuments hinzu.

### Wo finde ich weitere Beispiele?
 Sie können sich die[Dokumentation](https://reference.aspose.com/pdf/net/) für ausführliche Tutorials und Beispiele.

### Was tun, wenn ich Unterstützung brauche?
 Wenn Sie auf Probleme stoßen, können Sie Hilfe auf der[Support-Forum](https://forum.aspose.com/c/pdf/10).