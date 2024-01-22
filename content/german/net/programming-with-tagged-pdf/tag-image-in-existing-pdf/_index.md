---
title: Markieren Sie das Bild in einem vorhandenen PDF
linktitle: Markieren Sie das Bild in einem vorhandenen PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Bild in einem vorhandenen PDF markieren. Eine Schritt-für-Schritt-Anleitung zum Hinzufügen von Tags zu Bildern.
type: docs
weight: 210
url: /de/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
In diesem ausführlichen Tutorial führen wir Sie Schritt für Schritt durch den bereitgestellten C#-Quellcode, um mit Aspose.PDF für .NET ein Bild in einer vorhandenen PDF-Datei zu markieren. Befolgen Sie die nachstehenden Anweisungen, um zu verstehen, wie Sie Tags zu einem Bild in einer PDF-Datei hinzufügen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung für die Verwendung von Aspose.PDF für .NET konfiguriert haben. Dazu gehört die Installation der Aspose.PDF-Bibliothek und die Konfiguration Ihres Projekts, um darauf zu verweisen.

## Schritt 2: Öffnen Sie das vorhandene PDF-Dokument

In diesem Schritt öffnen wir ein vorhandenes PDF-Dokument mit Aspose.PDF.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Eingabe- und Ausgabedateipfade
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Öffnen Sie das Dokument
Document document = new Document(inFile);
```

Wir haben das vorhandene PDF-Dokument mit Aspose.PDF geöffnet.

## Schritt 3: Erhalten Sie getaggte Inhalte und Stammstrukturelemente

Jetzt erhalten wir den getaggten Inhalt des PDF-Dokuments und das entsprechende Stammstrukturelement.

```csharp
// Holen Sie sich getaggte Inhalte und Stammstrukturelemente
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Wir haben den getaggten Inhalt des PDF-Dokuments und das entsprechende Stammstrukturelement erhalten.

## Schritt 4: Festlegen des Titels für das getaggte PDF-Dokument

Legen wir nun den Titel für das getaggte PDF-Dokument fest.

```csharp
// Definieren Sie den Titel für das getaggte PDF-Dokument
taggedContent.SetTitle("Document with images");
```

Wir haben den Titel für das getaggte PDF-Dokument festgelegt.

## Schritt 5: Weisen Sie dem Bild Alternativtexte und einen Begrenzungsrahmen zu

Nun weisen wir jedem Bildelement Alternativtext und einen Begrenzungsrahmen zu.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Weisen Sie dem Bild Alternativtext zu
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Erstellen Sie den Begrenzungsrahmen (bbox) und weisen Sie ihn zu.
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

Wir haben jedem Bildelement im PDF-Dokument Alternativtext und einen Begrenzungsrahmen zugewiesen.

## Schritt 6: Verschieben des Span-Elements in den Absatz

Verschieben wir nun das Span-Element in den Absatz.

```csharp
// Span-Element in Absatz verschieben (falschen Span und Absatz im ersten TD finden)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Verschieben Sie das Span-Element im Absatz
spanElement.ChangeParentElement(paragraph);
```

Wir haben das Span-Element in den angegebenen Absatz verschoben.

## Schritt 7: Speichern des geänderten PDF-Dokuments

Nachdem wir nun die notwendigen Änderungen vorgenommen haben, speichern wir das geänderte PDF-Dokument.

```csharp
// Speichern Sie das PDF-Dokument
document. Save(outFile);
```

Wir haben das geänderte PDF-Dokument im angegebenen Verzeichnis gespeichert.

### Beispielquellcode für das Markieren von Bildern in vorhandenen PDFs mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Dokument öffnen
Document document = new Document(inFile);

// Ruft getaggte Inhalte und Stammstrukturelemente ab
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Legen Sie den Titel für das getaggte PDF-Dokument fest
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Alternativtext für Abbildung festlegen
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// BBox-Attribut erstellen und festlegen
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Span-Element in Absatz verschieben (falschen Span und Absatz im ersten TD finden)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Verschieben Sie das Span-Element in den Absatz
spanElement.ChangeParentElement(paragraph);

// Dokument speichern
document.Save(outFile);

//Überprüfung der PDF/UA-Konformität für unser Dokument
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Bild in einer vorhandenen PDF-Datei markiert. Sie können Aspose.PDF jetzt verwenden, um Tags hinzuzufügen und Bilder in Ihren PDF-Dokumenten zu bearbeiten.

### FAQs

#### F: Was ist das Hauptziel dieses Tutorials zum Markieren von Bildern in einem vorhandenen PDF mit Aspose.PDF für .NET?

