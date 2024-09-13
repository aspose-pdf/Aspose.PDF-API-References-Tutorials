---
title: Ta bort hyperlänkar efter konvertering från HTML
linktitle: Ta bort hyperlänkar efter konvertering från HTML
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du tar bort hyperlänkar från HTML-dokument efter konvertering till PDF med Aspose.PDF för .NET i denna steg-för-steg-guide.
type: docs
weight: 250
url: /sv/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## Introduktion

I den digitala tidsåldern är det en vanlig uppgift att konvertera HTML-dokument till PDF. Men ibland kanske du vill ta bort hyperlänkar från den konverterade PDF-filen av olika anledningar, som att förbättra läsbarheten eller förhindra oönskad navigering. I den här handledningen kommer vi att utforska hur man uppnår detta med Aspose.PDF för .NET. 

## Förutsättningar

Innan du dyker in i koden, se till att du har följande förutsättningar:

1. Visual Studio: Se till att du har Visual Studio installerat på din dator. Detta kommer att vara din utvecklingsmiljö.
2.  Aspose.PDF för .NET: Du måste ha Aspose.PDF-biblioteket. Du kan ladda ner den från[här](https://releases.aspose.com/pdf/net/).
3. Grundläggande kunskaper om C#: Bekantskap med C#-programmering hjälper dig att förstå koden bättre.

## Importera paket

För att komma igång måste du importera nödvändiga paket i ditt C#-projekt. Så här kan du göra det:

1. Öppna ditt Visual Studio-projekt.
2. Högerklicka på ditt projekt i Solution Explorer och välj "Hantera NuGet-paket."
3.  Leta efter`Aspose.PDF` och installera den.

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

Nu när du har allt inställt, låt oss bryta ner processen för att ta bort hyperlänkar från en HTML-fil efter att ha konverterat den till PDF.

## Steg 1: Konfigurera dokumentkatalogen

Först och främst måste du ange sökvägen till din dokumentkatalog. Det är här din HTML-fil finns och där den utgående PDF-filen kommer att sparas.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen där din HTML-fil är lagrad.

## Steg 2: Ladda HTML-dokumentet

 Därefter kommer du att ladda HTML-dokumentet med hjälp av`Document` klass från Aspose.PDF. Den här klassen låter dig enkelt arbeta med PDF-dokument.

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

 Här laddar vi HTML-filen med namnet`SampleHtmlFile.html`. Se till att den här filen finns i din angivna katalog.

## Steg 3: Spara dokumentet i minnesström

Innan vi börjar bearbeta kommentarerna måste vi spara dokumentet i en minnesström. Detta steg är avgörande eftersom det förbereder dokumentet för ytterligare manipulation.

```csharp
doc.Save(new MemoryStream());
```

Den här raden sparar dokumentet i minnet, så att vi kan arbeta med det utan att skriva det till disk ännu.

## Steg 4: Iterera genom anteckningar

Nu ska vi iterera igenom kommentarerna i dokumentet. Anteckningar är element som länkar, kommentarer och höjdpunkter. Vi är särskilt intresserade av länkkommentarer.

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        // Bearbeta länkanteckningen
    }
}
```

I denna loop kontrollerar vi om anteckningstypen är en länk. Om det är det går vi vidare till nästa steg.

## Steg 5: Ta bort hyperlänksåtgärden

För varje länkkommentar måste vi kontrollera om den har en hyperlänksåtgärd. Om den gör det tar vi bort hyperlänken genom att ställa in dess URI till en tom sträng.

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

Detta kodavsnitt säkerställer att hyperlänksåtgärden effektivt tas bort.

## Steg 6: Absorbera textfragment

Därefter kommer vi att absorbera textfragmenten som är associerade med länkkommentaren. Detta gör att vi kan manipulera textens utseende.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

 Här skapar vi en`TextFragmentAbsorber` och ställ in dess sökalternativ till anteckningens rektangel. Detta hjälper oss att hitta texten som länkades.

## Steg 7: Ändra textens utseende

När vi har textfragmenten kan vi ändra deras utseende. I det här fallet tar vi bort understrykningen och ändrar textfärgen till svart.

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

Det här steget förbättrar textens läsbarhet genom att ta bort hyperlänkstilen.

## Steg 8: Ta bort anteckningen

Efter att ha ändrat texten kan vi säkert ta bort länkanteckningen från dokumentet.

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

Den här raden tar bort hyperlänken från PDF-filen och säkerställer att den inte längre finns i den slutliga utmatningen.

## Steg 9: Spara det ändrade dokumentet

Slutligen måste vi spara det ändrade dokumentet till en ny PDF-fil. Detta är det sista steget i vår process.

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Den här raden sparar dokumentet med hyperlänkarna borttagna, vilket skapar en ny PDF-fil med namnet`RemoveHyperlinksFromText_out.pdf`.

## Slutsats

Och där har du det! Du har framgångsrikt tagit bort hyperlänkar från ett HTML-dokument efter att ha konverterat det till PDF med Aspose.PDF för .NET. Denna process förbättrar inte bara läsbarheten för din PDF utan ger dig också kontroll över innehållet du presenterar. 

## FAQ's

### Kan jag ta bort hyperlänkar från alla PDF-dokument?
Ja, du kan ta bort hyperlänkar från alla PDF-dokument med Aspose.PDF för .NET.

### Är Aspose.PDF gratis att använda?
 Aspose.PDF erbjuder en gratis provperiod, men för alla funktioner måste du köpa en licens. Kontrollera[köpsida](https://purchase.aspose.com/buy).

### Vad händer om jag stöter på problem när jag använder Aspose.PDF?
 Du kan söka hjälp på[supportforum](https://forum.aspose.com/c/pdf/10).

### Kan jag konvertera andra filformat till PDF med Aspose?
Ja, Aspose stöder olika filformat för konvertering till PDF.

### Var kan jag ladda ner Aspose.PDF för .NET?
 Du kan ladda ner den från[nedladdningslänk](https://releases.aspose.com/pdf/net/).