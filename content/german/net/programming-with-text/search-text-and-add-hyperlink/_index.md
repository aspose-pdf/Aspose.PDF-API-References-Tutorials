---
title: Text durchsuchen und Hyperlink hinzufügen
linktitle: Text durchsuchen und Hyperlink hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in unserem Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.PDF für .NET nach Text suchen und Hyperlinks in PDFs hinzufügen.
type: docs
weight: 450
url: /de/net/programming-with-text/search-text-and-add-hyperlink/
---
## Einführung

Suchen Sie nach einer Möglichkeit, PDFs nicht nur zu bearbeiten, sondern sie auch durch das Einfügen von Hyperlinks zu verbessern? Dann sind Sie hier richtig! Mit der leistungsstarken Aspose.PDF-Bibliothek für .NET können Sie in Ihren PDF-Dokumenten nach Textmustern suchen und nahtlos Hyperlinks hinzufügen. Stellen Sie sich vor, Sie haben ein Dokument, das nicht nur Informationen vermittelt, sondern Leser auch durch einfaches Klicken auf einen Link mit relevanten Ressourcen verbindet. Klingt gut, oder? In diesem Tutorial führen wir Sie Schritt für Schritt durch die Suche nach Text mit regulären Ausdrücken und das Hinzufügen von Hyperlinks in Ihre PDFs. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, Sie werden diesen Prozess einfach und lohnend finden.

## Voraussetzungen

Bevor wir uns ins Detail stürzen, stellen wir sicher, dass Sie alles haben, was Sie brauchen, um mitzumachen. Hier ist eine praktische Checkliste:

