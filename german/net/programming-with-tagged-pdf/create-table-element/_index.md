---
title: Tabellenelement erstellen
linktitle: Tabellenelement erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Erstellen eines Array-Elements mit Aspose.PDF für .NET. Erstellen Sie ganz einfach dynamische PDFs mit Tabellen.
type: docs
weight: 80
url: /de/net/programming-with-tagged-pdf/create-table-element/
---
In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess der Erstellung eines Array-Elements mit Aspose.PDF für .NET. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert bearbeiten können. Das Erstellen eines Array-Elements ist eine häufige Anforderung beim Generieren dynamischer PDFs, und Aspose.PDF bietet eine einfache und effiziente Möglichkeit, dies zu erreichen.

Lassen Sie uns in den Code eintauchen und lernen, wie Sie mit Aspose.PDF für .NET ein Array-Element erstellen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Aspose.PDF-Bibliothek für .NET installiert.
2. Grundkenntnisse der Programmiersprache C#.

## Schritt 1: Einrichten der Umgebung

Öffnen Sie zunächst Ihre C#-Entwicklungsumgebung und erstellen Sie ein neues Projekt. Stellen Sie sicher, dass Sie in Ihrem Projekt einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzugefügt haben.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments

 Der erste Schritt besteht darin, ein neues PDF-Dokument mit zu erstellen`Document` Klasse.

