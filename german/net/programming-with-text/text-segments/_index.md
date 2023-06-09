---
title: Textsegmente
linktitle: Textsegmente
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mithilfe regulärer Ausdrücke in Aspose.PDF für .NET nach bestimmten Textsegmenten in einem PDF-Dokument suchen.
type: docs
weight: 540
url: /de/net/programming-with-text/text-segments/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.PDF für .NET nach bestimmten Textsegmenten in einem PDF-Dokument suchen. Der bereitgestellte C#-Quellcode demonstriert verschiedene Szenarien mit regulären Ausdrücken.

## Voraussetzungen

Bevor Sie mit dem Tutorial fortfahren, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF für .NET-Bibliothek installiert. Sie können es von der Aspose-Website herunterladen oder NuGet verwenden, um es in Ihrem Projekt zu installieren.

## Schritt 1: Richten Sie das Projekt ein

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Importieren Sie die erforderlichen Namespaces

Fügen Sie am Anfang Ihrer C#-Datei die folgenden using-Anweisungen hinzu, um die erforderlichen Namespaces zu importieren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Schritt 3: Verwenden Sie TextFragmentAbsorber für die Textsuche

 Ein ... kreieren`TextFragmentAbsorber`Objekt zum Suchen nach bestimmten Textsegmenten mithilfe regulärer Ausdrücke:

```csharp
TextFragmentAbsorber textFragmentAbsorber;
```

## Schritt 4: Führen Sie Textsuchen mit regulären Ausdrücken durch

Führen Sie Textsuchen basierend auf verschiedenen Szenarien mithilfe regulärer Ausdrücke durch. Hier ein paar Beispiele:

- So suchen Sie nach einer exakten Wortübereinstimmung: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
```

- So suchen Sie nach einer Zeichenfolge in Groß- oder Kleinschreibung: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
```

- So suchen Sie nach allen Zeichenfolgen im PDF-Dokument: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

- So suchen Sie Text nach einer bestimmten Zeichenfolge bis zu einem Zeilenumbruch: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
```

- So finden Sie Text nach einer Regex-Übereinstimmung: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
```

- So suchen Sie im PDF-Dokument nach Hyperlinks/URLs: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```

Ersetzen Sie die regulären Ausdrücke durch Ihre gewünschten Suchmuster.

## Schritt 5: Führen Sie die Suche durch und verarbeiten Sie die Ergebnisse

 Führen Sie die Suche mit dem erstellten durch`TextFragmentAbsorber` Objekt und verarbeiten Sie die Ergebnisse entsprechend Ihren Anforderungen.

### Beispielquellcode für Textsegmente mit Aspose.PDF für .NET 
```csharp
TextFragmentAbsorber textFragmentAbsorber;
// Um nach einer genauen Übereinstimmung eines Wortes zu suchen, können Sie die Verwendung eines regulären Ausdrucks in Betracht ziehen.
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
//Um eine Zeichenfolge entweder in Groß- oder Kleinbuchstaben zu durchsuchen, können Sie die Verwendung eines regulären Ausdrucks in Betracht ziehen.
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
// Um alle Zeichenfolgen im PDF-Dokument zu durchsuchen (alle Zeichenfolgen zu analysieren), versuchen Sie bitte, den folgenden regulären Ausdruck zu verwenden.
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
// Finden Sie eine Übereinstimmung mit der Suchzeichenfolge und erhalten Sie alles nach der Zeichenfolge bis zum Zeilenumbruch.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
// Bitte verwenden Sie den folgenden regulären Ausdruck, um Text zu finden, der auf die Regex-Übereinstimmung folgt.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
// Um Hyperlinks/URLs in einem PDF-Dokument zu durchsuchen, versuchen Sie bitte, den folgenden regulären Ausdruck zu verwenden.
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```


## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET nach bestimmten Textsegmenten in einem PDF-Dokument suchen. Dieses Tutorial lieferte Beispiele für verschiedene Suchszenarien mit regulären Ausdrücken. Sie können diesen Code nun in Ihre eigenen C#-Projekte integrieren, um Textsegmente in PDF-Dateien zu suchen und zu verarbeiten.