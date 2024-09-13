---
title: Sign med smartkort med pdf-filsignatur
linktitle: Sign med smartkort med pdf-filsignatur
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du signerar PDF-filer med ett smartkort med Aspose.PDF för .NET. Följ denna steg-för-steg-guide för säkra digitala signaturer.
type: docs
weight: 110
url: /sv/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
## Introduktion

den digitala tidsåldern är det viktigare än någonsin att säkra dokument. Oavsett om det är ett kontrakt, ett avtal eller någon känslig information, är det av största vikt att se till att dokumentet är äkta och inte har manipulerats. Ange digitala signaturer! Idag ska vi fördjupa oss i hur man signerar en PDF-fil med ett smartkort med Aspose.PDF för .NET. Detta kraftfulla bibliotek låter utvecklare manipulera och skapa PDF-dokument effektivt, inklusive att lägga till säkra digitala signaturer. Så ta ditt smartkort och låt oss komma igång!

## Förutsättningar

Innan vi går in i det tråkiga med att signera en PDF-fil, låt oss se till att du har allt du behöver. Här är en checklista som hjälper dig att förbereda dig:

1.  Aspose.PDF för .NET: Se till att du har Aspose.PDF-biblioteket installerat. Du kan ladda ner den från[plats](https://releases.aspose.com/pdf/net/).
2. Visual Studio: En utvecklingsmiljö där du kan skriva och köra din .NET-kod.
3. Smartkort: Du behöver ett smartkort med ett giltigt digitalt certifikat installerat.
4. Grundläggande förståelse för C#: Bekantskap med C#-programmering kommer att vara fördelaktigt eftersom vi kommer att skriva kodavsnitt på detta språk.
5. PDF-dokument: Ett exempel på PDF-fil (som`blank.pdf`) för att testa vår signeringsprocess.

Med dessa förutsättningar på plats är du redo att dyka in i koden!

## Importera paket

Först till kvarn, låt oss importera de nödvändiga paketen. Du måste lägga till referenser till Aspose.PDF-biblioteket i ditt projekt. Så här kan du göra det:

1. Öppna Visual Studio.
2. Skapa ett nytt projekt eller öppna ett befintligt.
3.  Högerklicka på ditt projekt i Solution Explorer och välj`Manage NuGet Packages`.
4.  Leta efter`Aspose.PDF` och installera den senaste versionen.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nu när vi har de nödvändiga paketen importerade, låt oss dela upp koden steg för steg.

## Steg 1: Konfigurera ditt dokument

Det första steget i vår process är att skapa PDF-dokumentet vi vill signera. Så här kan du göra det:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
```
 I det här utdraget definierar vi sökvägen till vår dokumentkatalog och skapar en instans av`Document` klass med hjälp av en exempel-PDF-fil med namnet`blank.pdf` . Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen där din PDF-fil finns.

## Steg 2: Initiera PdfFileSignature

 Därefter initierar vi`PdfFileSignature` klass, som ansvarar för att hantera signeringsprocessen.

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
    pdfSign.BindPdf(doc);
```
Här skapar vi en instans av`PdfFileSignature`och binda den till vårt PDF-dokument. Detta förbereder dokumentet för signering.

## Steg 3: Få åtkomst till smartkortscertifikatet

Nu kommer den avgörande delen – att komma åt det digitala certifikatet som är lagrat på ditt smartkort. Så här kan vi göra det:

### Öppna certifikatarkivet

```csharp
System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
```
Vi öppnar certifikatarkivet som finns i den aktuella användarens profil. Detta ger oss tillgång till de certifikat som är installerade på din maskin, inklusive de på ditt smartkort.

### Välj certifikatet

```csharp
System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel =
    System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(
        store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
```
Denna kod uppmanar användaren att välja ett certifikat från samlingen. Användargränssnittet kommer att visa alla tillgängliga certifikat, så att du kan välja det som är kopplat till ditt smartkort.

## Steg 4: Skapa den externa signaturen

När du har valt ditt certifikat är nästa steg att skapa en extern signatur med det valda certifikatet.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
```
Här skapar vi en instans av`ExternalSignature` med det valda certifikatet. Detta objekt kommer att användas för att signera PDF-dokumentet.

## Steg 5: Ställ in signaturutseende

Låt oss nu ställa in utseendet på vår signatur. Det är här du kan anpassa hur din signatur ser ut på dokumentet.

```csharp
pdfSign.SignatureAppearance = dataDir + "demo.png";
```
 I det här utdraget anger vi signaturens utseende genom att tillhandahålla sökvägen till en bildfil (som en logotyp eller en signaturgrafik). Se till att byta ut`"demo.png"` med den faktiska bilden du vill använda.

## Steg 6: Signera PDF-filen

När allt är klart är det dags att signera PDF-dokumentet!

```csharp
pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
pdfSign.Save(dataDir + "externalSignature2.pdf");
```
 det här steget kallar vi`Sign` metod på vår`pdfSign` objekt. Så här betyder varje parameter:
- `1`: Sidnumret där signaturen kommer att visas.
- `"Reason"`: Skälet till att underteckna dokumentet.
- `"Contact"`: Kontaktuppgifter till undertecknaren.
- `"Location"`: Undertecknarens plats.
- `true`: Indikerar om en synlig signatur ska skapas.
- `new System.Drawing.Rectangle(100, 100, 200, 200)`: Signaturens placering och storlek på PDF:en.
- `externalSignature`: Signaturobjektet vi skapade tidigare.

 Slutligen sparar vi det signerade dokumentet som`externalSignature2.pdf`.

## Steg 7: Verifiera signaturen

Efter att ha undertecknat dokumentet är det viktigt att verifiera att signaturen är giltig. Så här gör du det:

### Initiera verifieringsprocessen

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
```
 Vi skapar en ny instans av`PdfFileSignature` för det undertecknade dokumentet. Vi hämtar sedan namnen på alla signaturer som finns i dokumentet.

### Kontrollera signaturens giltighet

```csharp
for (int index = 0; index <= sigNames.Count - 1; index++)
{
    if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
    {
        throw new ApplicationException("Not verified");
    }
}
```
Vi går igenom varje signaturnamn och verifierar dess giltighet. Om någon signatur misslyckas med verifieringen görs ett undantag, vilket indikerar att signaturen inte är giltig.

## Slutsats

Och där har du det! Du har framgångsrikt signerat ett PDF-dokument med ett smartkort med Aspose.PDF för .NET. Denna process säkrar inte bara ditt dokument utan lägger också till ett lager av autenticitet som är avgörande i dagens digitala värld. Oavsett om du har att göra med kontrakt, juridiska dokument eller annan känslig information, är det en värdefull färdighet att veta hur man implementerar digitala signaturer. 

## FAQ's

### Vad är Aspose.PDF för .NET?
Aspose.PDF för .NET är ett kraftfullt bibliotek som låter utvecklare skapa, manipulera och konvertera PDF-dokument i .NET-applikationer.

### Behöver jag ett smartkort för att signera PDF-filer?
Även om ett smartkort inte är obligatoriskt, rekommenderas det starkt för säkra digitala signaturer, eftersom det ger ett extra lager av säkerhet.

### Kan jag använda vilken PDF-fil som helst för att signera?
Ja, du kan använda vilken PDF-fil som helst, men se till att den inte är lösenordsskyddad. Om det är det måste du låsa upp det först.

### Vad händer om jag inte har ett digitalt certifikat?
Du kan skaffa ett digitalt certifikat från en betrodd certifikatutfärdare (CA) eller använda ett självsignerat certifikat för teständamål.

### Finns det en testversion av Aspose.PDF tillgänglig?
 Ja, du kan ladda ner en gratis testversion från[Aspose hemsida](https://releases.aspose.com/).