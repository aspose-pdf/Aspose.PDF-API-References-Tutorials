---
title: Strukturelemente verknüpfen
linktitle: Strukturelemente verknüpfen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Verwendung von Linkstrukturelementen mit Aspose.PDF für .NET. Erstellen Sie Hyperlinks in Ihren PDF-Dokumenten.
type: docs
weight: 120
url: /de/net/programming-with-tagged-pdf/link-structure-elements/
---
In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie Linkstrukturelemente mit Aspose.PDF für .NET verwenden. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert erstellen und bearbeiten können. Mithilfe von Linkstrukturelementen können Sie Hyperlinks zu Ihrem PDF-Dokument hinzufügen, sodass Benutzer auf die Links klicken und zu Online-Ressourcen navigieren können.

Lassen Sie uns in den Code eintauchen und lernen, wie Sie Linkstrukturelemente mit Aspose.PDF für .NET verwenden.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Aspose.PDF-Bibliothek für .NET installiert.
2. Grundkenntnisse der Programmiersprache C#.

## Schritt 1: Einrichten der Umgebung

Öffnen Sie zunächst Ihre C#-Entwicklungsumgebung und erstellen Sie ein neues Projekt. Stellen Sie sicher, dass Sie in Ihrem Projekt einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzugefügt haben.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## Schritt 2: Erstellen des Dokuments

 Der erste Schritt besteht darin, ein neues PDF-Dokument mit zu erstellen`Document` Klasse.

```csharp
// Erstellen Sie das PDF-Dokument
Document document = new Document();
```

## Schritt 3: Arbeiten Sie mit getaggten Inhalten

Dann erhalten wir den getaggten Inhalt des Dokuments, mit dem wir arbeiten können.

```csharp
// Rufen Sie den getaggten Inhalt des Dokuments ab
ITaggedContent taggedContent = document.TaggedContent;
```

## Schritt 4: Dokumenttitel und Sprache festlegen

Wir können nun den Titel und die Sprache des Dokuments festlegen.

```csharp
// Definieren Sie den Titel und die Sprache des Dokuments
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Schritt 5: Linkstrukturelemente hinzufügen

Fügen wir nun Linkstrukturelemente zu unserem Dokument hinzu. Wir erstellen verschiedene Arten von Links, darunter einfache Textlinks, Bildlinks und mehrzeilige Links.
```csharp
// Holen Sie sich das Stammstrukturelement (Dokumentstrukturelement)
StructureElement rootElement = taggedContent.RootElement;

// Fügen Sie einen Absatz mit einem Hyperlink hinzu
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

// Fügen Sie einen Absatz mit einem mehrzeiligen Hyperlink hinzu
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
// Speichern Sie das getaggte PDF-Dokument
document. Save(outFile);
```

## Schritt 7: Überprüfen Sie die PDF/UA-Konformität

 Wir können das Dokument auch mit dem auf PDF/UA-Konformität überprüfen`Validate` Methode der`Document` Klasse.

```csharp
// Überprüfen Sie die PDF/UA-Konformität
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Beispielquellcode für Link-Strukturelemente mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Erstellungsdokument und Abrufen getaggter PDF-Inhalte
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Festlegen der Titel- und Natursprache für das Dokument
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Root-Strukturelement (Dokumentstrukturelement) abrufen
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

// Markiertes PDF-Dokument speichern
document.Save(outFile);

// Überprüfung der PDF/UA-Konformität
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie Linkstrukturelemente mit Aspose.PDF für .NET verwenden. Jetzt können Sie Hyperlinks in Ihren PDF-Dokumenten erstellen, sodass Benutzer zu Online-Ressourcen navigieren können. Experimentieren Sie und erkunden Sie weitere Funktionen von Aspose.PDF, um interaktive und angereicherte PDF-Dokumente zu erstellen.

### FAQs

#### F: Was sind Linkstrukturelemente in einem PDF-Dokument und wie verbessern sie die Dokumentinteraktivität?

A: Linkstrukturelemente in einem PDF-Dokument werden verwendet, um Hyperlinks zu erstellen, die es Benutzern ermöglichen, zu Online-Ressourcen oder bestimmten Stellen innerhalb des Dokuments zu navigieren. Diese Elemente verbessern die Interaktivität, indem sie anklickbare Links bereitstellen, die es Benutzern ermöglichen, auf verwandte Inhalte oder externe Websites zuzugreifen.

