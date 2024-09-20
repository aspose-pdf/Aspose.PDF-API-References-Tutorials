---
title: Benutzerdefinierte Tabstopps in der PDF-Datei
linktitle: Benutzerdefinierte Tabstopps in der PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET benutzerdefinierte Tabstopps in einer PDF einrichten. Dieses Tutorial enthält schrittweise Anweisungen zum professionellen Ausrichten von Text.
type: docs
weight: 120
url: /de/net/programming-with-text/custom-tab-stops/
---
## Einführung

Mussten Sie schon einmal Text in einer PDF-Datei formatieren und wünschten, Sie könnten die Ausrichtung jedes einzelnen Wortes präzise steuern? Hier kommen Tabstopps ins Spiel! Genau wie in Word-Dokumenten können Sie benutzerdefinierte Tabstopps verwenden, um Ihren Text an bestimmten Stellen in Ihrer PDF-Datei perfekt auszurichten. Egal, ob Sie Inhalte rechtsbündig, zentriert oder linksbündig ausrichten möchten, Aspose.PDF für .NET macht es Ihnen leicht. In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET benutzerdefinierte Tabstopps in Ihrer PDF-Datei einrichten. Am Ende können Sie ganz einfach ein schön ausgerichtetes Dokument erstellen.

## Voraussetzungen

Bevor wir beginnen, müssen Sie Folgendes beachten:

