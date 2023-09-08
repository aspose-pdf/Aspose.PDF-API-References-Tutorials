---
title: Betten Sie Schriftarten mit der Subset-Strategie in eine PDF-Datei ein
linktitle: Betten Sie Schriftarten mit der Subset-Strategie ein
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

### FAQs zum Einbetten von Schriftarten in PDF-Dateien mit Teilmengenstrategie

#### F: Was ist eine Teilmengenstrategie zum Einbetten von Schriftarten in eine PDF-Datei?

A: Eine Teilmengenstrategie zum Einbetten von Schriftarten in eine PDF-Datei bedeutet, dass nur ein Teil der Schriftart eingebettet wird, der die im Dokument verwendeten Zeichen enthält. Dies trägt dazu bei, die Dateigröße des PDF-Dokuments zu reduzieren, indem unnötige Schriftartdaten entfernt werden.

#### F: Was ist der Unterschied zwischen den Strategien SubsetAllFonts und SubsetEmbeddedFontsOnly?

 A: Die`SubsetAllFonts`Die Strategie bettet alle Schriftarten als Teilmenge in das Dokument ein, während die`SubsetEmbeddedFontsOnly` Die Strategie bettet nur die Teilmenge der Schriftarten ein, die bereits im Dokument eingebettet sind. Die letztere Strategie wirkt sich nicht auf Schriftarten aus, die noch nicht eingebettet sind.

#### F: Warum ist das Einbetten von Schriftarten mit einer Teilmengenstrategie wichtig?

A: Das Einbetten von Schriftarten mit einer Teilmengenstrategie ist wichtig, um sicherzustellen, dass die PDF-Datei die erforderlichen Schriftartdaten für die korrekte Anzeige von Text enthält und gleichzeitig die Dateigröße kleiner gehalten wird, indem nur die im Dokument verwendeten Zeichen einbezogen werden.

#### F: Kann ich Aspose.PDF für .NET verwenden, um Schriftarten mit unterschiedlichen Strategien einzubetten?

 A: Ja, Aspose.PDF für .NET bietet verschiedene Strategien zum Einbetten von Schriftarten, darunter`SubsetAllFonts` Und`SubsetEmbeddedFontsOnly`. Basierend auf Ihren Anforderungen können Sie die passende Strategie wählen.

#### F: Ist Aspose.PDF für .NET eine zuverlässige Bibliothek für die Arbeit mit PDF-Dokumenten?

A: Ja, Aspose.PDF für .NET ist eine zuverlässige und leistungsstarke Bibliothek für die Arbeit mit PDF-Dokumenten. Es bietet umfangreiche Funktionen zum Erstellen, Bearbeiten und Bearbeiten von PDF-Dateien in .NET-Anwendungen.