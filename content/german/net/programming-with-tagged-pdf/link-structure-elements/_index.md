---
title: Linkstrukturelemente
linktitle: Linkstrukturelemente
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Verwendung von Linkstrukturelementen mit Aspose.PDF für .NET. Erstellen Sie Hyperlinks in Ihren PDF-Dokumenten.
type: docs
weight: 120
url: /de/net/programming-with-tagged-pdf/link-structure-elements/
---
In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie Linkstrukturelemente mit Aspose.PDF für .NET verwenden. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert erstellen und bearbeiten können. Mit Linkstrukturelementen können Sie Ihrem PDF-Dokument Hyperlinks hinzufügen, sodass Benutzer auf die Links klicken und zu Online-Ressourcen navigieren können.

Lassen Sie uns in den Code eintauchen und lernen, wie Sie Linkstrukturelemente mit Aspose.PDF für .NET verwenden.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Aspose.PDF-Bibliothek für .NET installiert.
2. Grundkenntnisse der Programmiersprache C#.

## Schritt 1: Einrichten der Umgebung

Öffnen Sie zunächst Ihre C#-Entwicklungsumgebung und erstellen Sie ein neues Projekt. Stellen Sie sicher, dass Sie in Ihrem Projekt einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzugefügt haben.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
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
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Schritt 5: Linkstruktur-Elemente hinzufügen

Fügen wir nun unserem Dokument Linkstrukturelemente hinzu. Wir erstellen verschiedene Arten von Links, darunter einfache Textlinks, Bildlinks und mehrzeilige Links.
```csharp
// Holen Sie sich das Stammstrukturelement (Dokumentstrukturelement).
StructureElement rootElement = taggedContent.RootElement;

// Hinzufügen eines Absatzes mit einem Hyperlink
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Fügen Sie einen Absatz mit einem Hyperlink hinzu, der Rich Text enthält
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Fügen Sie einen Absatz mit einem Hyperlink hinzu, der teilweise formatierten Text enthält
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// Hinzufügen eines Absatzes mit einem mehrzeiligen Hyperlink
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Fügen Sie einen Absatz mit einem Hyperlink hinzu, der ein Bild enthält
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## Schritt 6: Speichern Sie das getaggte PDF-Dokument

Abschließend speichern wir das getaggte PDF-Dokument.

```csharp
// Speichern des getaggten PDF-Dokuments
document. Save(outFile);
```

## Schritt 7: PDF/UA-Konformität prüfen

 Wir können das Dokument auch auf PDF/UA-Konformität prüfen, indem wir`Validate` Methode der`Document` Klasse.

```csharp
// Überprüfen Sie die PDF/UA-Konformität
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Beispiel-Quellcode für Link-Strukturelemente mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Dokument erstellen und getaggten PDF-Inhalt erhalten
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Festlegen von Titel und Artsprache für das Dokument
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Abrufen des Stammstrukturelements (Dokumentstrukturelement)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// Getaggtes PDF-Dokument speichern
document.Save(outFile);

// Überprüfung der PDF/UA-Konformität
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie Linkstrukturelemente mit Aspose.PDF für .NET verwenden. Jetzt können Sie Hyperlinks in Ihren PDF-Dokumenten erstellen, mit denen Benutzer zu Online-Ressourcen navigieren können. Experimentieren Sie und erkunden Sie weitere Funktionen von Aspose.PDF, um interaktive und angereicherte PDF-Dokumente zu erstellen.

### Häufig gestellte Fragen

#### F: Was sind Linkstrukturelemente in einem PDF-Dokument und wie verbessern sie die Dokumentinteraktivität?

A: Linkstrukturelemente in einem PDF-Dokument werden verwendet, um Hyperlinks zu erstellen, mit denen Benutzer zu Online-Ressourcen oder bestimmten Stellen im Dokument navigieren können. Diese Elemente verbessern die Interaktivität, indem sie anklickbare Links bereitstellen, über die Benutzer auf verwandte Inhalte oder externe Websites zugreifen können.

#### F: Welchen Nutzen können Linkstrukturelemente in einem PDF-Dokument haben?