-  Aspose.PDF für .NET: Sie müssen die Aspose.PDF-Bibliothek installiert haben. Sie können[Laden Sie es hier herunter](https://releases.aspose.com/pdf/net/).
- .NET-Entwicklungsumgebung: Stellen Sie sicher, dass Sie Visual Studio oder eine andere IDE zum Ausführen von .NET-Anwendungen eingerichtet haben.
- Grundlegende Kenntnisse in C#: Wir werden Code in C# schreiben, daher sind gewisse Kenntnisse in dieser Sprache empfehlenswert.
-  Temporäre Lizenz: Sie können die[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/)um alle Funktionen von Aspose.PDF für .NET freizuschalten.

Wenn Sie alles bereit haben, können wir mit dem Importieren der erforderlichen Pakete und dem Einrichten der Umgebung fortfahren.

## Pakete importieren

Um zu beginnen, müssen Sie die Aspose.PDF-Namespaces importieren. So geht's:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

 Diese beiden Zeilen sind wesentlich.`Aspose.Pdf` Namespace stellt die Dokumentstruktur bereit, während`Aspose.Pdf.Text` gibt uns Zugriff auf textspezifische Funktionen wie benutzerdefinierte Tabstopps.

Lassen Sie uns den Vorgang zum Einrichten benutzerdefinierter Tabstopps in einer PDF-Datei aufschlüsseln. Wir gehen jeden Schritt im Detail durch, um sicherzustellen, dass Sie genau verstehen, was passiert.

## Schritt 1: Ein neues PDF-Dokument erstellen

Als Erstes müssen Sie ein neues PDF-Dokument erstellen. Betrachten Sie es als Ihre Leinwand. Sie fügen Seiten hinzu und platzieren dann Ihren formatierten Text darauf.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
```

In diesem Snippet:
-  Wir schaffen ein neues`Document` Objekt.
-  Wir fügen dem Dokument eine neue Seite hinzu mit`Pages.Add()`. Hier fügen wir den Text mit Tabstopps ein.

## Schritt 2: Tabstopps einrichten

Da wir nun ein leeres Dokument haben, ist es an der Zeit, die Tabulatoren zu definieren. Tabulatoren steuern, wie Text an verschiedenen Positionen auf der Seite ausgerichtet wird. Sie möchten beispielsweise möglicherweise einen Teil des Textes rechts und einen anderen Teil zentriert oder links ausrichten.

```csharp
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
```

Hier führen wir Folgendes durch:
-  Initialisieren Sie einen`TabStops` Objekt, das unsere benutzerdefinierten Tabstopps enthält.
-  Fügen Sie bei der 100-Pixel-Marke einen Tabulator hinzu mit`ts.Add(100)`. Dadurch wird definiert, wo die Registerkarte angezeigt wird.
-  Stellen Sie den Ausrichtungstyp ein auf`Right`, was bedeutet, dass Text, der auf diesen Tabulatorstopp trifft, rechtsbündig ausgerichtet wird.
- Definieren Sie einen Führungstyp. Führungslinien sind die Punkte oder Striche, die den Raum vor dem Tabulatorstopp füllen. In diesem Fall verwenden wir eine durchgezogene Linie.

## Schritt 3: Weitere Tabstopps hinzufügen

Wir können so viele Tabstopps hinzufügen, wie wir benötigen. In diesem Beispiel werden wir einen zentrierten und einen linksbündigen Tabstopp hinzufügen.

```csharp
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

- Der zweite Tabulatorstopp wird auf 200 Pixel mit zentrierter Ausrichtung und einem Bindestrich als Füllzeichen eingestellt.
- Der dritte Tabulatorstopp wird bei 300 Pixeln platziert, ist linksbündig ausgerichtet und verwendet einen gepunkteten Füllstrich.

## Schritt 4: Text mit Tabulatoren erstellen

Nachdem die Tabstopps eingerichtet sind, ist es an der Zeit, Text zu erstellen, der sie verwendet. Sie können sich diese Tabstopps als unsichtbare Hilfslinien vorstellen, die Ihnen dabei helfen, Ihren Inhalt an verschiedenen Positionen auszurichten.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
```

- `TextFragment` stellt einen Textabschnitt dar.
- Wir verwenden Tabulatormarkierungen (`#$TAB`), um dem PDF mitzuteilen, wo die Tabstopps angewendet werden sollen.
-  Beispielsweise in`text0`, `#$TABHead1` wird nach dem ersten Tabulator ausgerichtet,`#$TABHead2` wird an der zweiten ausgerichtet und so weiter.

## Schritt 5: Segmente zum Text hinzufügen

 Manchmal möchten Sie Ihren Text in mehrere Abschnitte aufteilen, von denen jeder einen eigenen Tabstopp hat. Hier`TextSegment` ist praktisch.

```csharp
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
```

In diesem Fall:
-  Wir beginnen mit`#$TABdata21`, das am ersten Tabulatorstopp ausgerichtet wird.
-  Wir fügen weitere Segmente hinzu wie`data22` Und`data23`, die jeweils an unterschiedlichen Tabulatorstopps ausgerichtet sind.

## Schritt 6: Text zur PDF-Seite hinzufügen

Nachdem wir nun alle unsere Textfragmente erstellt haben, ist es Zeit, sie der Seite hinzuzufügen.

```csharp
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

 Dieser Code fügt jeweils`TextFragment`auf die PDF-Seite und achten Sie dabei darauf, dass der Text entsprechend den Tabstopps formatiert wird.

## Schritt 7: Speichern Sie das PDF-Dokument

Schließlich müssen wir das Dokument in dem von Ihnen angegebenen Verzeichnis speichern.

```csharp
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

- Die PDF-Datei wird mit den angewendeten benutzerdefinierten Tabstopps gespeichert.
- Es wird eine Meldung angezeigt, die die erfolgreiche Erstellung der Datei bestätigt.

## Abschluss

Und da haben Sie es! Indem Sie dieser Anleitung gefolgt sind, haben Sie gelernt, wie Sie mit Aspose.PDF für .NET benutzerdefinierte Tabstopps in einem PDF-Dokument erstellen. Mit Tabstopps können Sie Text strukturiert und optisch ansprechend ausrichten und so Ihre PDFs professioneller gestalten. Egal, ob Sie Rechnungsdetails, Tabellen oder eine andere Form von Daten ausrichten, diese Funktion gibt Ihnen die vollständige Kontrolle über die Textplatzierung.

## Häufig gestellte Fragen

### Kann ich Tabstopps auf vorhandene PDFs anwenden?  
Ja, Sie können vorhandene PDFs ändern, indem Sie benutzerdefinierte Tabulatoren zum Ausrichten von Text hinzufügen.

### Welche Anführertypen gibt es?  
Sie können zwischen durchgezogenen, gestrichelten, gepunkteten und anderen Füllzeichentypen wählen, um den Raum vor dem Tabulatorstopp zu füllen.

### Kann ich in einer einzigen Zeile mehrere Ausrichtungsarten hinzufügen?  
Auf jeden Fall! Wie im Beispiel gezeigt, können Sie die Ausrichtung rechts, links und zentriert in derselben Zeile kombinieren.

### Gibt es eine Begrenzung für die Anzahl der Tabstopps, die ich hinzufügen kann?  
Nein, Sie können so viele Tabstopps hinzufügen, wie Sie für Ihre Designanforderungen benötigen.

### Kann ich die Position der Tabulatoren anpassen?  
Ja, Sie können die genaue Pixelposition jedes Tabstopps so festlegen, dass sie zu Ihrem Layout passt.