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

//Fügen Sie einen Absatz mit einem Hyperlink hinzu, der ein Bild enthält
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

//Erstellungsdokument und Abrufen getaggter PDF-Inhalte
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