A: Linkstrukturelemente verbessern das Benutzererlebnis, indem sie das PDF-Dokument interaktiv machen. Sie bieten schnellen Zugriff auf zusätzliche Informationen, verwandte Inhalte, externe Websites oder bestimmte Abschnitte im Dokument, verbessern die Navigation und erleichtern den Informationsabruf.

#### F: Kann ich mit Linkstrukturelementen in Aspose.PDF für .NET verschiedene Arten von Hyperlinks erstellen?

A: Ja, Sie können mithilfe von Linkstrukturelementen verschiedene Arten von Hyperlinks erstellen. Mit Aspose.PDF für .NET können Sie Hyperlinks mit einfachem Text, Rich Text, Bildern und mehrzeiligen Beschreibungen erstellen und haben so vielfältige Möglichkeiten, auf externe Inhalte oder Stellen innerhalb des Dokuments zu verlinken.

#### F: Wie richte ich mit Aspose.PDF für .NET Linkstrukturelemente in einem PDF-Dokument ein und initialisiere sie?

 A: Um Linkstrukturelemente verwenden zu können, müssen Sie zunächst ein neues PDF-Dokument erstellen. Verwenden Sie dazu`Document` Klasse. Dann erhalten Sie den getaggten Inhalt mit dem`TaggedContent`Eigenschaft des Dokuments. Von dort aus können Sie Linkstrukturelemente erstellen, anpassen und sie dem Stammstrukturelement hinzufügen.

#### F: Wie kann ich mithilfe von Linkstrukturelementen einen einfachen Text-Hyperlink erstellen?
 A: Sie können einen einfachen Text-Hyperlink erstellen, indem Sie`LinkElement` und die Einstellung`Hyperlink` Eigentum an einem`WebHyperlink` mit der URL, auf die Sie verlinken möchten. Sie können den Anzeigetext des Links auch über die`SetText` Verfahren.

#### F: Ist es möglich, mithilfe von Linkstrukturelementen Hyperlinks mit Bildern zu erstellen?

 A: Ja, Sie können Hyperlinks mit Bildern erstellen, indem Sie Linkstrukturelemente verwenden. Sie erstellen ein`LinkElement` und fügen Sie dann ein`FigureElement` mit einem Bild. So können Sie einen bildbasierten Hyperlink erstellen.

#### F: Wie kann ich sicherstellen, dass mein PDF-Dokument mit Hyperlinks dem PDF/UA-Standard für Barrierefreiheit entspricht?

 A: Aspose.PDF für .NET bietet die Möglichkeit, die Konformität Ihres PDF-Dokuments mit dem PDF/UA-Standard mithilfe des`Validate` Methode der`Document`Klasse. Dadurch wird sichergestellt, dass die Hyperlinks des Dokuments für Benutzer mit Behinderungen zugänglich sind.

#### F: Was sind alternative Beschreibungen für Linkstrukturelemente und warum sind sie wichtig?

A: Alternative Beschreibungen (Alt-Text) für Linkstrukturelemente bieten Textbeschreibungen der Hyperlinks. Diese Beschreibungen sind für die Zugänglichkeit unerlässlich, da sie es sehbehinderten Benutzern ermöglichen, den Zweck und das Ziel des Links zu verstehen.

#### F: Kann ich das Erscheinungsbild und Verhalten von Hyperlinks anpassen, die mit Linkstrukturelementen erstellt wurden?

A: Während sich Linkstrukturelemente in erster Linie auf das Erstellen von Hyperlinks konzentrieren, können Sie das Erscheinungsbild und Verhalten von Hyperlinks mithilfe anderer von Aspose.PDF für .NET angebotener Funktionen weiter anpassen. Dazu gehört das Festlegen von Farben, Stilen und Linkaktionen.

#### F: Wie tragen Linkstrukturelemente dazu bei, PDF-Dokumente interaktiver und benutzerfreundlicher zu gestalten?

A: Linkstrukturelemente verwandeln statische PDF-Dokumente durch das Hinzufügen anklickbarer Hyperlinks in interaktive Erlebnisse. Diese Interaktivität verbessert die Benutzereinbindung, ermöglicht eine nahtlose Navigation zwischen verwandten Inhalten und verbessert die allgemeine Benutzerfreundlichkeit des Dokuments.