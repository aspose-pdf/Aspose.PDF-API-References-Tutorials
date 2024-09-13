---
title: Inline-Strukturelemente
linktitle: Inline-Strukturelemente
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Verwendung von Online-Strukturelementen mit Aspose.PDF für .NET. Organisieren Sie Ihre PDFs mit Überschriften und Absätzen.
type: docs
weight: 110
url: /de/net/programming-with-tagged-pdf/inline-structure-elements/
---
In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie Inline-Strukturelemente mit Aspose.PDF für .NET verwenden. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert bearbeiten können. Mit Inline-Strukturelementen können Sie mithilfe von Überschriften verschiedener Ebenen und Absätze eine hierarchische Struktur in Ihrem PDF-Dokument erstellen.

Lassen Sie uns in den Code eintauchen und lernen, wie Sie Inline-Strukturelemente mit Aspose.PDF für .NET verwenden.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Aspose.PDF-Bibliothek für .NET installiert.
2. Grundkenntnisse der Programmiersprache C#.

## Schritt 1: Einrichten der Umgebung

Öffnen Sie zunächst Ihre C#-Entwicklungsumgebung und erstellen Sie ein neues Projekt. Stellen Sie sicher, dass Sie in Ihrem Projekt einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzugefügt haben.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments

 Der erste Schritt besteht in der Erstellung eines neuen PDF-Dokuments mit dem`Document` Klasse.

```csharp
// Erstellen Sie das PDF-Dokument
Document document = new Document();
```

## Schritt 3: Mit getaggten Inhalten arbeiten

Dann erhalten wir den getaggten Inhalt des Dokuments, mit dem wir arbeiten können.

```csharp
// Holen Sie sich den getaggten Inhalt des Dokuments
ITaggedContent taggedContent = document.TaggedContent;
```

## Schritt 4: Dokumenttitel und Sprache festlegen

Wir können jetzt den Dokumenttitel und die Sprache festlegen.

```csharp
// Definieren Sie den Dokumenttitel und die Sprache
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Schritt 5: Strukturelemente online hinzufügen

Nun fügen wir unserem Dokument Inline-Strukturelemente wie Überschriften verschiedener Ebenen und Absätze hinzu.

```csharp
// Holen Sie sich das Stammstrukturelement
StructureElement rootElement = taggedContent.RootElement;

// Überschriften verschiedener Ebenen hinzufügen
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Fügen Sie jeder Kopfzeile Inhalt hinzu
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// Einen Absatz hinzufügen
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Fügen Sie dem Absatz Inhalt hinzu
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

Dabei erstellen wir Inline-Strukturelemente, wie Überschriften unterschiedlicher Ebenen und einen Absatz und fügen diesen Inhalt hinzu.

## Schritt 6: Speichern Sie das getaggte PDF-Dokument

Abschließend speichern wir das getaggte PDF-Dokument.

