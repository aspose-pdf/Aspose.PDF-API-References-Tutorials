---
title: Strukturelemente erstellen
linktitle: Strukturelemente erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: In diesem Tutorial erfahren Sie, wie Sie mit Aspose.PDF für .NET Strukturelemente in einem getaggten PDF-Dokument erstellen.
type: docs
weight: 60
url: /de/net/programming-with-tagged-pdf/create-structure-elements/
---
Der folgende C#-Quellcode verwendet Aspose.PDF für .NET, um Strukturelemente zu erstellen. Befolgen Sie die folgenden Schritte, um zu verstehen, wie der Code funktioniert.

## Schritt 1: Importieren Sie die erforderlichen Bibliotheken

```csharp
using Aspose.Pdf;
```

## Schritt 2: Definieren Sie das Verzeichnis Ihrer Dokumente

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Achten Sie darauf, den richtigen Pfad zu Ihrem Dokumentverzeichnis anzugeben.

## Schritt 3: Erstellen Sie ein PDF-Dokument

```csharp
Document document = new Document();
```

Wir erstellen ein neues Dokumentobjekt, das das PDF-Dokument darstellt.

## Schritt 4: Inhalte mit TaggedPdf bearbeiten

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Wir rufen den getaggten Inhalt des PDF-Dokuments ab. Dadurch können wir Strukturelemente bearbeiten.

## Schritt 5: Dokumenttitel und Sprache festlegen

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Wir legen den Titel und die Sprache des getaggten PDF-Dokuments fest. Dies verbessert die Zugänglichkeit des Dokuments.

## Schritt 6: Gruppierungselemente erstellen

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

Wir erstellen verschiedene Strukturelemente zur Gruppierung von Inhalten im PDF-Dokument.

## Schritt 7: Absatzstrukturelemente erstellen

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Wir erstellen blockweise Strukturelemente für Absätze und Überschriften. Das obige Beispiel zeigt die Erstellung einer Überschrift der Ebene 1.

## Schritt 8: Inline-Level-Strukturelemente erstellen

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Wir erstellen Inline-Level-Strukturelemente für die Textteile, die innerhalb eines Absatzes oder einer Überschrift erscheinen.

## Schritt 9: Bildstrukturelemente erstellen

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Wir erstellen Strukturelemente für die im Dokument vorhandenen Abbildungen und mathematischen Formeln.

## Schritt 10: Speichern Sie das getaggte PDF-Dokument

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Wir speichern das getaggte PDF-Dokument mit den erstellten Strukturelementen.

### Beispielquellcode zum Erstellen von Strukturelementen mit Aspose.PDF für .NET 

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
// Gruppierungselemente erstellen
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// Erstellen von Strukturelementen auf Textblockebene
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Erstellen von Text-Inline-Level-Strukturelementen
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Erstellen von Illustrationsstrukturelementen
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// Methoden sind in der Entwicklung
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// Getaggtes PDF-Dokument speichern
document.Save(dataDir + "StructureElements.pdf");

