---
title: Paginanummer in koptekst-voettekst met zwevend vak
linktitle: Paginanummer in koptekst-voettekst met zwevend vak
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u het paginanummer kunt toevoegen aan de kop- en voettekst van een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 150
url: /nl/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
In deze zelfstudie begeleiden we u stap voor stap bij het toevoegen van een paginanummer in de kop- en voettekst van een PDF-document met behulp van FloatingBox met Aspose.PDF voor .NET. We zullen de meegeleverde C#-broncode gebruiken om een PDF-document te maken, een pagina toe te voegen, een FloatingBox te maken, de positie ervan in te stellen en het paginanummer eraan toe te voegen, en vervolgens het gewijzigde PDF-document op te slaan.

## Stap 1: De omgeving instellen

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET gedownload en waarnaar wordt verwezen in uw project.

## Stap 2: Het PDF-document maken en een pagina toevoegen

De eerste stap is het maken van een exemplaar van het PDF-document en het toevoegen van een pagina eraan. Hier is hoe:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantieer het PDF-document
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Voeg een pagina toe aan het PDF-document
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waar u het PDF-document wilt opslaan.

## Stap 3: De FloatingBox aanmaken en het paginanummer toevoegen

Nu de pagina aan het PDF-document is toegevoegd, kunnen we een FloatingBox maken, de positie ervan instellen en er het paginanummer aan toevoegen. Hier is hoe:

```csharp
// Maak een FloatingBox met een breedte van 140 en een hoogte van 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Stel de linkerpositie van de alinea in
box1. Left = 2;

// Stel de bovenste positie van de alinea in
box1. Top = 10;

// Voeg het paginanummer toe aan de FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Voeg de FloatingBox toe aan de pagina
page.Paragraphs.Add(box1);
```

De bovenstaande code maakt een FloatingBox met een breedte van 140 en een hoogte van 80. Vervolgens stellen we de positie in door de linker- en bovenste waarden op te geven. Ten slotte voegen we het paginanummer toe aan de FloatingBox met behulp van een tekstfragment dat de syntaxis "($p/ $P )" bevat, die zal worden vervangen door het huidige paginanummer en het totale aantal pagina's.

## Stap 4: Het gewijzigde PDF-document opslaan

Zodra het paginanummer aan de kop- of voettekst is toegevoegd met behulp van de FloatingBox, kunnen we het gewijzigde PDF-document opslaan. Hier is hoe:

```csharp
// Sla het gewijzigde PDF-document op
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

De bovenstaande code slaat het bewerkte PDF-document op in de opgegeven map.

### Voorbeeldbroncode voor paginanummer in koptekst voettekst met zwevend vak met Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantie van documentinstantie
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Voeg een pagina toe aan het pdf-document
Aspose.Pdf.Page page = pdf.Pages.Add();

//Initialiseert een nieuw exemplaar van de klasse FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Zwevende waarde die de linkerpositie van de alinea aangeeft
box1.Left = 2;

// Zwevende waarde die de bovenste positie van de alinea aangeeft
box1.Top = 10;

// Voeg de macro's toe aan de alineacollectie van de FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Voeg een floatingBox toe aan de pagina
page.Paragraphs.Add(box1);

// Bewaar het document
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u een paginanummer kunt toevoegen aan de kop- en voettekst van een PDF-document met behulp van FloatingBox met Aspose.PDF voor .NET. U kunt nu uw kop- en voetteksten aanpassen door dynamische informatie toe te voegen, zoals het paginanummer.

### Veelgestelde vragen

#### Vraag: Wat is een FloatingBox en hoe wordt deze gebruikt om paginanummers toe te voegen aan de kop- of voettekst van een PDF-document?

A: Een FloatingBox is een veelzijdig lay-outelement in Aspose.PDF dat verschillende inhoud kan bevatten, inclusief tekst en afbeeldingen. In deze zelfstudie wordt het gebruikt om een container voor het paginanummer te maken, zodat u het huidige paginanummer en het totale aantal pagina's dynamisch in de kop- of voettekst kunt invoegen.

#### Vraag: Hoe kan de meegeleverde C#-broncode paginanummers toevoegen met behulp van een FloatingBox?

A: Het codefragment laat zien hoe u een PDF-document kunt maken, een pagina kunt toevoegen, een FloatingBox kunt maken, de positie binnen de pagina kunt instellen en het paginanummer kunt invoegen met behulp van een TextFragment. De syntaxis "($p/ $P )" in het tekstfragment wordt vervangen door het huidige paginanummer en het totale aantal pagina's.

#### Vraag: Kan ik het uiterlijk en de opmaak van het toegevoegde paginanummer aanpassen met behulp van de FloatingBox?

A: Ja, u kunt het uiterlijk van het paginanummer aanpassen door de eigenschappen van het TextFragment in de FloatingBox te wijzigen. U kunt de lettergrootte, kleur, stijl, uitlijning en andere opmaakopties wijzigen.

#### Vraag: Is het mogelijk om op een vergelijkbare manier verschillende dynamische elementen, zoals datum en tijd, aan de kop- of voettekst toe te voegen?

A: Absoluut, u kunt verschillende dynamische elementen toevoegen, zoals datum, tijd, documentmetagegevens of aangepaste tekst, door de TextFragment-inhoud in de FloatingBox te wijzigen. U kunt macro's gebruiken zoals "($p/ $P )" voor paginanummers of "($date)" voor de huidige datum.

#### Vraag: Hoe specificeer ik de positie van de FloatingBox binnen de kop- of voettekstsectie?
 A: De verstrekte code stelt de positie van de FloatingBox in met behulp van de`Left` En`Top` eigenschappen. U kunt deze waarden aanpassen om de FloatingBox naar wens binnen het kop- of voettekstgedeelte te positioneren.

#### Vraag: Kan ik een ander lettertype of een andere stijl gebruiken voor het paginanummer in de kop- of voettekst?

A: Ja, u kunt het lettertype, de stijl en andere opmaakeigenschappen van de paginanummertekst aanpassen door de TextFragment-eigenschappen in de FloatingBox te wijzigen.

#### Vraag: Wat gebeurt er als de inhoud in de FloatingBox de afmetingen overschrijdt?

A: Als de inhoud in de FloatingBox de afmetingen overschrijdt, kan deze worden afgesneden of kunnen er lay-outproblemen optreden. Zorg ervoor dat de afmetingen van de FloatingBox geschikt zijn voor de inhoud en overweeg om de pagina-indeling indien nodig aan te passen.

#### Vraag: Is het mogelijk om meerdere FloatingBoxes met verschillende inhoud toe te voegen aan de kop- of voettekst van dezelfde pagina?

A: Ja, u kunt meerdere FloatingBoxen met verschillende inhoud toevoegen aan de kop- of voettekst van dezelfde pagina door afzonderlijke FloatingBox-instanties te maken en deze toe te voegen aan de Paragraphs-verzameling van de pagina.

#### Vraag: Kan ik de FloatingBox-aanpak gebruiken om inhoud toe te voegen aan andere secties van het PDF-document, zoals de hoofdtekst of de marges?

A: Hoewel FloatingBoxes vaak worden gebruikt voor kop- en voetteksten, kunt u ze ook gebruiken om inhoud toe te voegen aan andere secties van het PDF-document, zoals de hoofdtekst of de marges, door ze dienovereenkomstig op de pagina te plaatsen.