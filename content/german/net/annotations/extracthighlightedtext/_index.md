---
title: Extrahieren Sie hervorgehobenen Text in einer PDF-Datei
linktitle: Extrahieren Sie hervorgehobenen Text in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET hervorgehobenen Text in einer PDF-Datei extrahieren.
type: docs
weight: 60
url: /de/net/annotations/extracthighlightedtext/
---
Um hervorgehobenen Text in einer PDF-Datei zu extrahieren, können Sie die Aspose.PDF für .NET-API verwenden. Diese API bietet eine einfache Möglichkeit, den gesamten Text abzurufen, der in einem Dokument hervorgehoben wurde.

## Schritt 1: Laden Sie das PDF-Dokument

 Der erste Schritt beim Extrahieren von hervorgehobenem Text in einer PDF-Datei besteht darin, das Dokument mithilfe der Aspose.PDF für .NET-API zu laden. Sie können dies tun, indem Sie eine neue Instanz von erstellen`Document` Klasse und Übergabe des Pfads zum PDF-Dokument als Parameter. 

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## Schritt 2: Durchlaufen Sie alle Anmerkungen

 Der nächste Schritt besteht darin, alle Anmerkungen im PDF-Dokument zu durchlaufen. Sie können dies mit a tun`foreach` Schleife, etwa so:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// Code kommt hierher
}
```

## Schritt 3: Text-Markup-Anmerkungen filtern

 Im Inneren`foreach` In der Schleife müssen Sie alle Anmerkungen herausfiltern, die keine Textmarkierungsanmerkungen sind. Sie können dies tun, indem Sie prüfen, ob die Anmerkung eine Instanz von ist`TextMarkupAnnotation` Klasse.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// Code kommt hierher
}
```

## Schritt 4: Hervorgehobene Textfragmente abrufen

 Nachdem Sie alle Text-Markup-Anmerkungen herausgefiltert haben, können Sie die hervorgehobenen Textfragmente für jede Anmerkung abrufen. Sie können dies tun, indem Sie die anrufen`GetMarkedTextFragments()` Methode auf der`TextMarkupAnnotation` Objekt.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## Schritt 5: Zeigen Sie den hervorgehobenen Text an

 Abschließend können Sie dem Benutzer den hervorgehobenen Text anzeigen. Sie können dies tun, indem Sie jeden durchlaufen`TextFragment` Objekt in der`TextFragmentCollection` und das Aufrufen des`Text` Eigentum.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Beispielquellcode zum Extrahieren von hervorgehobenem Text mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie mit Aspose.PDF für .NET hervorgehobenen Text aus einem PDF-Dokument extrahieren. Durch Befolgen der Schritt-für-Schritt-Anleitung und Verwendung des bereitgestellten C#-Quellcodes können Entwickler hervorgehobenen Text in ihren PDF-Dokumenten einfach extrahieren und verwalten.

### FAQs zum Extrahieren von hervorgehobenem Text in einer PDF-Datei

#### F: Was sind Textmarkierungsanmerkungen in einem PDF-Dokument?

A: Textmarkup-Anmerkungen sind Anmerkungen, die bestimmten Text in einem PDF-Dokument hervorheben oder markieren. Beispiele für Textmarkierungsanmerkungen sind Hervorhebungen, Unterstreichungen und Durchstreichungen.

#### F: Kann ich mit Aspose.PDF für .NET Text aus anderen Arten von Anmerkungen extrahieren?

A: Ja, Aspose.PDF für .NET bietet verschiedene Methoden zum Extrahieren von Text aus verschiedenen Arten von Anmerkungen, einschließlich Textmarkierungsanmerkungen, Freitextanmerkungen und mehr.

#### F: Unterstützt Aspose.PDF für .NET das Extrahieren von Text aus passwortgeschützten PDF-Dateien?

 A: Ja, Aspose.PDF für .NET unterstützt das Extrahieren von Text aus passwortgeschützten PDF-Dateien. Sie müssen das richtige Passwort angeben, wenn Sie das PDF-Dokument mit laden`Document` Klasse.

#### F: Kann ich hervorgehobenen Text nach anderen Kriterien filtern, beispielsweise nach Farbe oder Autor?

A: Ja, Sie können hervorgehobenen Text nach anderen Kriterien filtern, z. B. nach Farbe, Autor oder Erstellungsdatum. Aspose.PDF für .NET bietet Methoden für den Zugriff auf und das Filtern von Anmerkungen basierend auf ihren Eigenschaften.

#### F: Ist es möglich, den extrahierten hervorgehobenen Text in einer separaten Datei zu speichern?

A: Ja, Sie können den extrahierten hervorgehobenen Text in einer separaten Datei speichern oder ihn zur weiteren Verarbeitung oder Analyse in einer Datenstruktur speichern.
