---
title: Handtekeninggegevens extraheren
linktitle: Handtekeninggegevens extraheren
second_title: Aspose.PDF voor .NET API-referentie
description: Handtekeninginformatie extraheren met Aspose.PDF voor .NET.
type: docs
weight: 80
url: /nl/net/programming-with-security-and-signatures/extract-signature-info/
---
Het proces van het extraheren van handtekeninginformatie uit een PDF-document kan in verschillende scenario's behoorlijk nuttig zijn. Of u nu de authenticiteit van een ondertekend document wilt valideren of het certificaat wilt analyseren dat voor de handtekening wordt gebruikt, de Aspose.PDF voor .NET-bibliotheek biedt een handige oplossing. In deze zelfstudie begeleiden we u stapsgewijs door het proces voor het extraheren van handtekeninginformatie met behulp van de meegeleverde C#-broncode.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

1. Basiskennis van de programmeertaal C#.
2. Aspose.PDF voor .NET-bibliotheek geïnstalleerd op uw systeem.
3. Een geldig PDF-document met een of meer handtekeningvelden.

Laten we nu eens kijken naar de implementatiedetails.

## Stap 1: Importeren van de vereiste bibliotheken

 Om aan de slag te gaan, moet u de benodigde bibliotheken in uw C#-project importeren. In dit geval moeten we de`Aspose.Pdf` En`System.IO` naamruimten. Dit kunt u doen door de volgende code aan het begin van uw C#-bestand toe te voegen:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Stap 2: Het documentpad instellen

Vervolgens moet u het pad instellen naar het PDF-document waaruit u de handtekeninginformatie wilt extraheren. Vervangen`"YOUR DOCUMENTS DIRECTORY"` in het volgende codefragment met het daadwerkelijke pad naar uw document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Stap 3: Handtekeninginformatie extraheren

Laten we nu verder gaan met het hoofdgedeelte van de code, waar we de handtekeninginformatie uit het PDF-document extraheren. We doorlopen elk veld in het documentformulier en controleren of het een handtekeningveld is. Als er een handtekeningveld wordt gevonden, gaan we verder met het extraheren van het certificaat. Voeg het volgende codefragment toe:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Pak het certificaat uit
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## Stap 4: Het certificaat uitpakken

In deze stap halen we het certificaat uit het handtekeningveld en slaan het op als bestand. Het geëxtraheerde certificaat kan verder worden geanalyseerd of gebruikt voor validatiedoeleinden. Het onderstaande codefragment demonstreert het extractie- en opslagproces:

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## Stap 5

: Het certificaat opslaan

Ten slotte slaan we het uitgepakte certificaat op als bestand. In dit voorbeeld wordt het certificaat opgeslagen met de naam "input.cer" in de opgegeven map. U kunt de code aanpassen aan uw wensen. Hier is het codefragment voor het opslaan van het certificaat:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

Dat is het! U hebt met succes handtekeninginformatie geëxtraheerd met Aspose.PDF voor .NET. U kunt deze code gerust in uw eigen toepassingen integreren of naar wens aanpassen.

### Voorbeeldbroncode voor het extraheren van handtekeninginformatie met Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusie

In deze zelfstudie hebben we een stapsgewijze handleiding doorgenomen over het extraheren van handtekeninginformatie uit een PDF-document met behulp van de Aspose.PDF voor .NET-bibliotheek. We hebben het proces besproken van het importeren van de vereiste bibliotheken, het instellen van het documentpad, het extraheren van handtekeninginformatie, het extraheren van het certificaat en het opslaan ervan in een bestand. Door deze stappen te volgen, kunt u eenvoudig handtekeninggegevens ophalen en er indien nodig mee werken.

### Veelgestelde vragen

#### Vraag: Waarom zou ik handtekeninginformatie uit een PDF-document moeten halen?

A: Het extraheren van handtekeninginformatie uit een PDF-document is handig voor het valideren van de authenticiteit van een ondertekend document en het analyseren van het certificaat dat voor de handtekening wordt gebruikt. Dit proces helpt de integriteit van de ondertekende inhoud te garanderen en kan essentieel zijn voor juridische en veiligheidsdoeleinden.

#### Vraag: Wat is Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET is een bibliotheek waarmee ontwikkelaars met PDF-documenten kunnen werken in .NET-toepassingen. Het biedt een breed scala aan functies voor het programmatisch maken, wijzigen en gebruiken van PDF-bestanden.

#### Vraag: Wat zijn de vereisten voor het extraheren van handtekeninginformatie met Aspose.PDF voor .NET?

A: Om handtekeninginformatie te extraheren, hebt u basiskennis nodig van de programmeertaal C#, de Aspose.PDF voor .NET-bibliotheek die op uw systeem is geïnstalleerd en een geldig PDF-document met een of meer handtekeningvelden.

