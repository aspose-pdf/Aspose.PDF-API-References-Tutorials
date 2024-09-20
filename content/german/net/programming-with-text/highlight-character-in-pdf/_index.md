---
title: Zeichen in PDF-Datei hervorheben
linktitle: Zeichen in PDF-Datei hervorheben
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser umfassenden Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET Zeichen in einer PDF-Datei hervorheben.
type: docs
weight: 240
url: /de/net/programming-with-text/highlight-character-in-pdf/
---
## Einführung

Beim Arbeiten mit PDFs besteht häufig die Notwendigkeit, Text oder Zeichen hervorzuheben – sei es für akademische Zwecke, zum Bearbeiten oder einfach zur Verbesserung der Lesbarkeit. Stellen Sie sich vor, Sie haben ein schönes Dokument, möchten aber bestimmte Teile hervorheben. Hier kommt das Hervorheben ins Spiel! In diesem Tutorial erfahren Sie, wie Sie mithilfe der leistungsstarken Aspose.PDF-Bibliothek für .NET Zeichen in einer PDF-Datei hervorheben. 

## Voraussetzungen

Bevor wir uns in den Code stürzen, stellen wir sicher, dass wir alles haben, was wir brauchen. Folgendes benötigen Sie:

1. Eine Entwicklungsumgebung: Dieses Tutorial setzt voraus, dass Sie in Visual Studio oder einer ähnlichen .NET IDE arbeiten.
2.  Aspose.PDF für .NET-Bibliothek: Wenn Sie es noch nicht getan haben, können Sie[Laden Sie es hier herunter](https://releases.aspose.com/pdf/net/) und fügen Sie es Ihrem Projekt hinzu. 
3. Grundkenntnisse in C#: Eine Einführung in die C#-Programmierung hilft Ihnen, die Implementierung leicht zu verstehen.
4. Ein PDF-Dokument: Sie sollten eine Beispiel-PDF-Datei zum Arbeiten bereit haben. Sie können eine erstellen oder ein vorhandenes Dokument verwenden.

## Pakete importieren

Um zu beginnen, müssen wir die erforderlichen Namespaces importieren. Dazu müssen Sie sie oben in Ihrer C#-Datei einfügen:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Devices;
using Aspose.Pdf.Text;
using System;
using System.Drawing;
```

Diese Pakete sind für das Erstellen, Bearbeiten und Verarbeiten von PDF-Dokumenten mithilfe der Aspose-Bibliothek unerlässlich.

Lassen Sie uns nun den Vorgang zum Hervorheben von Zeichen in Ihrer PDF-Datei in einfachere Schritte aufteilen. 

## Schritt 1: Initialisieren Sie das PDF-Dokument

Der erste Schritt besteht darin, Ihr PDF-Dokument zu initialisieren. Dazu müssen Sie die PDF-Datei laden, mit der Sie arbeiten möchten. So geht's:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Stellen Sie sicher, dass Sie den richtigen Pfad festlegen.
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```
Ersetzen Sie in diesem Snippet`YOUR DOCUMENT DIRECTORY` mit dem tatsächlichen Pfad auf Ihrem Computer, in dem sich Ihre PDF-Eingabedatei befindet. Die`Aspose.Pdf.Document` Die Klasse wird instanziiert, um Ihr PDF zu laden.

## Schritt 2: Richten Sie den Rendering-Prozess ein

Als nächstes müssen wir den Rendering-Prozess für unser Dokument vorbereiten. Dies ist wichtig, um die Zeichen auf der Seite genau hervorzuheben.

```csharp
int resolution = 150; // Stellen Sie die Auflösung für die Bildaufnahme ein.
using (MemoryStream ms = new MemoryStream())
{
    PdfConverter conv = new PdfConverter(pdfDocument);
    conv.Resolution = new Resolution(resolution, resolution);
    conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```
 Wir definieren eine Auflösung für Klarheit, die eine korrekte Darstellung des Textes ermöglicht.`PdfConverter`wandelt die PDF-Seiten in Bilder um, sodass wir darauf zeichnen können.

## Schritt 3: Erstellen Sie ein Grafikobjekt zum Zeichnen

Nachdem wir den Zeichenvorgang eingerichtet haben, müssen wir ein Grafikobjekt erstellen, in dem wir unsere Hervorhebungen durchführen:

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
    float scale = resolution / 72f; // Skalierungsfaktor.
    gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
```
Hier erstellen wir das Grafikobjekt aus dem Bitmap-Bild. Die Transformation hilft dabei, das Rendering so anzupassen, dass es der benötigten Auflösung entspricht.

## Schritt 4: Jede Seite durchlaufen und Text markieren

Lassen Sie uns nun jede Seite im PDF durchgehen und die Textfragmente suchen, die wir hervorheben möchten:

```csharp
for (int i = 0; i < pdfDocument.Pages.Count; i++)
{
    Page page = pdfDocument.Pages[i + 1]; // Seiten sind in Aspose 1-indiziert.
    TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
    textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
    page.Accept(textFragmentAbsorber);
```
 Wir rufen jede Seite auf und suchen den gesamten Text mithilfe des`TextFragmentAbsorber` Das reguläre Ausdrucksmuster`@"[\S]+"` erfasst alle Zeichen außer Leerzeichen.

## Schritt 5: Textfragmente extrahieren und hervorheben

Jetzt ist es an der Zeit, die Textfragmente zu extrahieren und hervorzuheben. Dazu zeichnen wir Rechtecke um die Zeichen, die wir hervorheben möchten:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

foreach (TextFragment textFragment in textFragmentCollection)
{
    // Hier wird die Logik hervorgehoben
    for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
    {
        TextSegment segment = textFragment.Segments[segNum];
        for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
        {
            CharInfo characterInfo = segment.Characters[charNum];
            gr.DrawRectangle(Pens.Black, 
                (float)characterInfo.Rectangle.LLX, 
                (float)characterInfo.Rectangle.LLY, 
                (float)characterInfo.Rectangle.Width, 
                (float)characterInfo.Rectangle.Height);
        }
    }
}
```
Wir durchlaufen jedes Textfragment, seine Segmente und einzelnen Zeichen und zeichnen mithilfe des zuvor erstellten Grafikobjekts Rechtecke um sie herum.

## Schritt 6: Speichern Sie das geänderte Bild

Nach dem Hervorheben müssen Sie das resultierende Bild als neue PNG-Datei speichern:

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```
Diese Zeile speichert Ihr geändertes Bitmap-Bild als PNG-Datei im angegebenen Verzeichnis. 

## Schritt 7: Abschließend Ausnahmebehandlung

Schließlich empfiehlt es sich, Ihren Code in einen Try-Catch-Block einzuschließen, um sicherzustellen, dass unerwartete Fehler ordnungsgemäß behandelt werden:

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get a 30-day temporary license from [here](https://Purchase.aspose.com/temporary-license/).");
}
```

Dieser Block fängt alle Ausnahmen ab, die während des Vorgangs auftreten können, und gibt dem Benutzer informatives Feedback.

## Abschluss

Und da haben Sie es! Sie haben erfolgreich Zeichen in einer PDF-Datei mit Aspose.PDF für .NET hervorgehoben. Diese leistungsstarke Bibliothek öffnet Türen zu endlosen Möglichkeiten der PDF-Bearbeitung – egal, ob Sie mit Anmerkungen arbeiten, Formulare ausfüllen oder sogar Dokumente konvertieren. Denken Sie bei Ihrer weiteren Arbeit mit Aspose daran, dass Übung der Schlüssel ist. Experimentieren Sie weiter mit verschiedenen Funktionen und Sie werden schnell zum PDF-Profi!

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine Bibliothek, die das programmgesteuerte Erstellen, Bearbeiten und Konvertieren von PDF-Dokumenten in .NET-Anwendungen ermöglicht.

### Kann ich mehrere Textfragmente gleichzeitig markieren?
Ja, der bereitgestellte Code kann angepasst werden, um mehrere Fragmente hervorzuheben, indem der gesamte Text im PDF durchlaufen wird.

### Gibt es eine kostenlose Version von Aspose.PDF?
Ja, Aspose bietet eine kostenlose Testversion an, sodass Sie die Bibliothek vor dem Kauf testen können.

### Benötige ich Lizenzen, um Aspose.PDF zu verwenden?
Ja, für die kommerzielle Nutzung ist eine gültige Lizenz erforderlich. Sie können jedoch zum Testen eine 30-tägige, temporäre Lizenz erwerben.

### Wo finde ich weitere Dokumentation?
 Weitere Informationen finden Sie im[Aspose.PDF-Dokumentation](https://reference.aspose.com/pdf/net/) für ausführlichere Informationen zur Implementierung und den Funktionen.