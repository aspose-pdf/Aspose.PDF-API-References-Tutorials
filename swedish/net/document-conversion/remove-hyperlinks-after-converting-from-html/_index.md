---
title: Ta bort hyperlänkar efter konvertering från HTML
linktitle: Ta bort hyperlänkar efter konvertering från HTML
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att ta bort hyperlänkar efter att ha konverterat HTML till PDF med Aspose.PDF för .NET.
type: docs
weight: 250
url: /sv/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---

den här handledningen går vi igenom processen för att ta bort hyperlänkar från en PDF-fil som genererats från en HTML-fil med Aspose.PDF för .NET. Hyperlänkar är klickbara länkar som kan omdirigera till andra sidor eller webbplatser. Genom att följa stegen nedan kommer du att kunna ta bort hyperlänkar från den resulterande PDF-filen.

## Förutsättningar
Innan du börjar, se till att du uppfyller följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat på ditt system.
- En utvecklingsmiljö som Visual Studio.

## Steg 1: Laddar HTML-fil och tar bort hyperlänkar
I det här steget kommer vi att ladda HTML-filen och ta bort hyperlänkarna från det resulterande PDF-dokumentet. Använd följande kod:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda HTML-filen med HTML-laddningsalternativen
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Bläddra bland kommentarerna på första sidan i dokumentet
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Kontrollera om anteckningen är en länk
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Kontrollera om åtgärden är av typen GoToURIAction
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Använd en textfragmentabsorbator för att hitta matchande textfragment
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Gå igenom matchande textfragment och ta bort attribut från hyperlänkar
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Ta bort anteckningen från sidan
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din HTML-fil finns.

## Steg 2: Spara den resulterande PDF-filen
Slutligen kommer vi att spara den resulterande PDF-filen utan hyperlänkarna. Använd följande kod:

```csharp
// Spara den resulterande PDF-filen
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Koden ovan sparar den resulterande PDF-filen med filnamnet`"RemoveHyperlinksFromText_out.pdf"`.

### Exempel på källkod för Ta bort hyperlänkar efter konvertering från HTML med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
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

## Slutsats
I den här handledningen täckte vi steg-för-steg-processen för att ta bort hyperlänkar från en PDF-fil som genererats från en HTML-fil med Aspose.PDF för .NET. Genom att följa instruktionerna som beskrivs ovan kommer du att kunna ta bort hyperlänkar från den resulterande PDF-filen.