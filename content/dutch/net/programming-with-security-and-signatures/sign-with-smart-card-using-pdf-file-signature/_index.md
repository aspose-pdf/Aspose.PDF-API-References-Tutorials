---
title: Ondertekenen met smartcard met behulp van PDF-bestandshandtekening
linktitle: Ondertekenen met smartcard met behulp van PDF-bestandshandtekening
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u PDF-bestanden ondertekent met een smartcard met Aspose.PDF voor .NET. Volg deze stapsgewijze handleiding voor veilige digitale handtekeningen.
type: docs
weight: 110
url: /nl/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
## Invoering

In het digitale tijdperk is het beveiligen van documenten belangrijker dan ooit. Of het nu gaat om een contract, een overeenkomst of gevoelige informatie, het is van het grootste belang om ervoor te zorgen dat het document authentiek is en niet is gemanipuleerd. Digitale handtekeningen zijn in aantocht! Vandaag duiken we in hoe je een PDF-bestand ondertekent met een smartcard met Aspose.PDF voor .NET. Met deze krachtige bibliotheek kunnen ontwikkelaars PDF-documenten efficiënt bewerken en maken, inclusief het toevoegen van veilige digitale handtekeningen. Dus pak je smartcard en laten we beginnen!

## Vereisten

Voordat we in de details duiken van het ondertekenen van een PDF-bestand, zorgen we ervoor dat je alles hebt wat je nodig hebt. Hier is een checklist om je te helpen voorbereiden:

