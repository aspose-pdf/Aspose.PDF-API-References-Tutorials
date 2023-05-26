---
title: Hervorgehobenen Text extrahieren
linktitle: Hervorgehobenen Text extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie hervorgehobenen Text mit Aspose.PDF für .NET extrahieren.
type: docs
weight: 60
url: /de/net/annotations/extracthighlightedtext/
---
Um hervorgehobenen Text aus einem PDF-Dokument zu extrahieren, können Sie die Aspose.PDF für .NET-API verwenden. Diese API bietet eine einfache Möglichkeit, den gesamten Text abzurufen, der in einem Dokument hervorgehoben wurde.

## Schritt 1: Laden Sie das PDF-Dokument

 Der erste Schritt beim Extrahieren von hervorgehobenem Text aus einem PDF-Dokument besteht darin, das Dokument mithilfe der Aspose.PDF für .NET-API zu laden. Sie können dies tun, indem Sie eine neue Instanz von erstellen`Document` Klasse und Übergabe des Pfads zum PDF-Dokument als Parameter. 

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

