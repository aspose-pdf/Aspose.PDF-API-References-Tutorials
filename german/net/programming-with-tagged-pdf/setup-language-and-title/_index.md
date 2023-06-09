---
title: Sprache und Titel einrichten
linktitle: Sprache und Titel einrichten
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konfigurieren der Sprache und des Titels eines PDF-Dokuments mit Aspose.PDF für .NET. Erstellen Sie personalisierte mehrsprachige Dokumente.
type: docs
weight: 140
url: /de/net/programming-with-tagged-pdf/setup-language-and-title/
---
In dieser Anleitung erklären wir Ihnen, wie Sie die Sprache und den Titel eines PDF-Dokuments mithilfe der Aspose.PDF-Bibliothek für .NET konfigurieren. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dateien programmgesteuert erstellen, bearbeiten und konvertieren können.

Lassen Sie uns in den Code eintauchen und lernen, wie Sie die Sprache und den Titel eines PDF-Dokuments mit Aspose.PDF für .NET konfigurieren.

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
taggedContent.SetTitle("Example of tagged document");

// Legen Sie die Dokumentsprache fest
taggedContent.SetLanguage("fr-FR");
```

## Schritt 4: Mehrsprachige Inhalte hinzufügen

Als Nächstes fügen wir dem Dokument mehrsprachigen Inhalt hinzu, indem wir Absatzelemente für jede Sprache verwenden.

```csharp
// Fügen Sie einen Absatz auf Englisch hinzu
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Fügen Sie einen Absatz auf Deutsch hinzu
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hello Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Fügen Sie einen Absatz auf Französisch hinzu
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Hello world!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Fügen Sie einen Absatz auf Spanisch hinzu
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);
```

## Schritt 5: Speichern Sie das getaggte PDF-Dokument

Abschließend speichern wir das getaggte PDF-Dokument.

```csharp
// Speichern Sie das getaggte PDF-Dokument
document.Save(dataDir + "SetupLanguageAndTitle.pdf");
```

### Beispielquellcode für Setup-Sprache und -Titel mit Aspose.PDF für .NET 
```csharp

Document document = new Document();

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Get TaggedContent abrufen
Tagged.ITaggedContent taggedContent = document.TaggedContent;

// Legen Sie Titel und Sprache fest
taggedContent.SetTitle("Example Tagged Document");
taggedContent.SetLanguage("en-US");

// Kopfzeile (en-US, vom Dokument geerbt)
LogicalStructure.HeaderElement h1 = taggedContent.CreateHeaderElement(1);
h1.SetText("Phrase on different languages");
taggedContent.RootElement.AppendChild(h1);

// Absatz (Englisch)
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Absatz (deutsch)
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hallo Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Absatz (Französisch)
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Bonjour le monde!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Absatz (Spanisch)
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);

// Markiertes PDF-Dokument speichern
document.Save(dataDir + "SetupLanguageAndTitle.pdf");

```

## Abschluss

Herzlichen Glückwunsch! Sie wissen jetzt, wie Sie die Sprache und den Titel eines PDF-Dokuments mit Aspose.PDF für .NET konfigurieren. Sie können die Funktionen von Aspose.PDF weiter erkunden, um personalisierte und mehrsprachige PDF-Dokumente zu erstellen.
