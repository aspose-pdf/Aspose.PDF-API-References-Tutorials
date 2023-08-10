---
title: Suchen Sie Text mit Dot Net Regex
linktitle: Suchen Sie Text mit Dot Net Regex
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET mithilfe regulärer .NET-Ausdrücke in einem PDF-Dokument nach Text suchen.
type: docs
weight: 480
url: /de/net/programming-with-text/search-text-with-dot-net-regex/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.PDF für .NET mithilfe regulärer .NET-Ausdrücke in einem PDF-Dokument nach Text suchen. Der bereitgestellte C#-Quellcode demonstriert den Prozess Schritt für Schritt.

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

## Schritt 3: Legen Sie den Pfad zum Dokumentverzeichnis fest

 Legen Sie den Pfad zu Ihrem Dokumentverzeichnis mit fest`dataDir` Variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Erstellen Sie ein .NET-Regex-Objekt

 Ein ... kreieren`.NET Regex` Objekt zum Definieren des Suchmusters:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Ersetzen`@"[\S]+"` mit Ihrem gewünschten Muster für reguläre Ausdrücke.

## Schritt 5: Laden Sie das PDF-Dokument

 Laden Sie das PDF-Dokument mit`Document` Klasse:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Ersetzen`"SearchTextRegex.pdf"` mit dem tatsächlichen Namen Ihrer PDF-Datei.

## Schritt 6: Holen Sie sich eine bestimmte Seite

Holen Sie sich die gewünschte Seite des Dokuments:

```csharp
Page page = document.Pages[1];
```

 Ersetzen`1` mit der gewünschten Seitenzahl (1-basierter Index).

## Schritt 7: Erstellen Sie einen TextFragmentAbsorber

 Ein ... kreieren`TextFragmentAbsorber`Objekt, um alle Instanzen des eingegebenen regulären Ausdrucks zu finden:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Schritt 8: Akzeptieren Sie die Seite für die Seite

Akzeptieren Sie den Absorber für die Seite:

```csharp
page.Accept(textFragmentAbsorber);
```

## Schritt 9: Abrufen der extrahierten Textfragmente

Holen Sie sich die extrahierten Textfragmente mit`TextFragments` Eigentum der`TextFragmentAbsorber` Objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Schritt 10: Gehen Sie die Textfragmente in einer Schleife durch

Durchlaufen Sie die abgerufenen Textfragmente und führen Sie die gewünschten Aktionen aus:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Ändern Sie den Code innerhalb der Schleife, um bei Bedarf weitere Aktionen für jedes Textfragment auszuführen.

### Beispielquellcode für Search Text With Dot Net Regex mit Aspose.PDF für .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Erstellen Sie ein Regex-Objekt, um alle Wörter zu finden
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Dokument öffnen
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Holen Sie sich eine bestimmte Seite
Page page = document.Pages[1];
// Erstellen Sie ein TextAbsorber-Objekt, um alle Instanzen des eingegebenen regulären Ausdrucks zu finden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Akzeptieren Sie den Absorber für die Seite
page.Accept(textFragmentAbsorber);
// Holen Sie sich die extrahierten Textfragmente
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Durchlaufe die Fragmente
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mithilfe von regulären .NET-Ausdrücken in einem PDF-Dokument mit Aspose.PDF für .NET nach Text suchen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Einrichten des Projekts bis zum Zugriff auf die extrahierten Textfragmente. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um erweiterte Textsuchen in PDF-Dateien durchzuführen.