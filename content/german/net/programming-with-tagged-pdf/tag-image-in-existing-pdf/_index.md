---
title: Bild in vorhandenem PDF taggen
linktitle: Bild in vorhandenem PDF taggen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Bild in einer vorhandenen PDF-Datei markieren. Eine Schritt-für-Schritt-Anleitung zum Hinzufügen von Tags zu Bildern.
type: docs
weight: 210
url: /de/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
In diesem ausführlichen Tutorial führen wir Sie Schritt für Schritt durch den bereitgestellten C#-Quellcode, um ein Bild in einer vorhandenen PDF-Datei mit Aspose.PDF für .NET zu markieren. Befolgen Sie die nachstehenden Anweisungen, um zu verstehen, wie Sie einem Bild in einer PDF-Datei Tags hinzufügen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung für die Verwendung von Aspose.PDF für .NET konfiguriert haben. Dazu gehört die Installation der Aspose.PDF-Bibliothek und die Konfiguration Ihres Projekts, um darauf zu verweisen.

## Schritt 2: Öffnen Sie das vorhandene PDF-Dokument

In diesem Schritt öffnen wir ein vorhandenes PDF-Dokument mit Aspose.PDF.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Eingabe- und Ausgabedateipfade
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Öffnen Sie das Dokument
Document document = new Document(inFile);
```

Wir haben das vorhandene PDF-Dokument mit Aspose.PDF geöffnet.

## Schritt 3: Markierten Inhalt und Stammstrukturelement abrufen

Jetzt erhalten wir den getaggten Inhalt des PDF-Dokuments und das entsprechende Stammstrukturelement.

```csharp
// Getaggten Inhalt und Stammstrukturelement abrufen
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

## Schritt 5: Dem Bild Alternativtexte und Begrenzungsrahmen zuweisen

