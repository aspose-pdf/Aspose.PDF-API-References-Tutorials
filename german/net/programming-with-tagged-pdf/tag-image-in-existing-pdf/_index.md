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
//Definieren Sie den Titel für das getaggte PDF-Dokument
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

// Überprüfung der PDF/UA-Konformität für unser Dokument
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Bild in einer vorhandenen PDF-Datei markiert. Sie können Aspose.PDF jetzt verwenden, um Tags hinzuzufügen und Bilder in Ihren PDF-Dokumenten zu bearbeiten.
