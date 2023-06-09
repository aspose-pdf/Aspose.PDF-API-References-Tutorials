---
title: Eigenschaften von Strukturelementen
linktitle: Eigenschaften von Strukturelementen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Arbeiten mit Strukturelementeigenschaften in einem PDF-Dokument mit Aspose.PDF für .NET. Erstellen Sie informationsreiche Strukturelemente.
type: docs
weight: 150
url: /de/net/programming-with-tagged-pdf/structure-elements-properties/
---
In diesem Leitfaden zeigen wir Ihnen, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET mit Strukturelementeigenschaften in einem PDF-Dokument arbeiten. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dateien programmgesteuert erstellen, bearbeiten und konvertieren können.

Lassen Sie uns in den Code eintauchen und lernen, wie Sie mit Aspose.PDF für .NET mit Strukturelementeigenschaften in einem PDF-Dokument arbeiten.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Aspose.PDF für .NET installiert und Ihre Entwicklungsumgebung eingerichtet haben.

## Schritt 1: Dokument erstellen

 Der erste Schritt besteht darin, ein neues PDF-Dokument mit zu erstellen`Document` Klasse.

```csharp
// Erstellen Sie das PDF-Dokument
Document document = new Document();
```

## Schritt 2: Greifen Sie auf getaggte Inhalte zu

 Als nächstes greifen wir mithilfe von auf den getaggten Inhalt des Dokuments zu`ITaggedContent` Objekt.

```csharp
//Greifen Sie auf getaggte Inhalte zu
Tagged.ITaggedContent taggedContent = document.TaggedContent;
```

## Schritt 3: Titel und Sprache festlegen

 Jetzt können wir den Titel und die Sprache des Dokuments mit festlegen`SetTitle` Und`SetLanguage` Methoden der`ITaggedContent` Objekt.

```csharp
// Definieren Sie den Titel des Dokuments
taggedContent.SetTitle("Tagged PDF document");

// Legen Sie die Dokumentsprache fest
taggedContent.SetLanguage("fr-FR");
```

## Schritt 4: Strukturelemente erstellen

Anschließend erstellen wir die Strukturelemente im PDF-Dokument. In diesem Beispiel erstellen wir ein Abschnittselement (`SectElement`) und ein Header-Element (`HeaderElement`).

```csharp
//Erstellen Sie ein Abschnittselement
StructureElement rootElement = taggedContent.RootElement;
SectElement sect = taggedContent.CreateSectElement();
rootElement.AppendChild(sect);

// Erstellen Sie ein Header-Element
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
sect.AppendChild(h1);
h1.SetText("Header");
h1.Title = "Title";
h1.Language = "fr-FR";
h1.AlternativeText = "Alternative Text";
h1.ExpansionText = "Expansion Text";
h1.ActualText = "Actual Text";
```

## Schritt 5: Speichern Sie das getaggte PDF-Dokument

Abschließend speichern wir das getaggte PDF-Dokument.

```csharp
// Speichern Sie das getaggte PDF-Dokument
document.Save(dataDir + "StructureElementsProperties.pdf");
```

### Beispielquellcode für Strukturelementeigenschaften mit Aspose.PDF für .NET 
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

// Strukturelemente erstellen
StructureElement rootElement = taggedContent.RootElement;
SectElement sect = taggedContent.CreateSectElement();
rootElement.AppendChild(sect);
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
sect.AppendChild(h1);
h1.SetText("The Header");
h1.Title = "Title";
h1.Language = "en-US";
h1.AlternativeText = "Alternative Text";
h1.ExpansionText = "Expansion Text";
h1.ActualText = "Actual Text";

// Markiertes PDF-Dokument speichern
document.Save(dataDir + "StructureElementsProperties.pdf");

```

## Abschluss

Herzlichen Glückwunsch! Sie wissen jetzt, wie Sie mit Aspose.PDF für .NET mit Strukturelementeigenschaften in einem PDF-Dokument arbeiten. Sie können die Funktionen von Aspose.PDF weiter erkunden, um personalisierte PDF-Dokumente mit informationsreichen Strukturelementen zu erstellen.
