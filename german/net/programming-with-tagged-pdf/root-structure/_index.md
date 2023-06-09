---
title: Wurzelstruktur
linktitle: Wurzelstruktur
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Verwendung von Stammstrukturelementen mit Aspose.PDF für .NET, um auf das Stamm- und StructTreeRoot-Objekt des PDF-Dokuments zuzugreifen.
type: docs
weight: 130
url: /de/net/programming-with-tagged-pdf/root-structure/
---
In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie Stammstrukturelemente mit Aspose.PDF für .NET verwenden. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert erstellen und bearbeiten können. Mit Root-Strukturelementen können Sie auf das StructTreeRoot-Objekt des PDF-Dokuments und das Root-Strukturelement zugreifen.

Lassen Sie uns in den Code eintauchen und lernen, wie Sie Stammstrukturelemente mit Aspose.PDF für .NET verwenden.

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
// Erstellen Sie das PDF-Dokument
Document document = new Document();
```

## Schritt 3: Arbeiten Sie mit getaggten Inhalten

Dann erhalten wir den getaggten Inhalt des Dokuments, mit dem wir arbeiten können.

```csharp
// Rufen Sie den getaggten Inhalt des Dokuments ab
ITaggedContent taggedContent = document.TaggedContent;
```

## Schritt 4: Dokumenttitel und Sprache festlegen

Wir können nun den Titel und die Sprache des Dokuments festlegen.

```csharp
// Definieren Sie den Titel und die Sprache des Dokuments
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Schritt 5: Greifen Sie auf das Stammstrukturelement zu

Jetzt können wir auf das StructTreeRoot-Objekt und das Stammstrukturelement des Dokuments zugreifen.

```csharp
// Greifen Sie auf das Wurzelstrukturelement zu
StructTreeRootElement structTreeRootElement = taggedContent.StructTreeRootElement;
StructureElement rootElement = taggedContent.RootElement;
```

### Beispielquellcode für Root Structure mit Aspose.PDF für .NET 
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

// Für den Zugriff werden die Eigenschaften StructTreeRootElement und RootElement verwendet
// StructTreeRoot-Objekt des PDF-Dokuments und zum Stammstrukturelement (Dokumentstrukturelement).
StructTreeRootElement structTreeRootElement = taggedContent.StructTreeRootElement;
StructureElement rootElement = taggedContent.RootElement;

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie Stammstrukturelemente mit Aspose.PDF für .NET verwenden. Sie können jetzt auf das StructTreeRoot-Objekt und das Stammstrukturelement des PDF-Dokuments zugreifen, um erweiterte Vorgänge an der Dokumentstruktur durchzuführen.