A: Das Hauptziel dieses Tutorials besteht darin, Sie durch den Prozess der Markierung eines Bildes in einem vorhandenen PDF-Dokument mit Aspose.PDF für .NET zu führen. Das Tutorial bietet Schritt-für-Schritt-Anleitungen und C#-Quellcode-Beispiele, die Ihnen helfen zu verstehen, wie Sie Bildern alternativen Text und Begrenzungsrahmen zuweisen, Elemente innerhalb des Dokuments verschieben und Tags zu Bildern hinzufügen.

#### F: Was sind die Voraussetzungen, um diesem Tutorial zum Taggen von Bildern in einer PDF-Datei mit Aspose.PDF für .NET zu folgen?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung für die Verwendung von Aspose.PDF für .NET eingerichtet haben. Dazu müssen Sie die Aspose.PDF-Bibliothek installieren und Ihr Projekt so konfigurieren, dass es darauf verweist.

#### F: Wie kann ich mit Aspose.PDF für .NET ein vorhandenes PDF-Dokument öffnen und auf seinen getaggten Inhalt zugreifen?

A: Das Tutorial stellt C#-Quellcodebeispiele bereit, die zeigen, wie man ein vorhandenes PDF-Dokument mit Aspose.PDF für .NET öffnet und auf seinen getaggten Inhalt zur weiteren Bearbeitung zugreift.

#### F: Welchen Zweck hat die Zuweisung von Alternativtext und Begrenzungsrahmen zu Bildern in einem PDF-Dokument?

A: Das Zuweisen alternativer Texte und Begrenzungsrahmen zu Bildern verbessert die Barrierefreiheit, indem beschreibender Text für Bilder bereitgestellt und deren Layout und Position innerhalb des Dokuments definiert wird. Diese Informationen sind für Screenreader und andere unterstützende Technologien von entscheidender Bedeutung.

#### F: Wie kann ich mit Aspose.PDF für .NET den Titel für ein getaggtes PDF-Dokument festlegen?

A: Das Tutorial enthält C#-Quellcodebeispiele, die veranschaulichen, wie der Titel für ein getaggtes PDF-Dokument mit Aspose.PDF für .NET festgelegt wird.

#### F: Was beinhaltet der Prozess des Verschiebens von Elementen innerhalb eines PDF-Dokuments?

A: Das Verschieben von Elementen innerhalb eines PDF-Dokuments erfordert die Änderung des übergeordneten Elements eines bestimmten Elements. In diesem Tutorial erfahren Sie, wie Sie ein Span-Element in ein bestimmtes Paragraph-Element innerhalb einer Tabelle verschieben.

#### F: Wie speichere ich das geänderte PDF-Dokument, nachdem ich Tags hinzugefügt und Bilder bearbeitet habe?

 A: Nachdem Sie Tags hinzugefügt, alternativen Text zugewiesen, Begrenzungsrahmen festgelegt und Änderungen am PDF-Dokument vorgenommen haben, können Sie die bereitgestellten C#-Quellcodebeispiele verwenden, um das geänderte PDF-Dokument mit zu speichern`Save()` Methode.

#### F: Wozu dient der im Tutorial bereitgestellte Beispielquellcode?

A: Der Beispielquellcode dient als praktische Referenz für die Implementierung von Bildkennzeichnung und -bearbeitung mit Aspose.PDF für .NET. Sie können diesen Code als Ausgangspunkt verwenden und ihn an Ihre spezifischen Anforderungen anpassen.

#### F: Kann ich diese Techniken auf andere Arten von Elementen in einem PDF-Dokument anwenden, nicht nur auf Bilder?

A: Ja, die in diesem Tutorial gezeigten Techniken können angepasst werden, um mit verschiedenen Arten von Elementen in einem PDF-Dokument zu arbeiten. Sie können ähnliche Prinzipien anwenden, um andere Elemente wie Text, Tabellen usw. zu kennzeichnen und zu bearbeiten.

#### F: Wie kann ich die PDF/UA-Konformität des geänderten PDF-Dokuments überprüfen?

 A: Das Tutorial stellt C#-Quellcodebeispiele bereit, die zeigen, wie die PDF/UA-Konformität des geänderten PDF-Dokuments mithilfe von validiert wird`Validate()` Methode und Generieren eines XML-Berichts.

#### F: Welche weiteren Funktionen bietet Aspose.PDF für .NET für die Arbeit mit PDF-Dokumenten?

A: Aspose.PDF für .NET bietet eine breite Palette von Funktionen für die Arbeit mit PDF-Dokumenten, darunter Textbearbeitung, Bildeinfügung, Tabellenerstellung, Formularfeldverwaltung, digitale Signaturen, Anmerkungen und mehr. Weitere Informationen finden Sie in der offiziellen Dokumentation und den Ressourcen.