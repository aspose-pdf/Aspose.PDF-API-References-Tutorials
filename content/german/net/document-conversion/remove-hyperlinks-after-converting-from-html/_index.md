---
title: Entfernen Sie Hyperlinks nach der Konvertierung aus HTML
linktitle: Entfernen Sie Hyperlinks nach der Konvertierung aus HTML
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie Hyperlinks aus HTML-Dokumenten entfernen, nachdem Sie sie mit Aspose.PDF für .NET in PDF konvertiert haben.
type: docs
weight: 250
url: /de/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## Einführung

Im digitalen Zeitalter ist die Konvertierung von HTML-Dokumenten in PDF eine gängige Aufgabe. Manchmal möchten Sie jedoch aus verschiedenen Gründen Hyperlinks aus der konvertierten PDF-Datei entfernen, beispielsweise um die Lesbarkeit zu verbessern oder unerwünschte Navigation zu verhindern. In diesem Tutorial erfahren Sie, wie Sie dies mit Aspose.PDF für .NET erreichen. 

## Voraussetzungen

Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Dies wird Ihre Entwicklungsumgebung sein.
2.  Aspose.PDF für .NET: Sie benötigen die Aspose.PDF-Bibliothek. Sie können sie herunterladen von[Hier](https://releases.aspose.com/pdf/net/).
3. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, verstehen Sie den Code besser.

## Pakete importieren

Um zu beginnen, müssen Sie die erforderlichen Pakete in Ihr C#-Projekt importieren. So können Sie das tun:

1. Öffnen Sie Ihr Visual Studio-Projekt.
2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt und wählen Sie „NuGet-Pakete verwalten“ aus.
3.  Suchen nach`Aspose.PDF` und installieren Sie es.

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

Nachdem Sie nun alles eingerichtet haben, wollen wir den Vorgang zum Entfernen von Hyperlinks aus einer HTML-Datei nach der Konvertierung in PDF aufschlüsseln.

## Schritt 1: Einrichten des Dokumentverzeichnisses

Als Erstes müssen Sie den Pfad zu Ihrem Dokumentverzeichnis angeben. Hier befindet sich Ihre HTML-Datei und hier wird auch die Ausgabe-PDF-Datei gespeichert.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem Ihre HTML-Datei gespeichert ist.

## Schritt 2: Laden Sie das HTML-Dokument

 Als nächstes laden Sie das HTML-Dokument mit dem`Document` Klasse von Aspose.PDF. Mit dieser Klasse können Sie problemlos mit PDF-Dokumenten arbeiten.

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

 Hier laden wir die HTML-Datei mit dem Namen`SampleHtmlFile.html`. Stellen Sie sicher, dass diese Datei in Ihrem angegebenen Verzeichnis vorhanden ist.

## Schritt 3: Speichern Sie das Dokument im Memory Stream

Bevor wir mit der Verarbeitung der Anmerkungen beginnen, müssen wir das Dokument in einem Speicherstream speichern. Dieser Schritt ist entscheidend, da er das Dokument für die weitere Bearbeitung vorbereitet.

```csharp
doc.Save(new MemoryStream());
```

Diese Zeile speichert das Dokument im Speicher, sodass wir damit arbeiten können, ohne es sofort auf die Festplatte zu schreiben.

## Schritt 4: Durch Anmerkungen iterieren

Nun durchlaufen wir die Anmerkungen im Dokument. Anmerkungen sind Elemente wie Links, Kommentare und Hervorhebungen. Wir sind insbesondere an Linkanmerkungen interessiert.

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        // Verarbeiten der Linkanmerkung
    }
}
```

In dieser Schleife prüfen wir, ob der Annotationstyp ein Link ist. Wenn ja, fahren wir mit den nächsten Schritten fort.

## Schritt 5: Entfernen der Hyperlink-Aktion

Für jede Linkannotation müssen wir prüfen, ob sie eine Hyperlink-Aktion hat. Wenn ja, entfernen wir den Hyperlink, indem wir seine URI auf eine leere Zeichenfolge setzen.

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

Dieser Codeausschnitt stellt sicher, dass die Hyperlink-Aktion effektiv entfernt wird.

## Schritt 6: Textfragmente aufnehmen

Als nächstes werden wir die mit der Linkanmerkung verknüpften Textfragmente aufnehmen. Dadurch können wir das Erscheinungsbild des Textes bearbeiten.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

 Hier erstellen wir eine`TextFragmentAbsorber` und stellen Sie die Suchoptionen auf das Rechteck der Anmerkung ein. Dies hilft uns, den verlinkten Text zu finden.

## Schritt 7: Textdarstellung ändern

Sobald wir die Textfragmente haben, können wir ihr Aussehen ändern. In diesem Fall entfernen wir die Unterstreichung und ändern die Textfarbe in Schwarz.

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

Dieser Schritt verbessert die Lesbarkeit des Textes durch Entfernen der Hyperlink-Formatierung.

## Schritt 8: Löschen der Anmerkung

Nachdem wir den Text geändert haben, können wir die Linkanmerkung sicher aus dem Dokument löschen.

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

Diese Zeile entfernt den Hyperlink aus der PDF-Datei und stellt sicher, dass er in der endgültigen Ausgabe nicht mehr vorhanden ist.

## Schritt 9: Speichern Sie das geänderte Dokument

Abschließend müssen wir das geänderte Dokument in einer neuen PDF-Datei speichern. Dies ist der letzte Schritt in unserem Prozess.

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Diese Zeile speichert das Dokument ohne die Hyperlinks und erstellt eine neue PDF-Datei mit dem Namen`RemoveHyperlinksFromText_out.pdf`.

## Abschluss

Und da haben Sie es! Sie haben erfolgreich Hyperlinks aus einem HTML-Dokument entfernt, nachdem Sie es mit Aspose.PDF für .NET in PDF konvertiert haben. Dieser Vorgang verbessert nicht nur die Lesbarkeit Ihres PDFs, sondern gibt Ihnen auch Kontrolle über den von Ihnen präsentierten Inhalt. 

## Häufig gestellte Fragen

### Kann ich Hyperlinks aus jedem PDF-Dokument entfernen?
Ja, Sie können mit Aspose.PDF für .NET Hyperlinks aus jedem PDF-Dokument entfernen.

### Ist die Nutzung von Aspose.PDF kostenlos?
 Aspose.PDF bietet eine kostenlose Testversion an, für den vollen Funktionsumfang müssen Sie jedoch eine Lizenz erwerben. Überprüfen Sie die[Kaufen-Seite](https://purchase.aspose.com/buy).

### Was ist, wenn bei der Verwendung von Aspose.PDF Probleme auftreten?
 Hilfe finden Sie auf der[Support-Forum](https://forum.aspose.com/c/pdf/10).

### Kann ich mit Aspose andere Dateiformate in PDF konvertieren?
Ja, Aspose unterstützt verschiedene Dateiformate für die Konvertierung in PDF.

### Wo kann ich Aspose.PDF für .NET herunterladen?
 Sie können es herunterladen von der[Downloadlink](https://releases.aspose.com/pdf/net/).