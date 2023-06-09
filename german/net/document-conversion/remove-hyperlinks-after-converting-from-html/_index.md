---
title: Entfernen Sie Hyperlinks nach der Konvertierung aus HTML
linktitle: Entfernen Sie Hyperlinks nach der Konvertierung aus HTML
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Entfernen von Hyperlinks nach der Konvertierung von HTML in PDF mit Aspose.PDF für .NET.
type: docs
weight: 250
url: /de/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---

In diesem Tutorial führen wir Sie durch den Prozess des Entfernens von Hyperlinks aus einer PDF-Datei, die mit Aspose.PDF für .NET aus einer HTML-Datei generiert wurde. Hyperlinks sind anklickbare Links, die auf andere Seiten oder Websites weiterleiten können. Wenn Sie die folgenden Schritte ausführen, können Sie Hyperlinks aus der resultierenden PDF-Datei entfernen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: HTML-Datei laden und Hyperlinks entfernen
In diesem Schritt laden wir die HTML-Datei und entfernen die Hyperlinks aus dem resultierenden PDF-Dokument. Verwenden Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie die HTML-Datei mit den HTML-Ladeoptionen
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Durchsuchen Sie die Anmerkungen der ersten Seite des Dokuments
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Überprüfen Sie, ob es sich bei der Anmerkung um einen Link handelt
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Überprüfen Sie, ob die Aktion vom Typ GoToURIAction ist
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Verwenden Sie einen Textfragment-Absorber, um passende Textfragmente zu finden
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Durchlaufen Sie passende Textfragmente und entfernen Sie Attribute aus Hyperlinks
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Entfernen Sie die Anmerkung von der Seite
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre HTML-Datei befindet.

## Schritt 2: Speichern der resultierenden PDF-Datei
Abschließend speichern wir die resultierende PDF-Datei ohne die Hyperlinks. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie die resultierende PDF-Datei
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Der obige Code speichert die resultierende PDF-Datei unter dem Dateinamen`"RemoveHyperlinksFromText_out.pdf"`.

### Beispielquellcode zum Entfernen von Hyperlinks nach der Konvertierung aus HTML mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess zum Entfernen von Hyperlinks aus einer PDF-Datei behandelt, die mit Aspose.PDF für .NET aus einer HTML-Datei generiert wurde. Wenn Sie die oben beschriebenen Anweisungen befolgen, können Sie Hyperlinks erfolgreich aus der resultierenden PDF-Datei entfernen.