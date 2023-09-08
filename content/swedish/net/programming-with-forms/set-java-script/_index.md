---
title: Ställ in Java Script
linktitle: Ställ in Java Script
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du använder Aspose.PDF för .NET för att ställa in JavaScript i formulärfält i PDF-filer.
type: docs
weight: 270
url: /sv/net/programming-with-forms/set-java-script/
---
I den här guiden kommer vi att förklara steg för steg hur man använder Aspose.PDF-biblioteket för .NET för att definiera JavaScript i ett formulärfält i ett PDF-dokument. Vi visar dig hur du konfigurerar JavaScript-åtgärder för att utföra specifika operationer i textfältet.

## Förutsättningar

Innan du börjar, se till att du har följande:

- En .NET-utvecklingsmiljö installerad på ditt system.
- Aspose.PDF-biblioteket för .NET. Du kan ladda ner den från Asposes officiella hemsida.

## Steg 1: Konfigurera dokumentkatalogen

 Det första steget är att konfigurera dokumentkatalogen där PDF-filen du vill arbeta med finns. Du kan använda`dataDir` variabel för att ange katalogsökvägen.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 2: Ladda in PDF-filen

 det här steget laddar vi in PDF-filen med hjälp av`Document` klass av Aspose.PDF.

```csharp
// Ladda inmatad PDF-fil
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Se till att indata-PDF-filen finns i den angivna dokumentkatalogen.

## Steg 3: Öppna fältet TextBox

 För att tillämpa JavaScript på ett specifikt textfält måste vi först komma åt det fältet. I det här exemplet antar vi att textfältet heter "textbox1". Använd`doc.Form["textbox1"]` metod för att få motsvarande`TextBoxField` objekt.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Se till att det angivna textfältet finns i PDF-inmatningsfilen.

## Steg 4: Konfigurera JavaScript-åtgärder

 Nu när vi har öppnat textfältet kan vi konfigurera JavaScript-åtgärderna som är kopplade till detta fält. I det här exemplet kommer vi att använda två åtgärder:`OnModifyCharacter` och`OnFormat` . Dessa åtgärder kommer att definieras med hjälp av`JavascriptAction` föremål.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Se till att anpassa JavaScript-åtgärderna efter dina behov.

## Steg 5: Ställa in det initiala fältvärdet

Innan vi sparar den resulterande PDF-filen kan vi ställa in ett initialt värde för textfältet. I det här exemplet kommer vi att ställa in värdet "123" för fältet.

```csharp
field.Value = "123";
```

Anpassa detta värde efter dina behov.

## Steg 6: Spara den resulterande PDF-filen

 Nu när vi är klara med att ställa in textfältet och JavaScript-åtgärder kan vi spara den resulterande PDF-filen med hjälp av`Save` metod för`Document` klass.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Spara resulterande PDF
doc.Save(dataDir);
```

Var noga med att ange den fullständiga sökvägen och filnamnet för den resulterande PDF-filen.


### Exempel på källkod för Set Java Script med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ladda inmatad PDF-fil
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 siffror efter punkt
// Ingen separator
// Negativ stil = minus
// Ingen valuta
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Ställ in initialt fältvärde
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Spara resulterande PDF
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Slutsats

den här guiden lärde vi oss hur man använder Aspose.PDF-biblioteket för .NET för att ställa in JavaScript i ett formulärfält i ett PDF-dokument. Genom att följa stegen som beskrivs kan du anpassa JavaScript-åtgärder för att utföra olika operationer på textfält. Utforska gärna funktionerna i Aspose.PDF för .NET ytterligare för att utöka möjligheterna att manipulera PDF-filer.


### FAQ's

#### F: Kan jag använda Aspose.PDF för .NET för att lägga till JavaScript i andra formulärelement, såsom kryssrutor och alternativknappar?

 S: Ja, Aspose.PDF för .NET låter dig lägga till JavaScript i olika formulärelement, inklusive kryssrutor, alternativknappar och rullgardinslistor. Du kan använda`JavascriptAction` klass för att definiera JavaScript-åtgärder för olika formulärelement.

#### F: Är det möjligt att validera användarinmatning med JavaScript i formulärfält?

 S: Ja, du kan använda JavaScript för att validera användarinmatning i formulärfält. Genom att definiera JavaScript-åtgärder som`OnBlur` eller`OnKeystroke` för ett formulärfält kan du validera de angivna uppgifterna och visa felmeddelanden om det behövs.

#### F: Kan jag köra komplexa JavaScript-funktioner med Aspose.PDF för .NET?

 S: Ja, du kan köra komplexa JavaScript-funktioner med Aspose.PDF för .NET. Du har flexibiliteten att definiera anpassade JavaScript-funktioner och anropa dem inom`JavascriptAction`.

#### F: Stöder Aspose.PDF för .NET andra JavaScript-händelser än de som nämns i denna handledning?

 S: Ja, Aspose.PDF för .NET stöder ett brett utbud av JavaScript-händelser, inklusive`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , och`OnMouseUp`, bland andra. Du kan använda dessa händelser för att utlösa JavaScript-åtgärder baserat på användarinteraktioner.

#### F: Kan jag använda Aspose.PDF för .NET för att extrahera JavaScript-kod från befintliga PDF-dokument?

 S: Aspose.PDF för .NET ger möjlighet att extrahera JavaScript-kod från befintliga PDF-dokument. Du kan använda`JavascriptAction` klass och andra relevanta metoder för att komma åt och analysera JavaScript-åtgärder i en PDF-form.