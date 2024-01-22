---
title: Verwijder hyperlinks na het converteren van HTML
linktitle: Verwijder hyperlinks na het converteren van HTML
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het verwijderen van hyperlinks na het converteren van HTML naar PDF met Aspose.PDF voor .NET.
type: docs
weight: 250
url: /nl/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
In deze zelfstudie leiden we u door het proces van het verwijderen van hyperlinks uit een PDF-bestand dat is gegenereerd op basis van een HTML-bestand met Aspose.PDF voor .NET. Hyperlinks zijn klikbare links die kunnen doorverwijzen naar andere pagina's of websites. Door de onderstaande stappen te volgen, kunt u hyperlinks uit het resulterende PDF-bestand verwijderen.

## Vereisten
Zorg ervoor dat u aan de volgende vereisten voldoet voordat u begint:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF-bibliotheek voor .NET geïnstalleerd op uw systeem.
- Een ontwikkelomgeving zoals Visual Studio.

## Stap 1: HTML-bestand laden en hyperlinks verwijderen
Bij deze stap laden we het HTML-bestand en verwijderen we de hyperlinks uit het resulterende PDF-document. Gebruik de volgende code:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het HTML-bestand met behulp van de HTML-laadopties
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Blader door de annotaties op de eerste pagina van het document
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Controleer of de annotatie een link is
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Controleer of de actie van het type GoToURIAction is
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Gebruik een tekstfragmentabsorber om overeenkomende tekstfragmenten te vinden
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Blader door overeenkomende tekstfragmenten en verwijder attributen uit hyperlinks
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Verwijder de annotatie van de pagina
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 Zeker vervangen`"YOUR DOCUMENTS DIRECTORY"` met de daadwerkelijke map waar uw HTML-bestand zich bevindt.

## Stap 2: Het resulterende PDF-bestand opslaan
Ten slotte slaan we het resulterende PDF-bestand op zonder de hyperlinks. Gebruik de volgende code:

```csharp
// Sla het resulterende PDF-bestand op
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 De bovenstaande code slaat het resulterende PDF-bestand op met de bestandsnaam`"RemoveHyperlinksFromText_out.pdf"`.

### Voorbeeldbroncode voor het verwijderen van hyperlinks na het converteren van HTML met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
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

## Conclusie
In deze zelfstudie hebben we het stapsgewijze proces besproken van het verwijderen van hyperlinks uit een PDF-bestand dat is gegenereerd op basis van een HTML-bestand met Aspose.PDF voor .NET. Door de hierboven beschreven instructies te volgen, kunt u met succes hyperlinks uit het resulterende PDF-bestand verwijderen.

### Veelgestelde vragen

#### Vraag: Wat is Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars met PDF-documenten in C#-toepassingen kunnen werken. Het biedt een breed scala aan functionaliteiten, waaronder de mogelijkheid om HTML-bestanden naar PDF te converteren en PDF-inhoud te manipuleren.

#### Vraag: Waarom zou ik hyperlinks uit een PDF-bestand willen verwijderen?

A: Er zijn verschillende redenen om hyperlinks uit een PDF-bestand te verwijderen. U wilt bijvoorbeeld externe links verwijderen voor afdruk- of archiveringsdoeleinden of ervoor zorgen dat de PDF-inhoud niet via hyperlinks kan worden genavigeerd.

#### Vraag: Hoe kan ik een HTML-bestand laden en hyperlinks verwijderen met Aspose.PDF voor .NET?

 A: Om een HTML-bestand te laden en hyperlinks te verwijderen, kunt u Aspose.PDF voor .NET's gebruiken`HtmlLoadOptions` klas. Blader door de annotaties van de PDF-pagina's om linkannotaties te vinden en hun kenmerken te wijzigen.

#### Vraag: Kan ik de naam van het uitvoerbestand voor de resulterende PDF aanpassen?

A: Ja, u kunt de uitvoerbestandsnaam voor het resulterende PDF-bestand aanpassen door de code te wijzigen waarmee het PDF-document wordt opgeslagen. Wijzig eenvoudig de gewenste bestandsnaam in het`doc.Save()` methode.

#### Vraag: Is het mogelijk om hyperlinks selectief te verwijderen op basis van bepaalde criteria?

A: Ja, u kunt hyperlinks selectief verwijderen op basis van specifieke criteria. U kunt er bijvoorbeeld voor kiezen om alleen externe links of links die naar specifieke URL's verwijzen, te verwijderen.