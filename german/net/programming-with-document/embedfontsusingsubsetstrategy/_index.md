---
title: Betten Sie Schriftarten mithilfe der Subset-Strategie ein
linktitle: Betten Sie Schriftarten mithilfe der Subset-Strategie ein
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Subset Strategy mithilfe von Aspose.PDF für .NET Schriftarten in eine PDF-Datei einbetten. Optimieren Sie die Größe Ihrer PDF-Datei, indem Sie nur die erforderlichen Zeichen einbetten.
type: docs
weight: 130
url: /de/net/programming-with-document/embedfontsusingsubsetstrategy/
---

In diesem Tutorial besprechen wir, wie man Schriftarten mit einer Teilmengenstrategie mithilfe von Aspose.PDF für .NET in eine PDF-Datei einbettet. Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler PDF-Dokumente programmgesteuert erstellen, bearbeiten und bearbeiten können. Das Einbetten von Schriftarten in eine PDF-Datei ist ein wichtiger Schritt, um sicherzustellen, dass das Dokument auf verschiedenen Geräten korrekt angezeigt wird, unabhängig davon, ob die erforderlichen Schriftarten auf diesen Geräten installiert sind oder nicht.

## Schritt 1: Erstellen Sie eine neue C#-Konsolenanwendung
Erstellen Sie zunächst eine neue C#-Konsolenanwendung in Visual Studio. Sie können es beliebig benennen. Sobald das Projekt erstellt ist, müssen Sie einen Verweis auf die Bibliothek Aspose.PDF für .NET hinzufügen.

## Schritt 2: Importieren Sie den Aspose.PDF-Namespace
Fügen Sie oben in Ihrer C#-Datei die folgende Codezeile hinzu, um den Aspose.PDF-Namespace zu importieren:

```csharp
using Aspose.Pdf;
```

## Schritt 3: Laden Sie eine vorhandene PDF-Datei
Um Schriftarten in eine vorhandene PDF-Datei einzubetten, müssen Sie diese Datei mithilfe der Document-Klasse laden. Der folgende Code zeigt, wie eine vorhandene PDF-Datei geladen wird:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laden Sie eine vorhandene PDF-Datei
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 4: Schriftarten mit Subset-Strategie einbetten
Aspose.PDF für .NET bietet zwei Strategien zum Einbetten von Schriftarten: SubsetAllFonts und SubsetEmbeddedFontsOnly.

Die SubsetAllFonts-Strategie bettet alle Schriftarten als Teilmenge in das Dokument ein. Eine Teilmenge ist ein Teil der Schriftart, der nur die im Dokument verwendeten Zeichen enthält. Diese Strategie ist nützlich, um die Dateigröße des PDF-Dokuments zu reduzieren.

Die SubsetEmbeddedFontsOnly-Strategie bettet nur die Teilmenge der Schriftarten ein, die bereits im Dokument eingebettet sind. Wenn eine Schriftart nicht eingebettet ist, ist sie von dieser Strategie nicht betroffen.

Der folgende Code zeigt, wie Schriftarten mit einer Teilmengenstrategie in eine PDF-Datei eingebettet werden:

```csharp
// Bei SubsetAllFonts werden alle Schriftarten als Teilmenge in das Dokument eingebettet.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// Bei vollständig eingebetteten Schriftarten wird eine Teilmenge der Schriftarten eingebettet, Schriftarten, die nicht in das Dokument eingebettet sind, sind jedoch nicht betroffen.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## Schritt 5: Speichern Sie das PDF-Dokument
Nachdem Sie alle Schriftarten mit einer Teilmengenstrategie in die PDF-Datei eingebettet haben, müssen Sie das Dokument speichern. Der folgende Code zeigt, wie die PDF-Datei gespeichert wird:

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### Beispielquellcode zum Einbetten von Schriftarten mit Teilmengenstrategie unter Verwendung von Aspose.PDF für .NET. 

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
// Bei SubsetAllFonts werden alle Schriftarten als Teilmenge in das Dokument eingebettet.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
// Bei vollständig eingebetteten Schriftarten wird eine Teilmenge der Schriftarten eingebettet, Schriftarten, die nicht in das Dokument eingebettet sind, sind jedoch nicht betroffen.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
doc.Save(dataDir + "Output_out.pdf");
```

## Abschluss
In diesem Artikel haben wir besprochen, wie man Schriftarten mit einer Teilmengenstrategie mithilfe von Aspose.PDF für .NET in eine PDF-Datei einbettet. Aspose.PDF für .NET bietet eine einfache und benutzerfreundliche API für die Arbeit mit PDF-Dokumenten, einschließlich des Hinzufügens und Einbettens von Schriftarten mit verschiedenen Strategien. Das Einbetten von Schriftarten in eine PDF-Datei ist ein wichtiger Schritt, um sicherzustellen, dass das Dokument auf verschiedenen Geräten korrekt angezeigt wird, und die Subset-Strategie ist eine nützliche Funktion, um die Dateigröße des PDF-Dokuments zu reduzieren.