1.  Aspose.PDF voor .NET: Zorg ervoor dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd. U kunt deze downloaden van de[plaats](https://releases.aspose.com/pdf/net/).
2. Visual Studio: een ontwikkelomgeving waarin u uw .NET-code kunt schrijven en uitvoeren.
3. Smartcard: U hebt een smartcard nodig met een geldig digitaal certificaat.
4. Basiskennis van C#: Kennis van C#-programmering is nuttig omdat we codefragmenten in deze taal gaan schrijven.
5. PDF-document: een voorbeeld-PDF-bestand (zoals`blank.pdf`) om ons ondertekeningsproces te testen.

Nu u aan deze vereisten voldoet, bent u klaar om aan de slag te gaan met coderen!

## Pakketten importeren

Laten we eerst de benodigde pakketten importeren. U moet referenties toevoegen aan de Aspose.PDF-bibliotheek in uw project. Dit is hoe u dat kunt doen:

1. Open Visual Studio.
2. Maak een nieuw project of open een bestaand project.
3.  Klik met de rechtermuisknop op uw project in de Solution Explorer en selecteer`Manage NuGet Packages`.
4.  Zoeken naar`Aspose.PDF` en installeer de nieuwste versie.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nu we de benodigde pakketten hebben geïmporteerd, gaan we de code stap voor stap uitleggen.

## Stap 1: Stel uw document in

De eerste stap in ons proces is het opzetten van het PDF-document dat we willen ondertekenen. Dit is hoe u dat kunt doen:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
```
 In dit fragment definiëren we het pad naar onze documentenmap en maken we een exemplaar van de`Document` klasse met behulp van een voorbeeld-PDF-bestand met de naam`blank.pdf` Zorg ervoor dat u deze vervangt`"YOUR DOCUMENTS DIRECTORY"` met het werkelijke pad waar uw PDF zich bevindt.

## Stap 2: Initialiseer PdfFileSignature

 Vervolgens initialiseren we de`PdfFileSignature` klasse, die verantwoordelijk is voor het verwerken van het ondertekeningsproces.

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
    pdfSign.BindPdf(doc);
```
Hier maken we een instantie van`PdfFileSignature`en bind het aan ons PDF-document. Dit bereidt het document voor op ondertekening.

## Stap 3: Toegang tot het smartcardcertificaat

Nu komt het cruciale deel: toegang krijgen tot het digitale certificaat dat op uw smartcard is opgeslagen. Dit is hoe we dat kunnen doen:

### Open de certificaatopslag

```csharp
System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
```
We openen de certificaatwinkel die zich in het profiel van de huidige gebruiker bevindt. Dit geeft ons toegang tot de certificaten die op uw machine zijn geïnstalleerd, inclusief die op uw smartcard.

### Selecteer het certificaat

```csharp
System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel =
    System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(
        store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
```
Deze code vraagt de gebruiker om een certificaat uit de collectie te selecteren. De gebruikersinterface toont alle beschikbare certificaten, zodat u degene kunt kiezen die aan uw smartcard is gekoppeld.

## Stap 4: De externe handtekening maken

Nadat u uw certificaat hebt geselecteerd, is de volgende stap het maken van een externe handtekening met behulp van het geselecteerde certificaat.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
```
Hier maken we een instantie van`ExternalSignature` met behulp van het geselecteerde certificaat. Dit object wordt gebruikt om het PDF-document te ondertekenen.

## Stap 5: Stel het uiterlijk van de handtekening in

Laten we nu het uiterlijk van onze handtekening instellen. Hier kunt u aanpassen hoe uw handtekening eruitziet op het document.

```csharp
pdfSign.SignatureAppearance = dataDir + "demo.png";
```
 In dit fragment specificeren we het uiterlijk van de handtekening door het pad naar een afbeeldingsbestand (zoals een logo of een handtekeningafbeelding) op te geven. Zorg ervoor dat u`"demo.png"` met de afbeelding die u daadwerkelijk wilt gebruiken.

## Stap 6: Onderteken de PDF

Zodra alles is ingesteld, is het tijd om het PDF-document te ondertekenen!

```csharp
pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
pdfSign.Save(dataDir + "externalSignature2.pdf");
```
In deze stap noemen we de`Sign` methode op onze`pdfSign` object. Dit is wat elke parameter betekent:
- `1`: Het paginanummer waarop de handtekening zal verschijnen.
- `"Reason"`: De reden voor het ondertekenen van het document.
- `"Contact"`: Contactgegevens van de ondertekenaar.
- `"Location"`: De locatie van de ondertekenaar.
- `true`: Geeft aan of er een zichtbare handtekening moet worden gemaakt.
- `new System.Drawing.Rectangle(100, 100, 200, 200)`: De positie en grootte van de handtekening op het PDF-bestand.
- `externalSignature`: Het handtekeningobject dat we eerder hebben gemaakt.

 Ten slotte slaan we het ondertekende document op als`externalSignature2.pdf`.

## Stap 7: Controleer de handtekening

Nadat u het document hebt ondertekend, is het essentieel om te verifiëren of de handtekening geldig is. Dit is hoe u dat doet:

### Initialiseer verificatieproces

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
```
 We maken een nieuw exemplaar van`PdfFileSignature` voor het ondertekende document. Vervolgens halen we de namen op van alle handtekeningen die in het document aanwezig zijn.

### Controleer de geldigheid van de handtekening

```csharp
for (int index = 0; index <= sigNames.Count - 1; index++)
{
    if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
    {
        throw new ApplicationException("Not verified");
    }
}
```
We doorlopen elke handtekeningnaam en verifiëren de geldigheid ervan. Als een handtekening de verificatie niet doorstaat, wordt er een uitzondering gegenereerd, die aangeeft dat de handtekening niet geldig is.

## Conclusie

En daar heb je het! Je hebt succesvol een PDF-document ondertekend met een smartcard met Aspose.PDF voor .NET. Dit proces beveiligt niet alleen je document, maar voegt ook een laag authenticiteit toe die cruciaal is in de digitale wereld van vandaag. Of je nu te maken hebt met contracten, juridische documenten of andere gevoelige informatie, weten hoe je digitale handtekeningen implementeert is een waardevolle vaardigheid. 

## Veelgestelde vragen

### Wat is Aspose.PDF voor .NET?
Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars PDF-documenten kunnen maken, bewerken en converteren in .NET-toepassingen.

### Heb ik een smartcard nodig om PDF's te ondertekenen?
Hoewel een smartcard niet verplicht is, wordt het wel sterk aanbevolen voor veilige digitale handtekeningen, omdat het een extra beveiligingslaag biedt.

### Kan ik elk PDF-bestand gebruiken om te ondertekenen?
Ja, u kunt elk PDF-bestand gebruiken, maar zorg ervoor dat het niet met een wachtwoord is beveiligd. Als dat wel zo is, moet u het eerst ontgrendelen.

### Wat als ik geen digitaal certificaat heb?
U kunt een digitaal certificaat verkrijgen bij een vertrouwde certificeringsinstantie (CA) of een zelfondertekend certificaat gebruiken voor testdoeleinden.

### Is er een proefversie van Aspose.PDF beschikbaar?
 Ja, u kunt een gratis proefversie downloaden van de[Aspose-website](https://releases.aspose.com/).