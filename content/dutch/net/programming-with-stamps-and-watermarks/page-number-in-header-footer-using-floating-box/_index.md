---
title: Paginanummer in koptekst/voettekst met behulp van zwevende box
linktitle: Paginanummer in koptekst/voettekst met behulp van zwevende box
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u het paginanummer toevoegt aan de kop- en voettekst van een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 150
url: /nl/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
In deze tutorial laten we je stap voor stap zien hoe je een paginanummer toevoegt aan de header en footer van een PDF-document met behulp van FloatingBox met Aspose.PDF voor .NET. We gebruiken de meegeleverde C#-broncode om een PDF-document te maken, een pagina toe te voegen, een FloatingBox te maken, de positie ervan in te stellen en het paginanummer eraan toe te voegen, en vervolgens het gewijzigde PDF-document op te slaan.

## Stap 1: De omgeving instellen

Voordat u begint, moet u ervoor zorgen dat u het volgende bij de hand hebt:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET is gedownload en wordt in uw project gebruikt.

## Stap 2: Het PDF-document maken en een pagina toevoegen

De eerste stap is om een exemplaar van het PDF-document te maken en er een pagina aan toe te voegen. Dit doet u als volgt:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantieer het PDF-document
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Een pagina toevoegen aan het PDF-document
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waarin u het PDF-document wilt opslaan.

## Stap 3: De FloatingBox maken en het paginanummer toevoegen

Nu de pagina is toegevoegd aan het PDF-document, kunnen we een FloatingBox maken, de positie ervan instellen en het paginanummer eraan toevoegen. Dit doet u als volgt:

```csharp
// Maak een FloatingBox met een breedte van 140 en een hoogte van 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// De linkerpositie van de alinea instellen
box1. Left = 2;

// De bovenste positie van de alinea instellen
box1. Top = 10;

// Voeg het paginanummer toe aan de FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Voeg de FloatingBox toe aan de pagina
page.Paragraphs.Add(box1);
```

De bovenstaande code creëert een FloatingBox met een breedte van 140 en een hoogte van 80. Vervolgens stellen we de positie in door de linker- en bovenste waarden op te geven. Tot slot voegen we het paginanummer toe aan de FloatingBox met behulp van een TextFragment met de syntaxis "($p/ $P )" dat wordt vervangen door het huidige paginanummer en het totale aantal pagina's.

## Stap 4: Het gewijzigde PDF-document opslaan

Zodra het paginanummer is toegevoegd aan de header of footer met behulp van de FloatingBox, kunnen we het aangepaste PDF-document opslaan. Dit is hoe:

```csharp
// Sla het gewijzigde PDF-document op
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

De bovenstaande code slaat het bewerkte PDF-document op in de opgegeven map.

### Voorbeeldbroncode voor paginanummering in koptekst/voettekst met zwevend vak met Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantieer Document-instantie
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Voeg een pagina toe aan het pdf-document
Aspose.Pdf.Page page = pdf.Pages.Add();

// Initialiseert een nieuw exemplaar van de FloatingBox-klasse
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Vlotterwaarde die de linkerpositie van de alinea aangeeft
box1.Left = 2;

// Float-waarde die de bovenste positie van de alinea aangeeft
box1.Top = 10;

// Voeg de macro's toe aan de alineaverzameling van de FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Voeg een floatingBox toe aan de pagina
page.Paragraphs.Add(box1);

// Sla het document op
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u een paginanummer toevoegt aan de kop- en voettekst van een PDF-document met behulp van FloatingBox met Aspose.PDF voor .NET. U kunt nu uw kop- en voetteksten aanpassen door dynamische informatie toe te voegen, zoals een paginanummer.

### Veelgestelde vragen

#### V: Wat is een FloatingBox en hoe gebruik je deze om paginanummers toe te voegen aan de kop- of voettekst van een PDF-document?

A: Een FloatingBox is een veelzijdig lay-outelement in Aspose.PDF dat verschillende content kan bevatten, waaronder tekst en afbeeldingen. In deze tutorial wordt het gebruikt om een container voor het paginanummer te maken, zodat u dynamisch het huidige paginanummer en het totale aantal pagina's in de kop- of voettekst kunt invoegen.

#### V: Hoe wordt met de meegeleverde C#-broncode het toevoegen van paginanummers met behulp van een FloatingBox gerealiseerd?

A: Het codefragment laat zien hoe u een PDF-document maakt, een pagina toevoegt, een FloatingBox maakt, de positie ervan op de pagina instelt en het paginanummer invoegt met behulp van een TextFragment. De syntaxis "($p/ $P )" in het TextFragment wordt vervangen door het huidige paginanummer en het totale aantal pagina's.

#### V: Kan ik het uiterlijk en de opmaak van het paginanummer dat ik met behulp van de FloatingBox heb toegevoegd, aanpassen?

A: Ja, u kunt het uiterlijk van het paginanummer aanpassen door de eigenschappen van het TextFragment in de FloatingBox te wijzigen. U kunt de lettergrootte, kleur, stijl, uitlijning en andere opmaakopties wijzigen.

#### V: Is het mogelijk om verschillende dynamische elementen, zoals datum en tijd, op een vergelijkbare manier toe te voegen aan de kop- of voettekst?

A: Absoluut, u kunt verschillende dynamische elementen toevoegen zoals datum, tijd, documentmetadata of aangepaste tekst door de TextFragment-inhoud in de FloatingBox te wijzigen. U kunt macro's gebruiken zoals "($p/ $P )" voor paginanummers of "($date)" voor de huidige datum.

#### V: Hoe geef ik de positie van de FloatingBox binnen de header- of footersectie op?
 A: De meegeleverde code stelt de positie van de FloatingBox in met behulp van de`Left` En`Top` eigenschappen. U kunt deze waarden aanpassen om de FloatingBox naar wens te positioneren binnen de header- of footersectie.

#### V: Kan ik een ander lettertype of een andere stijl gebruiken voor het paginanummer in de kop- of voettekst?

A: Ja, u kunt het lettertype, de stijl en andere opmaakeigenschappen van de paginanummertekst aanpassen door de TextFragment-eigenschappen in de FloatingBox te wijzigen.

#### V: Wat gebeurt er als de inhoud van de FloatingBox de afmetingen overschrijdt?

A: Als de inhoud in de FloatingBox de afmetingen overschrijdt, kan deze worden afgesneden of kunnen er lay-outproblemen ontstaan. Zorg ervoor dat de afmetingen van de FloatingBox geschikt zijn voor de inhoud en overweeg om de pagina-indeling indien nodig aan te passen.

#### V: Is het mogelijk om meerdere FloatingBoxes met verschillende inhoud toe te voegen aan de kop- of voettekst van dezelfde pagina?

A: Ja, u kunt meerdere FloatingBoxes met verschillende inhoud toevoegen aan de kop- of voettekst van dezelfde pagina door afzonderlijke FloatingBox-instanties te maken en deze toe te voegen aan de Paragraphs-verzameling van de pagina.

#### V: Kan ik de FloatingBox-aanpak gebruiken om inhoud toe te voegen aan andere secties van het PDF-document, zoals de hoofdtekst of de marges?

A: Hoewel FloatingBoxes vaak worden gebruikt voor kop- en voetteksten, kunt u ze ook gebruiken om inhoud toe te voegen aan andere secties van het PDF-document, zoals de hoofdtekst of marges, door ze op de juiste manier op de pagina te positioneren.