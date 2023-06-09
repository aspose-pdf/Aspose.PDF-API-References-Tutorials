---
title: Textstrukturelemente
linktitle: Textstrukturelemente
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Textstrukturelemente zu einem PDF-Dokument hinzufügen. Verbessern Sie die Struktur und Zugänglichkeit Ihrer PDFs.
type: docs
weight: 230
url: /de/net/programming-with-tagged-pdf/text-structure-elements/
---
In diesem ausführlichen Tutorial führen wir Sie Schritt für Schritt durch den bereitgestellten C#-Quellcode, um mit Aspose.PDF für .NET Textstrukturelemente in einem getaggten PDF-Dokument zu erstellen. Befolgen Sie die nachstehenden Anweisungen, um zu verstehen, wie Sie Textstrukturelemente zu Ihrem PDF-Dokument hinzufügen.

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

## Schritt 5: Hinzufügen des Absatzstrukturelements

Fügen wir nun unserem PDF-Dokument ein Absatzstrukturelement hinzu.

```csharp
// Erstellen Sie das Absatzstrukturelement
ParagraphElement p = taggedContent.CreateParagraphElement();

// Definition des Textes des Absatzstrukturelements
p.SetText("Paragraph.");

// Fügen Sie das Absatzstrukturelement zum Stammstrukturelement hinzu
rootElement.AppendChild(p);
```

Wir haben unserem PDF-Dokument ein Absatzstrukturelement mit Text hinzugefügt.

## Schritt 6: Speichern des PDF-Dokuments

Nachdem wir nun mit der Bearbeitung des PDF-Dokuments fertig sind, speichern wir es in einer Datei.

```csharp
// Speichern Sie das getaggte PDF-Dokument
document.Save(dataDir + "ElementDeStructureDeTexte.pdf");
```

Wir haben das mit dem Textstrukturelement markierte PDF-Dokument im angegebenen Verzeichnis gespeichert.


### Beispielquellcode für Textstrukturelemente mit Aspose.PDF für .NET 

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

//Stammstrukturelemente abrufen
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p = taggedContent.CreateParagraphElement();

// Legen Sie „Text“ auf „Textstrukturelement“ fest
p.SetText("Paragraph.");
rootElement.AppendChild(p);

// Markiertes PDF-Dokument speichern
document.Save(dataDir + "TextStructureElement.pdf");
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man Aspose.PDF für .NET verwendet, um Textstrukturelemente zu einem PDF-Dokument hinzuzufügen. Mit diesen Funktionen können Sie nun die Struktur und Zugänglichkeit Ihrer PDF-Dokumente verbessern.