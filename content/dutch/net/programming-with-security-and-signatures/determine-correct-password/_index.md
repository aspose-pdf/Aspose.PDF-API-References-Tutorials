---
title: Bepaal het juiste wachtwoord in een PDF-bestand
linktitle: Bepaal het juiste wachtwoord in een PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u het juiste wachtwoord in een PDF-bestand kunt bepalen met Aspose.PDF voor .NET.
type: docs
weight: 30
url: /nl/net/programming-with-security-and-signatures/determine-correct-password/
---
In deze tutorial leiden we u door het proces van het bepalen van het juiste wachtwoord in een PDF-bestand met behulp van Aspose.PDF voor .NET. Met deze functie kunt u controleren of een PDF-bestand met een wachtwoord is beveiligd en het juiste wachtwoord vinden in een vooraf gedefinieerde lijst.

## Stap 1: Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Basiskennis van de programmeertaal C#
- Visual Studio op uw machine installeren
- Aspose.PDF-bibliotheek voor .NET geïnstalleerd

## Stap 2: Omgeving instellen

Om te beginnen volgt u deze stappen om uw ontwikkelomgeving in te stellen:

1. Open Visual Studio en maak een nieuw C#-project.
2. Importeer de vereiste naamruimten in uw codebestand:

```csharp
using Aspose.Pdf;
```

## Stap 3: Bron-PDF-bestand laden

De eerste stap is het uploaden van het PDF-bronbestand dat u wilt verifiëren. In dit voorbeeld gaan we ervan uit dat u een PDF-bestand met de naam "IsPasswordProtected.pdf" in de opgegeven directory hebt.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

Zorg ervoor dat u de tijdelijke aanduidingen vervangt door de daadwerkelijke locaties van uw PDF-bestand.

## Stap 4: Bepaal de bron-PDF-codering

 Nadat u het bron-PDF-bestand hebt geüpload, kunt u bepalen of het is gecodeerd met behulp van de`IsEncrypted` methode van de`PdfFileInfo` voorwerp.

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

Deze verklaring geeft aan of het PDF-bestand met een wachtwoord is beveiligd of niet.

## Stap 5: Het juiste wachtwoord vinden

Vervolgens zoeken we naar het juiste wachtwoord met behulp van een vooraf gedefinieerde lijst met wachtwoorden. We doorlopen elk wachtwoord in de lijst en proberen het PDF-document met dat wachtwoord te laden.

```csharp
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
try
{
Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
if (doc.Pages.Count > 0)
Console.WriteLine("The document contains " + doc.Pages.Count + " pages.");
}
catch (InvalidPasswordException)
{
Console.WriteLine("The password " + passwords[passwordcount] + " is not correct.");
}
}
```

Deze lus test elk woord van de pass uit de lijst. Als het wachtwoord correct is, wordt het aantal pagina's in het document weergegeven. Anders wordt een bericht weergegeven dat aangeeft dat het wachtwoord niet correct is.


### Voorbeeldbroncode voor Bepaal het juiste wachtwoord met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// Bron PDF-bestand laden
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
//Bepalen of de bron-PDF gecodeerd is
Console.WriteLine("File is password protected " + info.IsEncrypted);
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
	try
	{
		Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
		if (doc.Pages.Count > 0)
			Console.WriteLine("Number of Page in document are = " + doc.Pages.Count);
	}
	catch (InvalidPasswordException)
	{
		Console.WriteLine("Password = " + passwords[passwordcount] + "  is not correct");
	}
}
```

## Conclusie

Gefeliciteerd! U hebt met succes het juiste wachtwoord voor een PDF-bestand bepaald met Aspose.PDF voor .NET. Deze tutorial behandelde het stapsgewijze proces, van het verifiëren van bestandscodering tot het vinden van het juiste wachtwoord uit een vooraf gedefinieerde lijst. Nu kunt u deze functie gebruiken om het juiste wachtwoord van uw PDF-bestanden te controleren en te vinden.

### FAQ's voor het bepalen van het juiste wachtwoord in een PDF-bestand

#### V: Wat is het doel van deze tutorial?

A: Deze tutorial is bedoeld om u te begeleiden bij het bepalen van het juiste wachtwoord voor een PDF-bestand met Aspose.PDF voor .NET. Met deze functie kunt u controleren of een PDF-bestand met een wachtwoord is beveiligd en proberen het juiste wachtwoord te vinden in een vooraf gedefinieerde lijst.

#### V: Aan welke voorwaarden moet ik voldoen voordat ik kan beginnen?

A: Voordat u begint, moet u ervoor zorgen dat u een basiskennis hebt van de programmeertaal C#, dat Visual Studio op uw computer is geïnstalleerd en dat de Aspose.PDF-bibliotheek voor .NET is geïnstalleerd.

#### V: Hoe stel ik de ontwikkelomgeving in?

A: Volg de onderstaande stappen om uw ontwikkelomgeving in te stellen, waaronder het maken van een nieuw C#-project in Visual Studio en het importeren van de vereiste naamruimten.

#### V: Hoe kan ik bepalen of een PDF-bestand versleuteld is?

 A: Gebruik de`PdfFileInfo` klasse om het bron-PDF-bestand te binden. Gebruik vervolgens de`IsEncrypted`eigenschap om te bepalen of het PDF-bestand met een wachtwoord is beveiligd.

#### V: Hoe kan ik het juiste wachtwoord voor een PDF-bestand vinden?

A: Nadat u hebt vastgesteld dat het PDF-bestand is gecodeerd, kunt u proberen het juiste wachtwoord te vinden door een vooraf gedefinieerde lijst met wachtwoorden te gebruiken. De meegeleverde voorbeeldcode laat zien hoe u door de lijst kunt lopen, elk wachtwoord kunt proberen en kunt bepalen of het wachtwoord correct is.

#### V: Wat gebeurt er als het juiste wachtwoord is gevonden?

A: Als het juiste wachtwoord is gevonden, geeft de voorbeeldcode het aantal pagina's in het PDF-document weer.

#### V: Wat als het wachtwoord niet correct is?

 A: Als het wachtwoord niet correct is, zal de voorbeeldcode de`InvalidPasswordException` en een bericht weergeven dat aangeeft dat het wachtwoord niet correct is.

#### V: Kan ik een andere lijst met wachtwoorden gebruiken?

 A: Ja, u kunt de`passwords` array in de voorbeeldcode om de wachtwoorden op te nemen die u wilt testen.

#### V: Hoe weet ik of het wachtwoord succesvol is vastgesteld?

A: Als de voorbeeldcode het PDF-document met een wachtwoord succesvol laadt en het aantal pagina's weergeeft, betekent dit dat het juiste wachtwoord is bepaald.

#### V: Hoe kan ik de veiligheid van mijn wachtwoorden garanderen tijdens het testen?

A: Wees voorzichtig bij het gebruik van een vooraf gedefinieerde lijst met wachtwoorden en vermijd het gebruik van gevoelige of vertrouwelijke wachtwoorden voor testdoeleinden. Verwijder of wijzig bovendien de testcode voordat u uw applicatie implementeert.