```csharp
// Speichern des getaggten PDF-Dokuments
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Beispiel-Quellcode für Inline-Strukturelemente mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF-Dokument erstellen
Document document = new Document();

// Holen Sie sich Inhalte für die Arbeit mit TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Titel und Sprache für Dokument festlegen
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Stammstrukturelement abrufen
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// Getaggtes PDF-Dokument speichern
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie Inline-Strukturelemente mit Aspose.PDF für .NET verwenden. Sie können jetzt eine hierarchische Struktur in Ihrem PDF-Dokument erstellen, indem Sie Überschriften verschiedener Ebenen und Absätze verwenden. Entdecken Sie weitere Funktionen von Aspose.PDF, um sein volles Potenzial zu entdecken.

### Häufig gestellte Fragen

#### F: Was sind Inline-Strukturelemente in einem PDF-Dokument und wie tragen sie zur Erstellung einer hierarchischen Struktur bei?

A: Inline-Strukturelemente in einem PDF-Dokument, wie Überschriften verschiedener Ebenen und Absätze, dienen zum Erstellen einer hierarchischen Struktur, die Inhalte strukturiert organisiert und präsentiert. Mit diesen Elementen können Sie eine klare Hierarchie und einen klaren Informationsfluss innerhalb des Dokuments erstellen.

#### F: Wie können Inline-Strukturelemente die Lesbarkeit und Organisation eines PDF-Dokuments verbessern?

A: Inline-Strukturelemente, insbesondere Überschriften und Absätze, tragen zur besseren Lesbarkeit und Organisation eines PDF-Dokuments bei, indem sie eine logische Struktur bereitstellen. Überschriften zeigen unterschiedliche Wichtigkeitsstufen an und helfen den Lesern, sich im Inhalt zurechtzufinden, während Absätze verwandte Informationen zusammenfassen.

#### F: Wie erleichtert Aspose.PDF für .NET die Verwendung von Inline-Strukturelementen?

A: Aspose.PDF für .NET bietet Klassen und Methoden zum Erstellen und Bearbeiten von Inline-Strukturelementen wie Überschriften und Absätzen. Diese Elemente können angepasst, hierarchisch organisiert und mit Inhalten angereichert werden, um die visuelle Darstellung und Zugänglichkeit des Dokuments zu verbessern.

####  F: Was ist der Zweck der`taggedContent` object in relation to inline structure elements?

 A: Die`taggedContent` Objekt, erhalten aus dem`TaggedContent` Eigentum eines`Document`ermöglicht Ihnen die Arbeit mit strukturierten Elementen, einschließlich Inline-Strukturelementen. Sie können Überschriften und Absätze im Dokument erstellen, anpassen und organisieren.

#### F: Wie helfen Inline-Strukturelemente beim Erstellen einer klaren Dokumenthierarchie?

A: Inline-Strukturelemente wie Überschriften unterschiedlicher Ebenen tragen dazu bei, eine klare und wohldefinierte Hierarchie im Dokument zu schaffen. Leser können die Hauptthemen, Unterthemen und verwandten Inhalte schnell identifizieren, was die Navigation und das Verständnis des Dokuments erleichtert.

#### F: Kann ich das Erscheinungsbild und die Formatierung von Inline-Strukturelementen mit Aspose.PDF für .NET anpassen?

A: Ja, Sie können das Erscheinungsbild und die Formatierung von Inline-Strukturelementen anpassen. Sie können Eigenschaften wie Schriftarten, -größen, -farben, Ausrichtung, Einrückung und Abstände festlegen, um die gewünschte visuelle Darstellung für Überschriften und Absätze zu erreichen.

#### F: Wie erstelle und füge ich mithilfe von Inline-Strukturelementen in Aspose.PDF für .NET Überschriften verschiedener Ebenen zu einem PDF-Dokument hinzu?

 A: Sie können Überschriften auf verschiedenen Ebenen erstellen, indem Sie`CreateHeaderElement`-Methode und hängen Sie diese dann an das Stammstrukturelement an. Anschließend können Sie jedem Überschriftenelement mit der`CreateSpanElement` Methode zum Erstellen von Textabschnitten.

#### F: Kann ich Inline-Strukturelemente verwenden, um Listen, Aufzählungspunkte oder andere Arten der Inhaltsorganisation in einem PDF-Dokument zu erstellen?

A: Während Inline-Strukturelemente selbst hauptsächlich für Überschriften und Absätze verwendet werden, können Sie sie in Kombination mit anderen von Aspose.PDF für .NET angebotenen Funktionen verwenden, um Listen, Aufzählungspunkte, Tabellen und andere Arten der Inhaltsorganisation für eine umfassende Dokumentstruktur zu erstellen.

#### F: Wie tragen Inline-Strukturelemente zur Dokumentzugänglichkeit bei?

A: Inline-Strukturelemente spielen eine entscheidende Rolle bei der Verbesserung der Dokumentzugänglichkeit. Richtig strukturierte Überschriften und Absätze sorgen für eine klare Dokumenthierarchie, die Bildschirmleseprogrammen und anderen unterstützenden Technologien dabei hilft, den Inhalt richtig zu interpretieren und Benutzern mit Behinderungen zu vermitteln.

#### F: Kann ich erweiterte Verwendungsmöglichkeiten von Inline-Strukturelementen erkunden, z. B. das Erstellen interaktiver Elemente oder das Einbetten von Multimedia?

A: Absolut! Während sich dieses Tutorial auf das Erstellen von Überschriften und Absätzen konzentriert, bietet Aspose.PDF für .NET erweiterte Funktionen zum Erstellen interaktiver Elemente, zum Einbetten von Multimedia, zum Hinzufügen von Hyperlinks und mehr. Sehen Sie sich die Dokumentation und Beispiele der Bibliothek an, um mehr über diese erweiterten Funktionen zu erfahren.