---
title: Text suchen und Rechteck zeichnen
linktitle: Text suchen und Rechteck zeichnen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET nach Text in PDFs suchen und ihn mit Rechtecken hervorheben! Einfaches Schritt-für-Schritt-Tutorial für erweiterte PDF-Bearbeitungsfähigkeiten.
type: docs
weight: 460
url: /de/net/programming-with-text/search-text-and-draw-rectangle/
---
## Einführung

Möchten Sie Ihre PDF-Bearbeitungsfähigkeiten verbessern? Möchten Sie lernen, wie Sie in PDF-Dateien nach bestimmtem Text suchen und ihn mit einem Rechteck hervorheben? Dann sind Sie hier genau richtig! Heute zeige ich Ihnen, wie Sie mit Aspose.PDF für .NET in einem PDF-Dokument nach Text suchen und Rechtecke darum zeichnen. Dieser Artikel bietet eine Schritt-für-Schritt-Anleitung, die auf Klarheit und Nützlichkeit ausgelegt ist, damit Sie diese Techniken nachvollziehen und auf Ihre Projekte anwenden können. 

## Voraussetzungen

Bevor wir uns in das Tutorial vertiefen, bereiten wir alles vor, was Sie für einen reibungslosen Arbeitsablauf benötigen:

1. Grundlegende Kenntnisse in .NET: Sie sollten mit der C#-Programmierung und dem .NET-Framework vertraut sein, um diesem Tutorial effektiv folgen zu können.
   
2. Visual Studio installiert: Sie benötigen eine integrierte Entwicklungsumgebung (IDE), um Ihren Code zu schreiben und zu testen. Visual Studio Community ist eine großartige Option und kostenlos.
   