```csharp
// Erstellen Sie das Dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Hier legen wir auch den Titel und die Sprache für den getaggten Inhalt fest.

## Schritt 3: Erstellen des Array-Elements

Als nächstes müssen wir das Array-Element erstellen und es dem Dokument hinzufügen. Wir beginnen mit dem Abrufen des Stammstrukturelements und erstellen dann mithilfe von ein neues Tabellenelement`CreateTableElement` Methode.

```csharp
// Holen Sie sich das Stammstrukturelement
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
TableTRElement trElement = tableTBodyElement.CreateTR();
trElement.AlternativeText = String.Format("Row {0}", rowIndex);
for (colIndex = 0; colIndex < colCount; colIndex++)
{
int colSpan = 1;
int rowSpan = 1;
if (colIndex == 1 && rowIndex == 1)
{
colSpan = 2;
rowSpan = 2;
}
else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
{
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
tdElement.BackgroundColor = Color.Yellow;
tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
tdElement.IsNoBorder = false;
tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
tdElement.Alignment = HorizontalAlignment.Center;
TextState cellTextState = new TextState();
cellTextState.ForegroundColor = Color.DarkBlue;
cellTextState.FontSize = 7.5F;
cellTextState.FontStyle = FontStyles.Bold;
cellTextState.Font = FontRepository.FindFont("Arial");
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// Speichern Sie das getaggte PDF-Dokument
document.Save(dataDir + "CreateTableElement.pdf");

// Prüfung der PDF/UA-Konformität
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Beispielquellcode für „Tabellenelement erstellen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument erstellen
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Stammstrukturelement abrufen
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// Markiertes PDF-Dokument speichern
document.Save(dataDir + "CreateTableElement.pdf");

// Überprüfung der PDF/UA-Konformität
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Abschluss

Sie haben gelernt, wie Sie mit Aspose.PDF für .NET ein Array-Element erstellen. Mit dieser Methode können Sie nun PDF-Dokumente mit dynamischen Tabellen generieren. Entdecken Sie gerne weitere Funktionen von Aspose.PDF, um sein volles Potenzial zu entdecken.

### FAQs

#### F: Was ist ein Array-Element in einem PDF-Dokument und warum sollte ich eines mit Aspose.PDF für .NET erstellen?

A: Ein Array-Element in einem PDF-Dokument stellt eine strukturierte Datensammlung dar, die häufig zum Erstellen von Tabellen oder Rastern verwendet wird. Möglicherweise müssen Sie mit Aspose.PDF für .NET ein Array-Element erstellen, wenn Sie dynamische PDFs generieren, die eine strukturierte Datenpräsentation erfordern, z. B. tabellarische Informationen oder Raster.

#### F: Wie vereinfacht Aspose.PDF für .NET den Prozess der Erstellung eines Array-Elements?

A: Aspose.PDF für .NET bietet einen umfassenden Satz an Klassen und Methoden, mit denen Sie Array-Elemente (Tabellen) in einem PDF-Dokument programmgesteuert erstellen, anpassen und verwalten können. Dadurch entfällt die Notwendigkeit einer manuellen PDF-Bearbeitung und die Erstellung strukturierter Datendarstellungen wird optimiert.

#### F: Was sind die wichtigsten Schritte beim Erstellen eines Array-Elements mit Aspose.PDF für .NET?

A: Zu den wichtigsten Schritten gehören das Einrichten der Umgebung, das Erstellen des Dokuments, das Abrufen des Stammstrukturelements, das Erstellen eines Tabellenelements, das Definieren von Zeilen und Zellen innerhalb der Tabelle sowie das Festlegen von Formatierungen und Eigenschaften für die Elemente. Das bereitgestellte Codebeispiel veranschaulicht diese Schritte.

####  F: Welche Rolle spielt das?`taggedContent` object play in creating an array element?

 A: Die`taggedContent` Objekt, das aus dem Dokument stammt`TaggedContent`Mit dieser Eigenschaft können Sie die Struktur des getaggten Inhalts im PDF-Dokument definieren. Dazu gehört das hierarchische Erstellen und Organisieren von Array-Elementen und ihren untergeordneten Elementen.

#### F: Wie stellt der Code die Zugänglichkeit und Semantik des erstellten Array-Elements sicher?

 A: Der Code legt Attribute wie fest`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , Und`ColSpan` um die Zugänglichkeit und Semantik des Array-Elements zu verbessern. Diese Attribute tragen zu einer gut strukturierten, informativen und optisch ansprechenden Darstellung von Daten bei.

#### F: Welche Bedeutung hat die PDF/UA-Konformität im Zusammenhang mit der Erstellung von Array-Elementen?

 A: Durch die PDF/UA-Konformität (Universal Accessibility) wird sichergestellt, dass die generierten PDF-Dokumente für Benutzer mit Behinderungen zugänglich sind und bestimmte Barrierefreiheitsstandards erfüllen. Das Codebeispiel prüft die PDF/UA-Konformität mithilfe von`Validate` Methode, die Ihnen dabei hilft, Dokumente zu erstellen, die umfassend und barrierefrei sind.

#### F: Kann ich die Formatierung und das Erscheinungsbild der Array-Elemente weiter anpassen?

A: Ja, Sie können die Formatierung und das Erscheinungsbild der Array-Elemente anpassen, indem Sie Attribute wie Hintergrundfarbe, Rahmenstil, Schriftgröße und Ausrichtung anpassen. Aspose.PDF für .NET bietet eine Vielzahl von Eigenschaften, um die visuelle Präsentation an Ihre Anforderungen anzupassen.

#### F: Wie kann ich dieses Wissen erweitern, um komplexere Tabellenstrukturen zu erstellen oder Array-Elemente in größere PDF-Dokumente zu integrieren?

A: Sie können dieses Wissen erweitern, indem Sie zusätzliche Funktionen von Aspose.PDF für .NET erkunden, wie z. B. das Zusammenführen mehrerer Array-Elemente, das Erstellen verschachtelter Tabellen, das Hinzufügen von Kopf- und Fußzeilen und die Integration von Array-Elementen in größere PDF-Layouts. Die Dokumentation und Beispiele der Bibliothek bieten Anleitungen für diese erweiterten Szenarios.

#### F: Ist es möglich, Daten aus externen Quellen wie Datenbanken oder Tabellenkalkulationen zu importieren, um die Array-Elemente zu füllen?

A: Ja, Sie können Daten aus externen Quellen importieren, um Array-Elemente zu füllen. Sie können Datenabruf- und Transformationstechniken in C# verwenden, um Daten aus Datenbanken, Tabellenkalkulationen oder anderen Quellen abzurufen und dann die Array-Elemente entsprechend zu füllen.

#### F: Wie kann ich das in diesem Tutorial gewonnene Wissen nutzen, um die Qualität und Benutzerfreundlichkeit von PDF-Dokumenten zu verbessern, die ich programmgesteuert erstelle?

A: Mit den Erkenntnissen aus diesem Tutorial können Sie strukturierte und optisch ansprechende Array-Elemente (Tabellen) in PDF-Dokumenten erstellen. Durch die Integration dieser Techniken können Sie die Lesbarkeit, Zugänglichkeit und Benutzererfahrung dynamisch generierter PDFs verbessern und sie informativer und benutzerfreundlicher machen.