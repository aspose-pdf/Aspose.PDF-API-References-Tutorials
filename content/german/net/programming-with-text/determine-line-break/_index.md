---
title: Zeilenumbruch in PDF-Datei bestimmen
linktitle: Zeilenumbruch in PDF-Datei bestimmen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Zeilenumbrüche in PDF-Dateien bestimmen.
type: docs
weight: 130
url: /de/net/programming-with-text/determine-line-break/
---
Dieses Tutorial führt Sie durch den Prozess der Bestimmung von Zeilenumbrüchen in PDF-Dateien mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die erforderlichen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer C#-Compiler muss auf Ihrem Computer installiert sein.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Einrichten des Projekts
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in der Sie Zeilenumbrüche bestimmen möchten, am Anfang der Datei die folgenden Using-Direktiven hinzu:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Schritt 3: Dokumentverzeichnis festlegen
 Suchen Sie im Code nach der Zeile, die besagt:`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den Pfad zum Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Erstellen Sie eine neue Dokumentinstanz
 Instanziieren Sie ein neues`Document` -Objekt, indem Sie die folgende Codezeile hinzufügen:

```csharp
Document doc = new Document();
```

## Schritt 5: Dem Dokument eine Seite hinzufügen
 Fügen Sie dem Dokument eine neue Seite hinzu, indem Sie das`Add` Methode der`Pages` Sammlung. Im bereitgestellten Code wird die neue Seite der Variablen zugewiesen`page`.

```csharp
Page page = doc.Pages.Add();
```

## Schritt 6: Textfragmente mit Zeilenumbrüchen hinzufügen
Erstellen Sie eine Schleife, um der Seite mehrere Textfragmente hinzuzufügen, die jeweils einen Absatz mit Zeilenumbrüchen enthalten.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## Schritt 7: Speichern Sie das PDF-Dokument und extrahieren Sie die Zeilenumbruchinformationen
 Speichern Sie das PDF-Dokument mit dem`Save` Methode der`Document` Objekt. Extrahieren Sie dann die Zeilenumbruchinformationen mithilfe des`GetNotifications` Methode der gewünschten Seite.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### Beispielquellcode zum Bestimmen des Zeilenumbruchs mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
	text.TextState.FontSize = 20;
	page.Paragraphs.Add(text);
}
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

## Abschluss
Sie haben mit Aspose.PDF für .NET erfolgreich Zeilenumbrüche in einem PDF-Dokument ermittelt. Die Zeilenumbruchinformationen wurden extrahiert und in einer Textdatei gespeichert.

### Häufig gestellte Fragen

#### F: Worauf liegt der Schwerpunkt dieses Tutorials?

A: Dieses Tutorial führt Sie durch den Prozess der Bestimmung von Zeilenumbrüchen in einer PDF-Datei mithilfe der Aspose.PDF für .NET-Bibliothek. Der bereitgestellte C#-Quellcode demonstriert die erforderlichen Schritte, um dies zu erreichen.

#### F: Welche Namespaces soll ich für dieses Tutorial importieren?

A: Importieren Sie in der Codedatei, in der Sie Zeilenumbrüche bestimmen möchten, die folgenden Namespaces am Anfang der Datei:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### F: Wie gebe ich das Dokumentverzeichnis an?

 A: Suchen Sie im Code die Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie erstelle ich eine neue Dokumentinstanz?

 A: In Schritt 4 instanziieren Sie eine neue`Document` Objekt mithilfe des bereitgestellten Codes.

#### F: Wie füge ich dem Dokument eine Seite hinzu?

 A: In Schritt 5 fügen Sie dem Dokument eine neue Seite hinzu, indem Sie`Add` Methode der`Pages` Sammlung.

#### F: Wie füge ich Textfragmente mit Zeilenumbrüchen hinzu?

A: In Schritt 6 erstellen Sie eine Schleife, um der Seite mehrere Textfragmente hinzuzufügen, die jeweils einen Absatz mit Zeilenumbrüchen enthalten.

#### F: Wie speichere ich das PDF-Dokument und extrahiere Zeilenumbruchinformationen?

 A: In Schritt 7 speichern Sie das PDF-Dokument mit dem`Save` Methode der`Document` Objekt. Anschließend extrahieren Sie die Zeilenumbruchinformationen mithilfe des`GetNotifications` Methode der gewünschten Seite und speichern Sie sie in einer Textdatei.

#### F: Was ist der Zweck der extrahierten Zeilenumbruchinformationen?

A: Die extrahierten Zeilenumbruchinformationen liefern Details zu den im PDF-Dokument vorhandenen Zeilenumbrüchen und Benachrichtigungen. Dies kann hilfreich sein, um zu analysieren und zu verstehen, wie Text und Absätze im Dokument strukturiert sind.

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.PDF für .NET Zeilenumbrüche in einem PDF-Dokument bestimmen. Sie können dieses Wissen nutzen, um Zeilenumbruchinformationen programmgesteuert aus PDF-Dateien zu extrahieren und zu analysieren.