- .NET Framework: Auf Ihrem Computer sollte das .NET Framework installiert sein (Version 4.0 oder höher).
- Aspose.PDF für .NET-Bibliothek: Vergessen Sie nicht, die Aspose.PDF-Bibliothek herunterzuladen und in Ihrem Projekt einen Verweis darauf hinzuzufügen. Sie finden sie[Hier](https://releases.aspose.com/pdf/net/).
- IDE: Sie benötigen eine integrierte Entwicklungsumgebung (IDE) wie Visual Studio, um den Code zu schreiben und auszuführen.
- Beispiel-PDF-Datei: Holen Sie sich eine Beispiel-PDF-Datei, an der Sie den Code testen können. Sie können eine einfache PDF-Datei erstellen oder eines Ihrer vorhandenen Dokumente verwenden.

Sobald Sie alles auf dieser Liste abgehakt haben, kann es losgehen!

## Pakete importieren

Der erste Schritt auf unserer Reise besteht darin, die erforderlichen Pakete zu importieren. Hier teilen wir unserem Projekt mit, welche Tools wir verwenden werden. So können Sie es tun:

Beginnen Sie in Ihrer C#-Datei, indem Sie oben die folgenden Namespaces einschließen:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

Durch das Importieren dieser Namespaces geben Sie Ihrem Programm Zugriff auf alle coolen Funktionen, die Aspose.PDF zu bieten hat.

Jetzt, da alles eingerichtet ist, ist es Zeit, loszulegen. Wir werden dies in mehreren Schritten durchgehen, also folgen Sie uns genau!

### Schritt 1: Legen Sie Ihr Dokumentverzeichnis fest

Zuerst müssen Sie angeben, wo Ihre PDF-Dateien gespeichert sind. Ändern Sie die`dataDir` Variable, die auf das Verzeichnis Ihres Dokuments verweist. So geht's:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen Sie unbedingt`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihren Dokumenten.

### Schritt 2: Erstellen Sie einen TextFragmentAbsorber

 Als nächstes brauchen wir ein Tool, um den Text zu finden, den wir verlinken möchten. Geben Sie den`TextFragmentAbsorber`. Dieser kleine Kerl hilft uns bei der Suche nach dem spezifischen Textmuster in unserem PDF.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

Hier suchen wir nach einem bestimmten Muster: vier Ziffern, ein Bindestrich, gefolgt von weiteren vier Ziffern (wie eine Telefonnummer oder eine Jahreszahl).

### Schritt 3: Suche mit regulären Ausdrücken aktivieren

 Wir verwenden bereits einen regulären Ausdruck, um unser Textmuster zu finden, aber wir müssen sicherstellen, dass unser`absorber` weiß, dass es aktiviert ist. Dies ist für eine ordnungsgemäße Suche entscheidend.

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

### Schritt 4: PdfContentEditor initialisieren

 Nachdem wir nun unseren Absorber fertig haben, brauchen wir einen`PdfContentEditor` um mit unserer PDF-Datei zu arbeiten. Mit dieser Klasse können wir eine Bindung zu unserer PDF herstellen und sie bearbeiten.

```csharp
PdfContentEditor editor = new PdfContentEditor();
```

### Schritt 5: Binden Sie Ihre PDF-Quelldatei

Wenn unser Inhaltseditor bereit ist, ist es an der Zeit, ihn an die eigentliche PDF-Datei zu binden, an der wir arbeiten möchten.

```csharp
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Ersetzen Sie unbedingt`"SearchRegularExpressionPage.pdf"` durch den Namen Ihrer PDF-Datei.

### Schritt 6: Akzeptieren Sie den Absorber für die Seite

Wir müssen unserem Redakteur mitteilen, dass wir auf einer bestimmten Seite des Dokuments suchen möchten. In diesem Fall wählen wir Seite 1.

```csharp
editor.Document.Pages[1].Accept(absorber);
```

### Schritt 7: Bereiten Sie sich auf das Durchlaufen von Textfragmenten vor

Jetzt können wir alle von unserem Absorber gefundenen Textfragmente durchgehen. Wir optimieren ihr Erscheinungsbild und richten unseren Hyperlink ein.

```csharp
int[] dashArray = { };
String[] LEArray = { };
Color blue = Color.Blue;
```

Hier legen wir einige Parameter fest, wie beispielsweise die Farbe unseres Hyperlinks.

### Schritt 8: Durchlaufen Sie jedes Textfragment

Für jedes Textfragment, das unserer Suche entspricht, ändern wir seine Farbe und erstellen einen Hyperlink. So sieht das aus:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    Rectangle rect = new Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
    
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, blau, Aktionsname);
    editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
        (float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
```

### Schritt 9: Speichern Sie die bearbeitete PDF-Datei

Wir sind fast fertig! Jetzt ist es Zeit, unsere Änderungen in einer neuen PDF-Datei zu speichern.

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
```

### Schritt 10: Schließen Sie den Editor

Vergessen Sie nicht, Ihr Dokument zu schließen, um die Ressourcen freizugeben!

```csharp
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

Jetzt haben Sie gerade eine PDF-Datei mit einem Hyperlink erstellt, der dynamisch auf Grundlage der Suchergebnisse generiert wurde. Wie cool ist das denn?

## Abschluss

Und da haben Sie es! Indem Sie diese Schritte befolgen, haben Sie gelernt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET eine PDF-Datei durchsuchen und Hyperlinks hinzufügen. Dies kann eine Welt voller Möglichkeiten eröffnen, insbesondere wenn Sie mit Dokumenten arbeiten, die Interaktivität erfordern. Stellen Sie sich vor, Sie fügen Links zu verwandten Ressourcen, Referenzwebsites oder sogar internen Seiten hinzu – und das alles mit nur wenigen Codezeilen!
## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?  
Aspose.PDF für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente in .NET-Anwendungen zu erstellen, zu bearbeiten und zu verwalten.

### Wie kann ich Aspose.PDF für .NET herunterladen?  
 Sie können die Bibliothek herunterladen[Hier](https://releases.aspose.com/pdf/net/).

### Kann ich Aspose.PDF kostenlos testen?  
 Auf jeden Fall! Sie können eine kostenlose Testversion erhalten[Hier](https://releases.aspose.com/).

### Gibt es Support für Aspose-Produkte?  
 Ja, Sie finden Support und Community-Diskussionen[Hier](https://forum.aspose.com/c/pdf/10).

### Wie kann ich eine temporäre Lizenz für Aspose.PDF erhalten?  
 Sie können eine temporäre Lizenz anfordern[Hier](https://purchase.aspose.com/temporary-license/).