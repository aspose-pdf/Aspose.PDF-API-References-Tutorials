---
title: Linkstrukturelemente
linktitle: Linkstrukturelemente
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Linkstrukturelemente in einer PDF-Datei erstellen. Schritt-für-Schritt-Anleitung zum Hinzufügen zugänglicher Links, Bilder und Konformitätsvalidierung.
type: docs
weight: 120
url: /de/net/programming-with-tagged-pdf/link-structure-elements/
---
## Einführung

Das Erstellen und Verwalten von Linkstrukturelementen in einer PDF-Datei kann für Dokumente, die Zugänglichkeit und reibungslose Navigation erfordern, von entscheidender Bedeutung sein. In diesem Tutorial zeigen wir Ihnen, wie Sie dies mit Aspose.PDF für .NET tun. Wenn Sie mit Aspose.PDF oder der PDF-Bearbeitung im Allgemeinen noch nicht vertraut sind, machen Sie sich keine Sorgen. Ich erkläre jeden Schritt im Detail, damit Sie ihn problemlos nachvollziehen können!

## Voraussetzungen  

Bevor wir uns in die Programmierung stürzen, sollten wir zunächst ein paar Dinge klären. Dies sind die Grundvoraussetzungen für eine reibungslose Entwicklung.

1.  Aspose.PDF für .NET: Sie können die neueste Version herunterladen[Hier](https://releases.aspose.com/pdf/net/).
2. .NET-Entwicklungsumgebung: Egal, ob Visual Studio oder eine andere .NET-kompatible IDE, halten Sie es installiert und bereit.
3.  Aspose-Lizenz: Sie können die kostenlose Testversion von Aspose.PDF verwenden[Hier](https://releases.aspose.com/) oder erwerben Sie eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/).
4. Grundkenntnisse in C#: Wir werden mit einigem C#-Code arbeiten, daher wird das Verständnis der Grundlagen die Dinge wesentlich erleichtern.

## Pakete importieren

Sie müssen einige Pakete importieren, bevor Sie den Code für die Linkstrukturelemente schreiben. Beginnen Sie mit der Referenzierung der erforderlichen Aspose.PDF-Bibliotheken in Ihrem Projekt:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Diese Importe ermöglichen es uns, mit PDF-Dokumenten zu arbeiten, Tags hinzuzufügen und Strukturelemente zu verwalten.

Wir erstellen jetzt ein PDF-Dokument mit verschiedenen Arten von Linkstrukturen und erklären jeden Schritt im Detail, damit Sie den Vorgang gründlich verstehen.

## Schritt 1: Initialisieren Sie das Dokument  

Beginnen wir mit der Erstellung eines neuen PDF-Dokuments und dem Einrichten getaggter Inhalte für die Barrierefreiheit.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Neues PDF-Dokument erstellen
Document document = new Document(); 

// Abrufen der TaggedContent-Schnittstelle
ITaggedContent taggedContent = document.TaggedContent;
```
  
 Hier initialisieren wir die`Document` -Objekt, das unsere PDF-Datei darstellt. Wir holen auch die`TaggedContent` Schnittstelle, die es uns ermöglicht, Strukturelemente wie Absätze, Links und Bilder hinzuzufügen.

## Schritt 2: Titel und Sprache festlegen  

Jedes PDF sollte einen Titel und eine Spracheinstellung haben, insbesondere wenn Sie die Einhaltung der PDF/UA-Standards anstreben.

```csharp
// Legen Sie den Dokumenttitel und die Sprache fest
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
Dieser Schritt stellt sicher, dass Ihr PDF einen aussagekräftigen Titel hat und stellt die Sprache auf Englisch ein (`en-US`). Dies ist für die Zugänglichkeit von entscheidender Bedeutung und stellt sicher, dass Bildschirmleseprogramme oder andere unterstützende Technologien Ihr Dokument richtig interpretieren können.

## Schritt 3: Absätze erstellen und anhängen  

In diesem Schritt fügen wir Absätze hinzu, die unsere Linkelemente enthalten.

```csharp
// Erstellen des Stammelements
StructureElement rootElement = taggedContent.RootElement;

// Erstellen Sie einen Absatz und fügen Sie ihn dem Stammelement hinzu
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
Wir erstellen ein Stammstrukturelement, das im Wesentlichen der Container der obersten Ebene für alle anderen Elemente ist. Anschließend erstellen wir einen Absatz (`p1`) und hängen Sie es an das Stammelement an.

## Schritt 4: Einen einfachen Link hinzufügen  

Fügen wir nun einen einfachen Hyperlink hinzu, der auf Google verweist.

```csharp
// Erstellen Sie ein Link-Element und fügen Sie es dem Absatz hinzu
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

// Hyperlink und Text für den Link festlegen
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
In diesem Schritt haben wir ein Link-Element erstellt, seinen Hyperlink auf „http://google.com“ gesetzt und Text („Google“) für den Link bereitgestellt. Wir haben auch eine alternative Beschreibung hinzugefügt, um die Zugänglichkeit sicherzustellen.

## Schritt 5: Hinzufügen eines Links mit Spans  

Wir können auch Links mit unterschiedlichen Textabschnitten erstellen.

```csharp
// Einen weiteren Absatz erstellen
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

// Erstellen eines Links mit einem Span-Element
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
Hier haben wir ein Span-Element verwendet, um einen Teil des Textes in den Link einzuschließen. Dadurch konnten wir anpassen, wie bestimmte Teile des Links angezeigt werden.

## Schritt 6: Mehrzeiliger Link  

Was ist, wenn Ihr Linktext zu lang ist? Keine Sorge, Sie können ihn auf mehrere Zeilen aufteilen.

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
In diesem Fall haben wir einen mehrzeiligen Link erstellt, indem wir einfach einen langen Textwert festgelegt haben. Der Text wird dann automatisch über mehrere Zeilen umbrochen.

## Schritt 7: Fügen Sie dem Link ein Bild hinzu  

Schließlich können Sie einem Link auch Bilder hinzufügen.

```csharp
// Einen neuen Absatz und ein neues Link-Element erstellen
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");

// Fügen Sie dem Link ein Bild hinzu
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
Dieser Schritt zeigt, wie Sie Ihre Links mit einem Bild verbessern können. In diesem Fall haben wir dem Link ein Google-Symbol hinzugefügt. Wir haben auch die Zugänglichkeit sichergestellt, indem wir einen alternativen Text für das Bild festgelegt haben.

## Schritt 8: PDF auf Konformität prüfen  

Wenn Sie die Konformität mit PDF/UA (einem Zugänglichkeitsstandard) anstreben, empfiehlt es sich, Ihr Dokument zu validieren.

```csharp
// Speichern des PDF-Dokuments
document.Save(outFile);

// Validieren Sie das Dokument auf PDF/UA-Konformität.
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
Wir haben das Dokument gespeichert und anhand des PDF/UA-Standards validiert. Dadurch wird sichergestellt, dass das PDF die Barrierefreiheitsanforderungen erfüllt.

## Abschluss  

In diesem Tutorial haben wir erläutert, wie Sie mit Aspose.PDF für .NET strukturierte PDF-Dokumente erstellen. Vom Hinzufügen einfacher Hyperlinks bis hin zu komplexeren Strukturen wie Spannen, mehrzeiligen Links und sogar Bildern bietet dieser Leitfaden eine solide Grundlage für die Bearbeitung von Linkelementen in Ihren PDFs. Mit dem zusätzlichen Vorteil der PDF/UA-Konformität sind Sie nun in der Lage, zugängliche und navigierbare PDFs zu erstellen.

## Häufig gestellte Fragen

### Kann ich komplexere Strukturen wie Tabellen in Links einfügen?  
Nein, Links dienen in erster Linie Text und Bildern, Sie können aber auch komplexe Elemente in der Nähe einbetten.

### Ist die PDF/UA-Validierung obligatorisch?  
Nicht immer, aber es wird dringend empfohlen, wenn Ihnen die Zugänglichkeit wichtig ist.

### Was passiert, wenn der Bilddateipfad falsch ist?  
Das Bild wird im Dokument nicht angezeigt und beim Rendern kann ein Fehler auftreten.

### Kann ich den Text im Link formatieren?  
Ja, Sie können mit den Span-Elementen Textstile anwenden.

### Ist es möglich, interne Dokumentlinks zu erstellen?  
Auf jeden Fall! Sie können auf bestimmte Abschnitte innerhalb desselben Dokuments verlinken.