---
title: Elemente der Textblockstruktur
linktitle: Elemente der Textblockstruktur
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Textblockstrukturelemente wie Überschriften und getaggte Absätze zu einem vorhandenen PDF-Dokument hinzufügen.
type: docs
weight: 220
url: /de/net/programming-with-tagged-pdf/text-block-structure-elements/
---

In diesem ausführlichen Tutorial führen wir Sie Schritt für Schritt durch den bereitgestellten C#-Quellcode, um mit Aspose.PDF für .NET Textblockstrukturelemente in einem getaggten PDF-Dokument zu erstellen. Befolgen Sie die nachstehenden Anweisungen, um zu verstehen, wie Sie Ihrem PDF-Dokument mehrstufige Überschriften und getaggte Absätze hinzufügen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung für die Verwendung von Aspose.PDF für .NET konfiguriert haben. Dazu gehört die Installation der Aspose.PDF-Bibliothek und die Konfiguration Ihres Projekts, um darauf zu verweisen.

## Schritt 2: Erstellen des PDF-Dokuments

In diesem Schritt erstellen wir mit Aspose.PDF ein neues PDF-Dokumentobjekt.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das PDF-Dokument
Document document = new Document();
```

Wir haben mit Aspose.PDF ein neues PDF-Dokument erstellt.

## Schritt 3: Markieren Sie den Inhalt und legen Sie Titel und Sprache fest

Lassen Sie uns nun den getaggten Inhalt des PDF-Dokuments abrufen und den Titel und die Sprache des Dokuments festlegen.

```csharp
// Holen Sie sich getaggte Inhalte
ITaggedContent taggedContent = document.TaggedContent;

// Definieren Sie den Titel und die Sprache des Dokuments
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Wir haben den Titel und die Sprache des getaggten PDF-Dokuments festgelegt.

## Schritt 4: Erhalten des Wurzelstrukturelements

Lassen Sie uns nun das Stammstrukturelement des PDF-Dokuments ermitteln.

```csharp
// Rufen Sie das Wurzelstrukturelement ab
StructureElement rootElement = taggedContent.RootElement;
```

Wir haben das Wurzelstrukturelement des PDF-Dokuments erhalten.

## Schritt 5: Überschriften und Absätze hinzufügen

Jetzt fügen wir unserem PDF-Dokument Überschriften verschiedener Ebenen und markierte Absätze hinzu.

```csharp
//Erstellen Sie Überschriften auf verschiedenen Ebenen
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);

// Definition des Headertextes
h1.SetText("H1. Level 1 header");
h2.SetText("H2. Level 2 header");
h3.SetText("H3. Level 3 header");
h4.SetText("H4. Level 4 header");
h5.SetText("H5. Heading level 5");
h6.SetText("H6. Level 6 header");

// Fügen Sie Header zum Stammstrukturelement hinzu
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Erstellen Sie den Absatz
ParagraphElement p = taggedContent.CreateParagraphElement();

// Definition des Texts des Absatzes
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet Nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");

// Fügen Sie den Absatz zum Stammstrukturelement hinzu
rootElement.AppendChild(p);
```

Wir haben dem Wurzelstrukturelement des PDF-Dokuments Überschriften verschiedener Ebenen und einen getaggten Absatz hinzugefügt.

## Schritt 6: Speichern des PDF-Dokuments

Nachdem wir nun mit der Bearbeitung des PDF-Dokuments fertig sind, speichern wir es in einer Datei.

```csharp
// Speichern Sie das getaggte PDF-Dokument
document.Save(dataDir + "ElementsDeStructureDeBlocsDeTexte.pdf");
```

Wir haben das getaggte PDF-Dokument mit den Textblockstrukturelementen im angegebenen Verzeichnis gespeichert.

### Beispielquellcode für Textblockstrukturelemente mit Aspose.PDF für .NET 
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

// Stammstrukturelement abrufen
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
h1.SetText("H1. Header of Level 1");
h2.SetText("H2. Header of Level 2");
h3.SetText("H3. Header of Level 3");
h4.SetText("H4. Header of Level 4");
h5.SetText("H5. Header of Level 5");
h6.SetText("H6. Header of Level 6");
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
rootElement.AppendChild(p);

// Markiertes PDF-Dokument speichern
document.Save(dataDir + "TextBlockStructureElements.pdf");
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET Textblockstrukturelemente wie Überschriften und getaggte Absätze zu einem PDF-Dokument hinzufügt. Mit diesen Funktionen können Sie nun die Struktur und Zugänglichkeit Ihrer PDF-Dokumente verbessern.