3. Aspose.PDF für .NET: Sie müssen die Aspose.PDF-Bibliothek in Ihrem Projekt installiert haben. Sie können sie herunterladen[Hier](https://releases.aspose.com/pdf/net/) oder erwägen Sie eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) für erweiterte Funktionen.
   
4.  Beispiel-PDF-Dokument: Für dieses Tutorial benötigen Sie eine Beispiel-PDF-Datei mit dem Namen`SearchAndGetTextFromAll.pdf` in Ihrem Projektverzeichnis gespeichert. 

## Pakete importieren

Um zu beginnen, müssen Sie zunächst die erforderlichen Pakete in Ihr .NET-Projekt importieren. Folgen Sie diesen Schritten:

### Öffnen Sie Visual Studio

Starten Sie Visual Studio und erstellen Sie eine neue Konsolenanwendung oder verwenden Sie eine vorhandene, in der Sie die PDF-Funktionen implementieren möchten.

### Fügen Sie Aspose.PDF zu Ihrem Projekt hinzu

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt.
2. Wählen Sie „NuGet-Pakete verwalten“ aus.
3.  Suchen nach`Aspose.PDF` und installieren Sie die neueste Version.

Auf diese Weise legen Sie den Grundstein für alle erstaunlichen PDF-Manipulationen, die Sie durchführen werden.

## Namespaces importieren

Oben in Ihrer Programmdatei möchten Sie die relevanten Namespaces aus der Aspose-Bibliothek importieren:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

Dies erleichtert den Zugriff auf Klassen und Methoden innerhalb der Aspose.PDF-Bibliothek für Ihre Aufgaben.


Nachdem Sie nun alles eingerichtet haben, unterteilen wir den Vorgang der Textsuche in einer PDF-Datei und des Zeichnens eines Rechtecks darum in überschaubare Schritte.

## Schritt 1: Legen Sie den Pfad für Ihr Dokument fest

 Legen Sie zunächst den Pfad zu Ihrer PDF-Datei fest. Ersetzen Sie`YOUR DOCUMENT DIRECTORY` mit dem tatsächlichen Pfad, auf dem Ihr`SearchAndGetTextFromAll.pdf` gespeichert ist.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument

 Erstellen Sie als nächstes eine Instanz des`Document` Klasse zum Laden Ihres PDF:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

Diese Codezeile öffnet Ihre angegebene PDF-Datei und ermöglicht Ihnen weitere Bearbeitungen.

## Schritt 3: Erstellen Sie einen Textabsorber

 Nun benötigen Sie eine Möglichkeit, innerhalb dieses Dokuments nach Text zu suchen. Dazu verwenden wir die`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Der reguläre Ausdruck`@"[\S]+"` ist so konzipiert, dass es mit jeder Zeichenfolge im PDF übereinstimmt, die keine Leerzeichen enthält. 

## Schritt 4: Konfigurieren Sie die Textsuchoptionen

Als nächstes sollten Sie die Textsuchoptionen einrichten:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

 Hier die`true` Parameter bedeutet, dass die Suche Groß- und Kleinschreibung berücksichtigt. Sie können ihn auf`false` wenn Sie eine Suche ohne Berücksichtigung der Groß-/Kleinschreibung wünschen.

## Schritt 5: Akzeptieren Sie den Text Absorber im Dokument

 Mit Ihrem`TextFragmentAbsorber` und die Suchoptionen sind bereit. Jetzt ist es an der Zeit, Text aus dem Dokument aufzunehmen:

```csharp
document.Pages.Accept(textAbsorber);
```

Diese Methode untersucht jede Seite in Ihrem PDF, um Textfragmente zu finden, die dem angegebenen Muster entsprechen.

## Schritt 6: Erstellen Sie einen PdfContentEditor

 Um Formen auf dem Dokument zu zeichnen, benötigen Sie die`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

Mit diesem Editor können Sie den PDF-Inhalt problemlos bearbeiten und ändern.

## Schritt 7: Durch gefundene Textfragmente schleifen

Nun möchten Sie die gefundenen Textfragmente durchlaufen, um Rechtecke um sie herum zu zeichnen:

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

 Diese Schleife durchläuft alle Textfragmente und deren Segmente und ruft einen`DrawBox` Methode zum Zeichnen von Rechtecken.

## Schritt 8: Definieren Sie die DrawBox-Methode

 Sie müssen definieren,`DrawBox` Methode, die die Logik zum Zeichnen des Rechtecks handhabt. Hier ist eine einfache Implementierung:

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // Berechnen Sie die Abmessungen des Rechtecks auf Basis des Textsegments
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // Zeichnen Sie ein Rechteck mit den berechneten Werten
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

Diese Methode bestimmt die Position und Größe des Rechtecks basierend auf dem Begrenzungsrechteck des Segments und verwendet den Editor, um es zu zeichnen.

## Schritt 9: Speichern Sie das geänderte Dokument

Nachdem Sie Rechtecke um den gefundenen Text gezeichnet haben, können Sie das geänderte Dokument speichern:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

Stellen Sie sicher, dass Ihre neue Datei unter einem eindeutigen Namen gespeichert wird, um ein Überschreiben Ihres Originaldokuments zu vermeiden.

## Schritt 10: Bestätigungsnachricht

Drucken Sie abschließend eine Bestätigungsmeldung auf der Konsole aus, um Sie darüber zu informieren, dass der Vorgang erfolgreich war:

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

Und da haben Sie es! Sie haben erfolgreich ein Skript erstellt, um in einer PDF-Datei nach Text zu suchen und ihn mit Rechtecken hervorzuheben.

## Abschluss

Herzlichen Glückwunsch! Sie haben gerade eine leistungsstarke Fähigkeit freigeschaltet, die Ihre PDF-Bearbeitungsfähigkeiten mit Aspose.PDF für .NET erheblich verbessern kann. Mit nur wenigen einfachen Schritten können Sie nach beliebigem Text in Ihrem Dokument suchen und ihn visuell hervorheben, wodurch Ihre PDF-Dokumente interaktiver und handlicher werden. Zögern Sie nicht, mit verschiedenen Regex-Mustern und Farboptionen zu experimentieren, um dieses Tool wirklich zu Ihrem eigenen zu machen!

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine Bibliothek, die eine umfassende Möglichkeit zum programmgesteuerten Erstellen, Bearbeiten und Konvertieren von PDF-Dokumenten bietet.

### Kann ich Aspose.PDF kostenlos nutzen?
Ja, Aspose bietet eine kostenlose Testversion an, mit der Sie die Funktionen der Bibliothek testen können. Probieren Sie es aus[Hier](https://releases.aspose.com/).

### Welche Programmiersprache muss ich mit Aspose.PDF für .NET verwenden?
Aspose.PDF für .NET ist für die Verwendung mit C# und anderen .NET-Sprachen konzipiert.

### Wie bekomme ich Hilfe zu Aspose.PDF?
 Sie können das Aspose-Supportforum besuchen, um Hilfe zu allen möglichen Problemen oder Fragen zu erhalten. Finden Sie Support[Hier](https://forum.aspose.com/c/pdf/10).

### Wo lade ich Aspose.PDF für .NET herunter?
 Sie können die Bibliothek von der Aspose-Website herunterladen.[Hier](https://releases.aspose.com/pdf/net/).