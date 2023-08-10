---
title: Strukturelemente erstellen
linktitle: Strukturelemente erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: In diesem Tutorial erfahren Sie, wie Sie mit Aspose.PDF für .NET Strukturelemente in einem mit Tags versehenen PDF-Dokument erstellen.
type: docs
weight: 60
url: /de/net/programming-with-tagged-pdf/create-structure-elements/
---
Der folgende C#-Quellcode verwendet Aspose.PDF für .NET, um Strukturelemente zu erstellen. Führen Sie die folgenden Schritte aus, um zu verstehen, wie der Code funktioniert.

## Schritt 1: Importieren Sie die erforderlichen Bibliotheken

```csharp
using Aspose.Pdf;
```

## Schritt 2: Definieren Sie das Verzeichnis Ihrer Dokumente

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrem Dokumentenverzeichnis angeben.

## Schritt 3: Erstellen Sie ein PDF-Dokument

```csharp
Document document = new Document();
```

Wir erstellen ein neues Document-Objekt, das das PDF-Dokument darstellt.

## Schritt 4: Machen Sie Inhalte mit TaggedPdf nutzbar

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Wir rufen den getaggten Inhalt des PDF-Dokuments ab. Dadurch können wir Strukturelemente manipulieren.

## Schritt 5: Dokumenttitel und Sprache festlegen

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Wir legen den Titel und die Sprache des getaggten PDF-Dokuments fest. Dadurch wird die Zugänglichkeit des Dokuments verbessert.

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

## Schritt 7: Erstellen Sie Absatzstrukturelemente

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Wir erstellen Strukturelemente auf Blockebene für Absätze und Überschriften. Das obige Beispiel zeigt die Erstellung eines Level-1-Headers.

## Schritt 8: Erstellen Sie Inline-Level-Strukturelemente

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Wir erstellen Strukturelemente auf Inline-Ebene für die Textteile, die innerhalb eines Absatzes oder einer Überschrift erscheinen.

## Schritt 9: Erstellen Sie Grafikstrukturelemente

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Wir erstellen Strukturelemente für die im Dokument enthaltenen Abbildungen und mathematischen Formeln.

## Schritt 10: Speichern Sie das getaggte PDF-Dokument

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Wir speichern das getaggte PDF-Dokument mit den erstellten Strukturelementen.

### Beispielquellcode zum Erstellen von Strukturelementen mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Erstellen Sie ein PDF-Dokument
Document document = new Document();
// Holen Sie sich Inhalte für die Arbeit mit TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Legen Sie Titel und Sprache für Documentt fest
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
// Erstellen Sie Strukturelemente auf Textblockebene
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Erstellen Sie Textstrukturelemente auf Inline-Ebene
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Erstellen Sie Strukturelemente für Illustrationen
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
// Markiertes PDF-Dokument speichern
document.Save(dataDir + "StructureElements.pdf");

