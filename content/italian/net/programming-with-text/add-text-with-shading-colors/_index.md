---
title: Aggiungi testo con colori ombreggiati nel file PDF
linktitle: Aggiungi testo con colori ombreggiati nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come aggiungere testo con colori di ombreggiatura nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 80
url: /it/net/programming-with-text/add-text-with-shading-colors/
---
Questo tutorial ti guiderà attraverso il processo di aggiunta di testo con colori di ombreggiatura nel file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri aggiungere testo con colori di ombreggiatura, aggiungi la seguente direttiva using nella parte superiore del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Passaggio 3: imposta la directory dei documenti
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: carica il documento PDF
 Caricare il documento PDF esistente utilizzando il file`Document` costruttore e fornire il percorso del file del documento.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Il codice va qui...
}
```

## Passaggio 5: trova il testo da modificare
 Utilizzo`TextFragmentAbsorber` per trovare il testo desiderato all'interno del documento. Nel codice fornito cerca il testo "Lorem ipsum".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Passaggio 6: imposta il colore dell'ombreggiatura per il testo
 Creane uno nuovo`Color` oggetto con uno spazio colore pattern e specificare i colori dell'ombreggiatura del gradiente. Assegna questo colore a`ForegroundColor` proprietà del`TextState` del`TextFragment` oggetto.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Passaggio 7: applicare ulteriore formattazione del testo (facoltativo)
 È possibile applicare una formattazione aggiuntiva al frammento di testo, ad esempio la sottolineatura, modificando le proprietà del file`TextState` oggetto.

```csharp
textFragment.TextState.Underline = true;
```

## Passaggio 8: salva il documento PDF modificato
 Salvare il documento PDF modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Codice sorgente di esempio per Aggiungi testo con colori di ombreggiatura utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Crea un nuovo colore con lo spazio colore del pattern
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Conclusione
Hai aggiunto con successo testo con colori di ombreggiatura al tuo documento PDF utilizzando Aspose.PDF per .NET. Il file PDF risultante può ora essere trovato nel percorso del file di output specificato.

### Domande frequenti

#### D: Qual è l'obiettivo principale di questo tutorial?

R: Questo tutorial ti guida attraverso il processo di aggiunta di testo con colori di ombreggiatura a un file PDF utilizzando la libreria Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari per raggiungere questo obiettivo.

#### D: Quali spazi dei nomi devo importare per questo tutorial?

R: Nel file di codice in cui desideri aggiungere testo con colori di ombreggiatura, importa i seguenti spazi dei nomi all'inizio del file:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### D: Come posso specificare la directory dei documenti?

 A: Nel codice, individuare la riga`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

#### D: Come carico un documento PDF esistente?

 R: Nel passaggio 4, caricherai un documento PDF esistente utilizzando il file`Document` costruttore e fornendo il percorso del file del documento:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Il codice va qui...
}
```

#### D: Come posso trovare e modificare un testo specifico all'interno del documento PDF?

 R: Nel passaggio 5 utilizzerai il file`TextFragmentAbsorber`per trovare il testo desiderato all'interno del documento. Quindi, puoi modificare le sue proprietà:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### D: Come posso impostare i colori di ombreggiatura per il testo?

 R: Nel passaggio 6 ne creerai uno nuovo`Color` oggetto con uno spazio colore pattern e specificare i colori dell'ombreggiatura del gradiente. Assegna questo colore a`ForegroundColor` proprietà del`TextState` del`TextFragment` oggetto:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### D: Posso applicare una formattazione aggiuntiva al testo modificato?

 R: Sì, al passaggio 7 è possibile applicare ulteriore formattazione del testo, ad esempio la sottolineatura, modificando le proprietà del`TextState` oggetto:

```csharp
textFragment.TextState.Underline = true;
```

#### D: Come posso salvare il documento PDF modificato?

 R: Nel passaggio 8, salverai il documento PDF modificato utilizzando il file`Save` metodo del`Document` oggetto:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### D: Qual è il punto principale di questo tutorial?

R: Seguendo questo tutorial, hai imparato con successo come migliorare il tuo documento PDF aggiungendo testo con colori di ombreggiatura utilizzando Aspose.PDF per .NET. Ciò può essere particolarmente utile per evidenziare ed enfatizzare contenuti di testo specifici all'interno dei file PDF.