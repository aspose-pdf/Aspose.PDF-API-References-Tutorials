---
title: Markierten Text in PDF-Datei extrahieren
linktitle: Markierten Text in PDF-Datei extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in diesem Tutorial, wie Sie mit Aspose.PDF für .NET markierten Text effizient aus einer PDF-Datei extrahieren. Perfekt für die Datenanalyse und Inhaltsüberprüfung.
type: docs
weight: 60
url: /de/net/annotations/extracthighlightedtext/
---
## Einführung

Beim Arbeiten mit PDF-Dateien kann das Extrahieren von markiertem Text eine wichtige Aufgabe sein, sei es für die Datenanalyse, die Inhaltsüberprüfung oder einfach zum Organisieren Ihrer Notizen. Wenn Sie Aspose.PDF für .NET verwenden, ist dieser Vorgang unkompliziert und effizient. In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET markierten Text aus einem PDF-Dokument extrahieren. Wir behandeln alles von den Voraussetzungen bis zur Schritt-für-Schritt-Anleitung, damit Sie am Ende ein umfassendes Verständnis haben.

## Voraussetzungen

Bevor Sie sich in den Code vertiefen, müssen Sie einige Dinge vorbereitet haben:

-  Aspose.PDF für .NET-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert haben. Wenn nicht, können Sie sie von der[Veröffentlichungsseite](https://releases.aspose.com/pdf/net/).
- Entwicklungsumgebung: Sie sollten eine funktionierende Entwicklungsumgebung wie beispielsweise Visual Studio eingerichtet haben.
- Grundkenntnisse in C#: Vertrautheit mit der Programmiersprache C# und der objektorientierten Programmierung ist unbedingt erforderlich.
-  Eine gültige Aspose-Lizenz: Sie können zwar mit einer kostenlosen Testversion beginnen, sollten aber den Erwerb einer[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) oder den Kauf eines von[Hier](https://purchase.aspose.com/buy) zur uneingeschränkten Nutzung.

## Pakete importieren

Zu Beginn müssen Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren. Dies ist entscheidend für den Zugriff auf die von Aspose.PDF für .NET bereitgestellten Klassen und Methoden.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Lassen Sie uns nun den Prozess des Extrahierens von markiertem Text aus einer PDF-Datei mit Aspose.PDF für .NET aufschlüsseln. Jeder Schritt wird ausführlich erklärt, damit Sie die zugrunde liegenden Konzepte und die Implementierung verstehen.

## Schritt 1: Richten Sie Ihr Projektverzeichnis ein

Als Erstes müssen Sie Ihr Projektverzeichnis einrichten, in dem sich Ihre PDF-Datei befindet. Hier geschieht die Magie.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"`durch den tatsächlichen Pfad zu Ihrem Verzeichnis, in dem sich die PDF-Datei befindet. Aus diesem Verzeichnis ruft die Anwendung die PDF-Datei zur Verarbeitung ab.

## Schritt 2: Laden Sie das PDF-Dokument

 Als nächstes müssen Sie das PDF-Dokument laden, aus dem Sie den markierten Text extrahieren möchten. Dies geschieht mit dem`Document` Klasse bereitgestellt von Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

 Der`Document` Klasse wird mit dem Pfad zur PDF-Datei instanziiert. Hier`"ExtractHighlightedText.pdf"` ist der Name der PDF-Datei, die den markierten Text enthält. Stellen Sie sicher, dass diese Datei im angegebenen Verzeichnis vorhanden ist.

## Schritt 3: Zugriff auf die Annotations-Sammlung

Sobald das PDF-Dokument geladen ist, besteht der nächste Schritt darin, auf die Anmerkungen auf der ersten Seite des Dokuments zuzugreifen. Anmerkungen werden in PDFs verwendet, um zusätzliche Informationen wie Hervorhebungen, Kommentare und mehr hinzuzufügen.

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
```

 Der`Annotations` Eigentum der`Page` Objekt bietet Zugriff auf alle Anmerkungen auf einer bestimmten Seite des PDF. Hier durchlaufen wir jede Anmerkung auf der ersten Seite.

## Schritt 4: Filtern nach hervorgehobenen Textanmerkungen

Da wir nun Zugriff auf alle Anmerkungen haben, müssen wir nur die hervorgehobenen Textanmerkungen herausfiltern. Dies erreichen wir, indem wir den Typ jeder Anmerkung überprüfen.

```csharp
if (annotation is TextMarkupAnnotation)
{
    TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
```

 Der`TextMarkupAnnotation` Klasse wird verwendet, um Textmarkierungsanmerkungen, einschließlich Hervorhebungen, darzustellen. Die`is` Das Schlüsselwort prüft, ob die Annotation vom Typ ist`TextMarkupAnnotation` , und wenn dies der Fall ist, wird die Annotation in`TextMarkupAnnotation`.

## Schritt 5: Den markierten Text extrahieren

Nachdem die hervorgehobene Anmerkung identifiziert wurde, besteht der nächste Schritt darin, den mit der Hervorhebung verknüpften Text zu extrahieren.

```csharp
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
foreach (TextFragment tf in collection)
{
    Console.WriteLine(tf.Text);
}
```

 Der`GetMarkedTextFragments()` Methode gibt eine Sammlung von`TextFragment` Objekte, die jeweils einen Teil des hervorgehobenen Textes darstellen. Wir durchlaufen diese Sammlung und drucken den Text jedes Fragments auf der Konsole.

## Abschluss

Das Extrahieren von markiertem Text aus einer PDF-Datei mit Aspose.PDF für .NET ist eine leistungsstarke Funktion, die Ihren Arbeitsablauf optimieren kann, insbesondere wenn Sie mit großen Dokumenten arbeiten. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie diese Funktion problemlos in Ihre eigenen Projekte implementieren. Egal, ob Sie Ihre Notizen organisieren, Berichte erstellen oder Datenanalysen durchführen, diese Methode bietet eine nahtlose Lösung zum Extrahieren und Verwenden von markiertem Text.

## Häufig gestellte Fragen

### Kann ich mit dieser Methode andere Arten von Anmerkungen extrahieren?  
 Ja, Sie können andere Arten von Anmerkungen extrahieren, indem Sie die`if` Bedingung zur Überprüfung auf verschiedene Annotationstypen, wie z. B.`TextAnnotation`, `StampAnnotation`, usw.

### Ist es möglich, markierten Text aus allen Seiten der PDF-Datei zu extrahieren?  
Auf jeden Fall! Sie können jede Seite des PDF-Dokuments durchlaufen und dieselbe Extraktionslogik anwenden, um markierten Text von jeder Seite zu erfassen.

### Benötige ich eine Lizenz, um Aspose.PDF für .NET zu verwenden?  
 Sie können zwar mit einer kostenlosen Testversion beginnen, es wird jedoch empfohlen, eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/)oder erwerben Sie eine Volllizenz für uneingeschränkten Zugriff auf alle Funktionen.

### Kann ich den extrahierten Text in einer Datei speichern, anstatt ihn auf der Konsole auszudrucken?  
Ja, Sie können den Code einfach ändern, um den extrahierten Text in einer Textdatei oder einem anderen gewünschten Format zu speichern.

### Unterstützt Aspose.PDF andere Plattformen außer .NET?  
Ja, Aspose.PDF unterstützt auch Java und andere Plattformen und bietet ähnliche Funktionen in verschiedenen Umgebungen.