```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET Strukturelemente in einem getaggten PDF-Dokument erstellt. Strukturelemente tragen dazu bei, die Zugänglichkeit von Dokumenten zu verbessern und Inhalte sinnvoll zu organisieren. Jetzt können Sie dieses Wissen nutzen, um strukturierte, leicht zu navigierende PDF-Dokumente zu erstellen.

### FAQs

#### F: Was ist der Zweck der Erstellung von Strukturelementen in einem PDF-Dokument mit Aspose.PDF für .NET?

A: Das Erstellen von Strukturelementen in einem PDF-Dokument mit Aspose.PDF für .NET verbessert die Zugänglichkeit und Organisation des Dokumentinhalts. Strukturelemente sorgen für eine hierarchische Struktur, die die Navigation, Semantik und Kompatibilität mit unterstützenden Technologien verbessert.

#### F: Wie erstellt der bereitgestellte C#-Code Strukturelemente in einem PDF-Dokument?

A: Das Codebeispiel zeigt, wie verschiedene Arten von Strukturelementen erstellt werden, darunter Gruppierungselemente (wie Teile, Abschnitte und Divs), Elemente auf Blockebene (wie Absätze und Überschriften) und Elemente auf Inline-Ebene (Span, Zitat, Notiz). ) und Grafikelemente (z. B. Zahlen und Formeln). Diese Strukturelemente helfen bei der Organisation von Inhalten.

####  F: Warum ist es wichtig, den Titel und die Sprache des Dokuments mithilfe von festzulegen`SetTitle` and `SetLanguage` methods?

 A: Legen Sie den Titel und die Sprache des Dokuments mit fest`SetTitle` Und`SetLanguage`Methoden verbessern die Zugänglichkeit und Semantik von Dokumenten. Der Titel bietet eine kurze Beschreibung des Zwecks des Dokuments, während das Sprachattribut die sprachspezifische Darstellung und Zugänglichkeit verbessert.

####  F: Wie funktionieren Gruppierungselemente, z`PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: Durch Gruppierungselemente wird eine hierarchische Struktur innerhalb des PDF-Dokuments erstellt, sodass Sie zusammengehörige Inhalte logisch organisieren und gruppieren können. Dies verbessert die Navigation und bietet Benutzern eine klare Struktur.

#### F: Was sind Strukturelemente auf Block- und Inline-Ebene und wie unterscheiden sie sich?

A: Strukturelemente auf Blockebene stellen größere Inhaltsblöcke dar, z. B. Absätze und Überschriften, während Elemente auf Inline-Ebene Textteile innerhalb eines Absatzes oder einer Überschrift darstellen, z. B. Abschnitte, Anführungszeichen und Notizen. Sie helfen dabei, die Hierarchie und Beziehungen von Inhalten zu definieren.

####  F: Wie strukturieren Kunstwerke Elemente?`FigureElement` and `FormulaElement`, contribute to the document?

A: Mithilfe von Strukturelementen für Grafiken können Sie dem Dokument Illustrationen, Abbildungen und mathematische Formeln hinzufügen. Sie bieten eine strukturierte Möglichkeit, visuelle und mathematische Inhalte einzubinden.

#### F: Kann ich ähnliche Techniken verwenden, um andere Arten von Strukturelementen wie Listen, Tabellen oder Anmerkungen zu erstellen?

A: Ja, Sie können ähnliche Techniken verwenden, um andere Arten von Strukturelementen wie Listen, Tabellen, Anmerkungen, Referenzen und mehr zu erstellen. Aspose.PDF bietet eine breite Palette von Methoden zur Strukturelementerstellung.

####  F: Wie funktioniert das Speichern des getaggten PDF-Dokuments mit`Save` method ensure the preservation of structure elements?

 A: Die`Save` Die Methode speichert das PDF-Dokument zusammen mit den erstellten Strukturelementen und stellt so sicher, dass die hierarchische und semantische Struktur des Dokuments für die Zugänglichkeit und Navigation erhalten bleibt.

#### F: Welche Vorteile bringen Strukturelemente für PDF-Dokumente im Hinblick auf Zugänglichkeit und Kompatibilität mit unterstützenden Technologien?

A: Strukturelemente verbessern die Zugänglichkeit, indem sie dem Dokument eine sinnvolle Struktur und Semantik verleihen. Dadurch können unterstützende Technologien wie Bildschirmlesegeräte den Inhalt des Dokuments besser interpretieren und Benutzern mit Behinderungen besser vermitteln.

#### F: Wie kann ich verschiedene Arten von Strukturelementen in meinen PDF-Dokumenten weiter anpassen und kombinieren?

A: Sie können Strukturelemente kombinieren und anpassen, indem Sie die entsprechenden Erstellungsmethoden von Aspose.PDF verwenden. Experimentieren Sie mit verschiedenen Elementen und ihren Eigenschaften, um ein gut strukturiertes und organisiertes PDF-Dokument zu erstellen.