Jetzt weisen wir jedem Bildelement einen Alternativtext und einen Begrenzungsrahmen zu.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Dem Bild Alternativtext zuweisen
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Erstellen und Zuweisen des Begrenzungsrahmens (bbox)
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
// Speichern des PDF-Dokuments
document. Save(outFile);
```

Wir haben das geänderte PDF-Dokument im angegebenen Verzeichnis gespeichert.

### Beispielquellcode zum Taggen von Bildern in vorhandenen PDFs mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Dokument öffnen
Document document = new Document(inFile);

// Ruft getaggte Inhalte und Stammstrukturelemente ab
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Titel für getaggtes PDF-Dokument festlegen
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

// Span-Element in Absatz verschieben
spanElement.ChangeParentElement(paragraph);

// Dokument speichern
document.Save(outFile);

//Überprüfung der PDF/UA-Konformität für unser Dokument
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Bild in einer vorhandenen PDF-Datei markiert. Sie können jetzt Aspose.PDF verwenden, um Tags hinzuzufügen und Bilder in Ihren PDF-Dokumenten zu bearbeiten.

### Häufig gestellte Fragen

#### F: Was ist das Hauptziel dieses Tutorials zum Taggen von Bildern in einer vorhandenen PDF-Datei mit Aspose.PDF für .NET?

A: Das Hauptziel dieses Tutorials besteht darin, Sie durch den Prozess der Markierung eines Bilds in einem vorhandenen PDF-Dokument mit Aspose.PDF für .NET zu führen. Das Tutorial enthält schrittweise Anleitungen und C#-Quellcodebeispiele, die Ihnen helfen zu verstehen, wie Sie Bildern alternativen Text und Begrenzungsrahmen zuweisen, Elemente innerhalb des Dokuments verschieben und Bildern Tags hinzufügen.

#### F: Was sind die Voraussetzungen, um diesem Tutorial zum Taggen von Bildern in einer PDF-Datei mit Aspose.PDF für .NET folgen zu können?

A: Stellen Sie vor dem Start sicher, dass Sie Ihre Entwicklungsumgebung für die Verwendung von Aspose.PDF für .NET eingerichtet haben. Dazu müssen Sie die Aspose.PDF-Bibliothek installieren und Ihr Projekt so konfigurieren, dass es darauf verweist.

#### F: Wie kann ich mit Aspose.PDF für .NET ein vorhandenes PDF-Dokument öffnen und auf dessen getaggten Inhalt zugreifen?

A: Das Tutorial bietet C#-Quellcodebeispiele, die zeigen, wie Sie mit Aspose.PDF für .NET ein vorhandenes PDF-Dokument öffnen und auf den getaggten Inhalt für weitere Bearbeitungen zugreifen.

#### F: Welchen Zweck hat die Zuweisung von Alternativtext und Begrenzungsrahmen zu Bildern in einem PDF-Dokument?

A: Durch die Zuweisung von Alternativtext und Begrenzungsrahmen zu Bildern wird die Zugänglichkeit verbessert, da beschreibender Text für Bilder bereitgestellt und deren Layout und Position im Dokument definiert wird. Diese Informationen sind für Bildschirmleseprogramme und andere unterstützende Technologien von entscheidender Bedeutung.

#### F: Wie kann ich mit Aspose.PDF für .NET den Titel für ein getaggtes PDF-Dokument festlegen?

A: Das Tutorial enthält C#-Quellcodebeispiele, die veranschaulichen, wie der Titel für ein getaggtes PDF-Dokument mit Aspose.PDF für .NET festgelegt wird.

#### F: Was beinhaltet der Vorgang des Verschiebens von Elementen innerhalb eines PDF-Dokuments?

A: Beim Verschieben von Elementen in einem PDF-Dokument wird das übergeordnete Element eines bestimmten Elements geändert. In diesem Tutorial erfahren Sie, wie Sie ein Span-Element in ein bestimmtes Paragraph-Element innerhalb einer Tabelle verschieben.

#### F: Wie speichere ich das geänderte PDF-Dokument, nachdem ich Tags hinzugefügt und Änderungen an Bildern vorgenommen habe?

 A: Nachdem Sie Tags hinzugefügt, Alternativtext zugewiesen, Begrenzungsrahmen festgelegt und Änderungen am PDF-Dokument vorgenommen haben, können Sie die bereitgestellten C#-Quellcodebeispiele verwenden, um das geänderte PDF-Dokument mit dem`Save()` Verfahren.

#### F: Was ist der Zweck des im Tutorial bereitgestellten Beispielquellcodes?

A: Der Beispielquellcode dient als praktische Referenz für die Implementierung der Bildmarkierung und -bearbeitung mit Aspose.PDF für .NET. Sie können diesen Code als Ausgangspunkt verwenden und ihn an Ihre spezifischen Anforderungen anpassen.

#### F: Kann ich diese Techniken nicht nur auf Bilder, sondern auch auf andere Elementtypen in einem PDF-Dokument anwenden?

A: Ja, die in diesem Tutorial gezeigten Techniken können angepasst werden, um mit verschiedenen Elementtypen in einem PDF-Dokument zu arbeiten. Sie können ähnliche Prinzipien anwenden, um andere Elemente wie Text, Tabellen und mehr zu kennzeichnen und zu bearbeiten.

#### F: Wie kann ich die PDF/UA-Konformität des geänderten PDF-Dokuments überprüfen?

 A: Das Tutorial enthält C#-Quellcodebeispiele, die zeigen, wie die PDF/UA-Konformität des geänderten PDF-Dokuments mithilfe des`Validate()` Methode und Generieren eines XML-Berichts.

#### F: Welche anderen Funktionen bietet Aspose.PDF für .NET für die Arbeit mit PDF-Dokumenten?

A: Aspose.PDF für .NET bietet eine breite Palette an Funktionen für die Arbeit mit PDF-Dokumenten, darunter Textbearbeitung, Bildeinfügung, Tabellenerstellung, Formularfeldverwaltung, digitale Signaturen, Anmerkungen und mehr. Weitere Informationen finden Sie in der offiziellen Dokumentation und den Ressourcen.