---
title: Greifen Sie auf untergeordnete Elemente zu
linktitle: Greifen Sie auf untergeordnete Elemente zu
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Zugreifen auf und Bearbeiten untergeordneter Elemente eines PDF-Dokuments mit Aspose.PDF für .NET. Personalisieren Sie Ihren PDF-Inhalt.
type: docs
weight: 10
url: /de/net/programming-with-tagged-pdf/access-children-elements/
---
In diesem Tutorial stellen wir Ihnen eine Schritt-für-Schritt-Anleitung zum Zugriff auf untergeordnete Elemente eines PDF-Dokuments mit Aspose.PDF für .NET zur Verfügung. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können. Mithilfe der markierten Inhaltsstrukturfunktionen von Aspose.PDF können Sie auf die Eigenschaften strukturierter Elemente in einem PDF-Dokument zugreifen und diese ändern.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Visual Studio mit .NET Framework installiert.
2. Die Aspose.PDF-Bibliothek für .NET.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues Projekt in Visual Studio und fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu. Sie können die Bibliothek von der offiziellen Website von Aspose herunterladen und auf Ihrem Computer installieren.

## Schritt 2: Importieren Sie die erforderlichen Namespaces

Importieren Sie in Ihre C#-Codedatei die Namespaces, die für den Zugriff auf die von Aspose.PDF bereitgestellten Klassen und Methoden erforderlich sind:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Schritt 3: Laden des PDF-Dokuments und Zugriff auf untergeordnete Elemente

Verwenden Sie den folgenden Code, um das PDF-Dokument zu laden und auf die untergeordneten Elemente zuzugreifen:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document(dataDir + "StructureElementsTree.pdf");
ITaggedContent taggedContent = document.TaggedContent;
ElementList elementList = taggedContent.StructTreeRootElement.ChildElements;

foreach(Element element in elementList)
{
if (element is StructureElement)
{
StructureElement structureElement = element as StructureElement;
// Greifen Sie auf die Eigenschaften des Elements zu
string title = structureElement.Title;
string language = structureElement.Language;
string actualText = structureElement.ActualText;
string expansionText = structureElement.ExpansionText;
string alternativeText = structureElement.AlternativeText;
}
}
```

Mit diesem Code können Sie auf die untergeordneten Elemente im Stammverzeichnis der PDF-Dokumentstruktur zugreifen und die Eigenschaften jedes Elements abrufen.

## Schritt 4: Auf untergeordnete Root-Elemente zugreifen und Eigenschaften ändern

Verwenden Sie den folgenden Code, um auf die untergeordneten Elemente des Stammelements zuzugreifen und die Eigenschaften zu ändern:

```csharp
elementList = taggedContent.RootElement.ChildElements[1].ChildElements;

foreach(Element element in elementList)
{
if (element is StructureElement)
{
StructureElement structureElement = element as StructureElement;
// Ändern Sie die Eigenschaften des Elements
structureElement.Title = "title";
structureElement.Language = "fr-FR";
structureElement.ActualText = "actual text";
structureElement.ExpansionText = "exp";
structureElement.AlternativeText = "alt";
}
}
```

Mit diesem Code können Sie auf die untergeordneten Elemente des ersten Elements des Stammelements zugreifen und die Eigenschaften jedes Elements ändern.


### Beispielquellcode für Access Children Elements mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF-Dokument öffnen
Document document = new Document(dataDir + "StructureElementsTree.pdf");
// Holen Sie sich Inhalte für die Arbeit mit TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Zugriff auf Root-Element(e)
ElementList elementList = taggedContent.StructTreeRootElement.ChildElements;
foreach (Element element in elementList)
{
	if (element is StructureElement)
	{
		StructureElement structureElement = element as StructureElement;
		// Holen Sie sich Eigenschaften
		string title = structureElement.Title;
		string language = structureElement.Language;
		string actualText = structureElement.ActualText;
		string expansionText = structureElement.ExpansionText;
		string alternativeText = structureElement.AlternativeText;
	}
}
// Zugriff auf untergeordnete Elemente des ersten Elements im Stammelement
elementList = taggedContent.RootElement.ChildElements[1].ChildElements;
foreach (Element element in elementList)
{
	if (element is StructureElement)
	{
		StructureElement structureElement = element as StructureElement;
		// Eigenschaften festlegen
		structureElement.Title = "title";
		structureElement.Language = "fr-FR";
		structureElement.ActualText = "actual text";
		structureElement.ExpansionText = "exp";
		structureElement.AlternativeText = "alt";
	}
}
// Markiertes PDF-Dokument speichern
document.Save(dataDir + "AccessChildrenElements.pdf");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.PDF für .NET auf untergeordnete Elemente eines PDF-Dokuments zugreifen und Elementeigenschaften ändern. Dadurch können Sie die strukturierten Elemente in einem PDF-Dokument Ihren Bedürfnissen entsprechend anpassen und bearbeiten.