#### F: Wie können Linkstrukturelemente in einem PDF-Dokument von Vorteil sein?

A: Linkstrukturelemente verbessern das Benutzererlebnis, indem sie das PDF-Dokument interaktiv machen. Sie bieten schnellen Zugriff auf zusätzliche Informationen, verwandte Inhalte, externe Websites oder bestimmte Abschnitte innerhalb des Dokuments, verbessern die Navigation und erleichtern das Abrufen von Informationen.

#### F: Kann ich mithilfe von Linkstrukturelementen in Aspose.PDF für .NET verschiedene Arten von Hyperlinks erstellen?

A: Ja, Sie können mithilfe von Linkstrukturelementen verschiedene Arten von Hyperlinks erstellen. Mit Aspose.PDF für .NET können Sie Hyperlinks mit einfachem Text, Rich Text, Bildern und mehrzeiligen Beschreibungen erstellen und bieten so Vielseitigkeit bei der Verknüpfung mit externen Inhalten oder Stellen innerhalb des Dokuments.

#### F: Wie richte ich Linkstrukturelemente in einem PDF-Dokument mit Aspose.PDF für .NET ein und initialisiere sie?

 A: Um Linkstrukturelemente verwenden zu können, müssen Sie zunächst ein neues PDF-Dokument mit erstellen`Document` Klasse. Rufen Sie dann den getaggten Inhalt mithilfe von ab`TaggedContent`Eigentum des Dokuments. Von dort aus können Sie Link-Strukturelemente erstellen und anpassen und sie dem Root-Strukturelement hinzufügen.

#### F: Wie kann ich mithilfe von Linkstrukturelementen einen einfachen Text-Hyperlink erstellen?
 A: Sie können einen einfachen Text-Hyperlink erstellen, indem Sie einen erstellen`LinkElement` und dessen Einstellung`Hyperlink` Eigentum an a`WebHyperlink` mit der URL, auf die Sie verlinken möchten. Sie können den Anzeigetext des Links auch über festlegen`SetText` Methode.

#### F: Ist es möglich, Hyperlinks mit Bildern mithilfe von Linkstrukturelementen zu erstellen?

 A: Ja, Sie können mithilfe von Linkstrukturelementen Hyperlinks mit Bildern erstellen. Sie würden eine erstellen`LinkElement` und dann a anhängen`FigureElement` mit einem Bild dazu. Dadurch können Sie einen bildbasierten Hyperlink erstellen.

#### F: Wie kann ich sicherstellen, dass mein PDF-Dokument mit Hyperlinks dem PDF/UA-Standard für Barrierefreiheit entspricht?

 A: Aspose.PDF für .NET bietet die Möglichkeit, die Konformität Ihres PDF-Dokuments mit dem PDF/UA-Standard mithilfe von zu überprüfen`Validate` Methode der`Document`Klasse. Dadurch wird sichergestellt, dass die Hyperlinks des Dokuments für Benutzer mit Behinderungen zugänglich sind.

#### F: Was sind alternative Beschreibungen für Linkstrukturelemente und warum sind sie wichtig?

A: Alternative Beschreibungen (Alt-Text) für Linkstrukturelemente bieten textliche Beschreibungen der Hyperlinks. Diese Beschreibungen sind für die Barrierefreiheit unerlässlich und ermöglichen Benutzern mit Sehbehinderungen, den Zweck des Links und sein Ziel zu verstehen.

#### F: Kann ich das Erscheinungsbild und Verhalten von Hyperlinks anpassen, die mithilfe von Linkstrukturelementen erstellt wurden?

A: Während sich Linkstrukturelemente in erster Linie auf die Erstellung von Hyperlinks konzentrieren, können Sie das Erscheinungsbild und Verhalten von Hyperlinks mithilfe anderer von Aspose.PDF für .NET angebotener Funktionen weiter anpassen. Dazu gehört die Angabe von Farben, Stilen und Linkaktionen.

#### F: Wie tragen Linkstrukturelemente dazu bei, PDF-Dokumente interaktiver und benutzerfreundlicher zu machen?

A: Linkstrukturelemente verwandeln statische PDF-Dokumente in interaktive Erlebnisse, indem sie anklickbare Hyperlinks hinzufügen. Diese Interaktivität verbessert die Benutzereinbindung, ermöglicht eine nahtlose Navigation zwischen verwandten Inhalten und verbessert die allgemeine Benutzerfreundlichkeit des Dokuments.