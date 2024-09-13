---
title: Ondertekenen met smartcard met behulp van handtekeningveld
linktitle: Ondertekenen met smartcard met behulp van handtekeningveld
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u PDF's veilig kunt ondertekenen met een smartcard met Aspose.PDF voor .NET. Volg onze stapsgewijze handleiding voor eenvoudige implementatie.
type: docs
weight: 120
url: /nl/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
## Invoering

In de digitale wereld van vandaag is het beveiligen van documenten belangrijker dan ooit. Of u nu een ontwikkelaar, een bedrijfseigenaar of gewoon iemand bent die gevoelige informatie verwerkt, weten hoe u PDF's elektronisch ondertekent, kan u tijd besparen en ervoor zorgen dat uw documenten worden geauthenticeerd. In deze gids leiden we u door het proces van het ondertekenen van een PDF met een smartcard en een handtekeningveld met Aspose.PDF voor .NET. 

## Vereisten

Voordat we in de details van het ondertekeningsproces duiken, zorgen we ervoor dat u alles hebt wat u nodig hebt om te beginnen. Hier is een checklist met vereisten:

1. Aspose.PDF voor .NET: Zorg ervoor dat u de Aspose.PDF-bibliotheek in uw .NET-omgeving hebt geïnstalleerd. U kunt deze downloaden van de[plaats](https://releases.aspose.com/pdf/net/).

2. Visual Studio: U hebt een IDE nodig om uw .NET-code te schrijven en uit te voeren. Visual Studio Community Edition is een geweldige gratis optie.

3. Een smartcard: Dit is essentieel voor het ondertekenen van uw PDF. Zorg ervoor dat u een smartcardlezer en de benodigde certificaten op uw machine hebt geïnstalleerd.

4. Basiskennis van C#: Kennis van C#-programmering helpt u de codefragmenten die we gaan gebruiken te begrijpen.

5. Voorbeeld PDF-document: Zorg dat u een voorbeeld PDF-document gereed hebt om te testen. U kunt een lege PDF maken of een bestaande gebruiken.

## Pakketten importeren

Voordat we beginnen met coderen, importeren we de benodigde pakketten. U moet de volgende namespaces opnemen in uw C#-bestand:

```csharp
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Via deze naamruimten krijgt u toegang tot de klassen en methoden die nodig zijn voor het werken met PDF's en het verwerken van digitale handtekeningen.

## Stapsgewijze handleiding voor het ondertekenen van een PDF met een smartcard

Nu we onze vereisten op een rijtje hebben, gaan we het ondertekeningsproces opsplitsen in beheersbare stappen. We gaan elke stap gedetailleerd doornemen, zodat u weet wat er onder de motorkap gebeurt.

### Stap 1: Stel uw documentenmap in

Wat u moet doen: Definieer het pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Uitleg: Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het werkelijke pad waar uw PDF-bestanden zich bevinden. Dit is waar we de lege PDF zullen lezen en het ondertekende document zullen opslaan.

### Stap 2: Kopieer de lege PDF

Wat u moet doen: Maak een kopie van uw lege PDF om mee te werken.

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
```

 Uitleg: Deze regel kopieert de`blank.pdf`bestand naar een nieuw bestand met de naam`externalSignature1.pdf` . De`true` parameter staat overschrijven toe als het bestand al bestaat.

### Stap 3: Open het PDF-document

Wat u moet doen: Open de gekopieerde PDF om te lezen en schrijven.

```csharp
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
    using (Document doc = new Document(fs))
    {
        // Verdere stappen zullen hier plaatsvinden
    }
}
```

 Uitleg: Wij gebruiken een`FileStream` om ons PDF-bestand te openen. De`Document` klasse van Aspose.PDF stelt ons in staat om de PDF-inhoud te manipuleren.

### Stap 4: Maak een handtekeningveld

Wat u moet doen: Definieer een handtekeningveld in de PDF waar de handtekening moet worden geplaatst.

```csharp
SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
```

 Uitleg: Hier maken we een`SignatureField` op de tweede pagina (pagina-index begint bij 1) van de PDF. De`Rectangle` definieert de positie en grootte van het handtekeningveld.

### Stap 5: Toegang tot de Smart Card Certificate Store

Wat u moet doen: Open het certificaatarchief om uw smartcardcertificaat te selecteren.

```csharp
X509Store store = new X509Store(StoreLocation.CurrentUser);
store.Open(OpenFlags.ReadOnly);
```

Uitleg: We benaderen de certificaatopslag voor de huidige gebruiker. Dit is waar uw smartcardcertificaten worden opgeslagen.

### Stap 6: Selecteer het certificaat

Wat u moet doen: Vraag de gebruiker om een certificaat uit de winkel te selecteren.

```csharp
X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
```

Uitleg: Deze regel opent een dialoogvenster waarin u een certificaat kunt selecteren. U kunt het certificaat kiezen dat aan uw smartcard is gekoppeld.

### Stap 7: Een externe handtekening maken

 Wat te doen: Maak een instantie van`ExternalSignature` met behulp van het geselecteerde certificaat.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
{
    Authority = "Me",
    Reason = "Reason",
    ContactInfo = "Contact"
};
```

 Uitleg: We initialiseren de`ExternalSignature` met het geselecteerde certificaat. U kunt ook de autoriteit, reden voor ondertekening en contactgegevens instellen.

### Stap 8: Voeg het handtekeningveld toe aan het document

Wat u moet doen: Voeg het handtekeningveld toe aan het document.

```csharp
field1.PartialName = "sig1";
doc.Form.Add(field1, 1);
```

Uitleg: We geven het handtekeningveld een naam en voegen het toe aan de eerste pagina van het document. Dit bereidt de PDF voor op ondertekening.

### Stap 9: Onderteken het document

Wat u moet doen: Gebruik de externe handtekening om de PDF te ondertekenen.

```csharp
field1.Sign(externalSignature);
doc.Save();
```

Uitleg: Deze regel ondertekent het document met de externe handtekening en slaat de wijzigingen op in de PDF. Uw document is nu ondertekend!

### Stap 10: Controleer de handtekening

Wat u moet doen: Controleer of de handtekening geldig is.

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
    for (int index = 0; index <= sigNames.Count - 1; index++)
    {
        if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
        {
            throw new ApplicationException("Not verified");
        }
    }
}
```

Uitleg: We maken een instantie van`PdfFileSignature` om de handtekeningen in het document te verifiëren. Als de handtekening niet geldig is, wordt er een uitzondering gegenereerd.

## Conclusie

Gefeliciteerd! U hebt zojuist geleerd hoe u een PDF-document ondertekent met een smartcard en een handtekeningveld met Aspose.PDF voor .NET. Dit proces beveiligt niet alleen uw documenten, maar zorgt ook voor authenticiteit, waardoor het een essentiële vaardigheid is in het digitale landschap van vandaag. Of u nu contracten, facturen of andere belangrijke documenten ondertekent, weten hoe u digitale handtekeningen implementeert, kan u tijd besparen en gemoedsrust bieden.

## Veelgestelde vragen

### Wat is Aspose.PDF voor .NET?
Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars PDF-documenten in .NET-toepassingen kunnen maken, bewerken en converteren.

### Heb ik een smartcard nodig om PDF's te ondertekenen?
Ja, voor het veilig ondertekenen van PDF's met een digitaal certificaat is een smartcard vereist.

### Kan ik Aspose.PDF gratis gebruiken?
 Aspose.PDF biedt een gratis proefversie aan, die u kunt downloaden[hier](https://releases.aspose.com/).

### Hoe kan ik een ondertekend PDF-bestand verifiëren?
 U kunt de`PdfFileSignature` klasse in Aspose.PDF om de handtekeningen in uw PDF-document te verifiëren.

### Waar kan ik meer documentatie over Aspose.PDF vinden?
 U kunt de[Aspose.PDF-documentatie](https://reference.aspose.com/pdf/net/) voor meer details en voorbeelden.