```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET Strukturelemente in einem getaggten PDF-Dokument erstellt. Strukturelemente helfen, die Zugänglichkeit von Dokumenten zu verbessern und Inhalte auf sinnvolle Weise zu organisieren. Jetzt können Sie dieses Wissen nutzen, um strukturierte, leicht navigierbare PDF-Dokumente zu erstellen.

### Häufig gestellte Fragen

#### F: Was ist der Zweck der Erstellung von Strukturelementen in einem PDF-Dokument mit Aspose.PDF für .NET?

A: Das Erstellen von Strukturelementen in einem PDF-Dokument mit Aspose.PDF für .NET verbessert die Zugänglichkeit und Organisation des Dokumentinhalts. Strukturelemente bieten eine hierarchische Struktur, die die Navigation, Semantik und Kompatibilität mit unterstützenden Technologien verbessert.

#### F: Wie erstellt der bereitgestellte C#-Code Strukturelemente in einem PDF-Dokument?

A: Das Codebeispiel zeigt, wie verschiedene Arten von Strukturelementen erstellt werden, darunter Gruppierungselemente (wie Teile, Abschnitte und Divs), Elemente auf Blockebene (wie Absätze und Überschriften), Elemente auf Inline-Ebene (Span, Zitat, Notiz) und Grafikelemente (wie Abbildungen und Formeln). Diese Strukturelemente helfen beim Organisieren von Inhalten.

####  F: Warum ist es wichtig, den Titel und die Sprache des Dokuments mit dem`SetTitle` and `SetLanguage` methods?

 A: Festlegen des Titels und der Sprache des Dokuments mithilfe der`SetTitle` Und`SetLanguage`Methoden verbessern die Zugänglichkeit und Semantik des Dokuments. Der Titel bietet eine kurze Beschreibung des Zwecks des Dokuments, während das Sprachattribut die sprachspezifische Darstellung und Zugänglichkeit verbessert.

####  F: Wie können Gruppierungselemente wie`PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: Gruppierungselemente erstellen eine hierarchische Struktur innerhalb des PDF-Dokuments, sodass Sie verwandte Inhalte logisch organisieren und gruppieren können. Dies verbessert die Navigation und bietet Benutzern eine klare Struktur.

#### F: Was sind Strukturelemente auf Blockebene und Inline-Ebene und worin unterscheiden sie sich?

A: Strukturelemente auf Blockebene stellen größere Inhaltsblöcke dar, wie Absätze und Überschriften, während Elemente auf Inline-Ebene Textteile innerhalb eines Absatzes oder einer Überschrift darstellen, wie Spannen, Zitate und Notizen. Sie helfen dabei, die Hierarchie und Beziehungen des Inhalts zu definieren.

####  F: Wie strukturieren Kunstwerke Elemente, wie`FigureElement` and `FormulaElement`, contribute to the document?

A: Mithilfe von Grafikstrukturelementen können Sie dem Dokument Abbildungen, Figuren und mathematische Formeln hinzufügen. Sie bieten eine strukturierte Möglichkeit, visuelle und mathematische Inhalte einzubinden.

#### F: Kann ich ähnliche Techniken verwenden, um andere Arten von Strukturelementen wie Listen, Tabellen oder Anmerkungen zu erstellen?

A: Ja, Sie können ähnliche Techniken verwenden, um andere Arten von Strukturelementen wie Listen, Tabellen, Anmerkungen, Referenzen und mehr zu erstellen. Aspose.PDF bietet eine breite Palette von Methoden zum Erstellen von Strukturelementen.

####  F: Wie funktioniert das Speichern des getaggten PDF-Dokuments mit dem`Save` method ensure the preservation of structure elements?

 A: Die`Save` Die Methode speichert das PDF-Dokument zusammen mit den erstellten Strukturelementen und stellt sicher, dass die hierarchische und semantische Struktur des Dokuments für die Zugänglichkeit und Navigation erhalten bleibt.

#### F: Welche Vorteile bieten Strukturelemente für PDF-Dokumente im Hinblick auf Zugänglichkeit und Kompatibilität mit unterstützenden Technologien?

A: Strukturelemente verbessern die Zugänglichkeit, indem sie dem Dokument eine sinnvolle Struktur und Semantik verleihen. Dadurch können unterstützende Technologien wie Bildschirmleseprogramme den Inhalt des Dokuments besser interpretieren und Benutzern mit Behinderungen vermitteln.

#### F: Wie kann ich verschiedene Arten von Strukturelementen in meinen PDF-Dokumenten weiter anpassen und kombinieren?

A: Sie können Strukturelemente kombinieren und anpassen, indem Sie entsprechende Erstellungsmethoden von Aspose.PDF verwenden. Experimentieren Sie mit verschiedenen Elementen und ihren Eigenschaften, um ein gut strukturiertes und organisiertes PDF-Dokument zu erstellen.