#### Vraag: Hoe importeer ik de vereiste bibliotheken voor het extractieproces?

A: U kunt de benodigde bibliotheken importeren door de`using` richtlijnen voor`Aspose.Pdf` En`System.IO` aan het begin van uw C#-bestand. Met deze richtlijnen kunt u de klassen en methoden gebruiken die nodig zijn voor het extraheren van handtekeninginformatie.

#### Vraag: Hoe specificeer ik het PDF-document voor het extraheren van handtekeninginformatie?

 A: U kunt het pad naar het PDF-document instellen door te vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad naar uw document in het opgegeven codefragment. Dit pad wordt gebruikt om het PDF-document te laden waaruit u handtekeninginformatie wilt extraheren.

#### Vraag: Wat is het proces voor het extraheren van handtekeninginformatie uit een PDF-document?

A: Het extractieproces omvat het doorlopen van de formuliervelden van het PDF-document, waarbij wordt gecontroleerd of elk veld een handtekeningveld is, en zo ja, het bijbehorende certificaat wordt geëxtraheerd. Het uitgepakte certificaat kan als bestand worden opgeslagen voor verdere analyse of validatie.

#### Vraag: Hoe wordt het certificaat geëxtraheerd uit een handtekeningveld?

A: Het certificaat wordt uit een handtekeningveld gehaald met behulp van de`ExtractCertificate()` methode aangeboden door de`SignatureField` klasse in Aspose.PDF voor .NET. Deze methode retourneert een stream met de certificaatgegevens.

#### Vraag: Hoe sla ik het uitgepakte certificaat op als bestand?

 A: U kunt het uitgepakte certificaat opslaan als een bestand door de certificaatstroom te lezen en de inhoud ervan naar een bestand te schrijven met behulp van de`FileStream` klas. De code in de zelfstudie demonstreert dit proces.

#### Vraag: Kan ik dit geëxtraheerde certificaat gebruiken voor handtekeningvalidatie?

A: Ja, het geëxtraheerde certificaat kan worden gebruikt voor handtekeningvalidatie. U kunt de details van het certificaat analyseren en de authenticiteit ervan verifiëren om de integriteit van het ondertekende document te garanderen.

#### Vraag: Hoe kan ik deze code in mijn eigen applicaties integreren?

A: U kunt de meegeleverde code integreren in uw eigen C#-applicaties door de stapsgewijze handleiding te volgen. Wijzig indien nodig de paden en bestandsnamen en neem de code op in uw bestaande projecten.

#### Vraag: Zijn er andere functies in Aspose.PDF voor .NET gerelateerd aan handtekeningbeheer?

A: Ja, Aspose.PDF voor .NET biedt een reeks functies voor het werken met digitale handtekeningen, waaronder het ondertekenen van documenten, het verifiëren van handtekeningen en het toevoegen van tijdstempelinformatie. U kunt de officiële documentatie raadplegen voor meer informatie over deze functies.

#### Vraag: Waar kan ik aanvullende bronnen vinden voor het gebruik van Aspose.PDF voor .NET?

 A: Voor meer informatie, tutorials en bronnen over het gebruik van Aspose.PDF voor .NET,[Aspose.PDF voor .NET](https://reference.aspose.com/pdf/net/).

#### Vraag: Is het mogelijk om handtekeningen uit gecodeerde PDF-documenten te halen?

A: De mogelijkheid om handtekeningen te extraheren uit gecodeerde PDF-documenten kan afhankelijk zijn van de coderingsinstellingen en machtigingen van het document. Mogelijk moet u ervoor zorgen dat u over de benodigde machtigingen beschikt om handtekeninginformatie te openen en te extraheren.

#### Vraag: Kan ik meerdere handtekeningen uit één enkel PDF-document halen?

A: Ja, u kunt de meegeleverde code wijzigen om alle handtekeningvelden in het PDF-document te doorlopen en handtekeninginformatie uit elk ervan te extraheren. Hiermee kunt u informatie extraheren over meerdere handtekeningen in het document.

#### Vraag: Wat zijn enkele praktische gebruiksscenario's voor het extraheren van handtekeninginformatie?

A: Enkele praktische gebruiksscenario's voor het extraheren van handtekeninginformatie zijn onder meer het valideren van de authenticiteit van digitaal ondertekende documenten, het analyseren van certificaatgegevens voor nalevingsdoeleinden en het bijhouden van een register van handtekeningen en ondertekenaars voor auditdoeleinden.

#### Vraag: Zijn er juridische overwegingen bij het extraheren van handtekeninginformatie?

A: Het extraheren van handtekeninginformatie kan juridische implicaties hebben, vooral bij het verwerken van juridisch bindende documenten. Zorg ervoor dat u voldoet aan de relevante regelgeving en wetten met betrekking tot elektronische handtekeningen en documentauthenticiteit in uw rechtsgebied.