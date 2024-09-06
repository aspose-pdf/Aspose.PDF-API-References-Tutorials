---
title: Estrai paragrafi nel file PDF
linktitle: Estrai paragrafi nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come estrarre paragrafi da un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 160
url: /it/net/programming-with-text/extract-paragraphs/
---
Questo tutorial ti guiderà attraverso il processo di estrazione di paragrafi in un file PDF usando Aspose.PDF per .NET. Il codice sorgente C# fornito dimostra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito web ufficiale di Aspose o usare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importare gli spazi dei nomi richiesti
Nel file di codice in cui vuoi estrarre i paragrafi, aggiungi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Passaggio 3: impostare la directory del documento
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: aprire il documento PDF
 Aprire un documento PDF esistente utilizzando`Document` costruttore e passando il percorso al file PDF di input.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 5: estrai i paragrafi
 Istanziare il`ParagraphAbsorber` classe e usa il suo`Visit` metodo per estrarre paragrafi dal documento.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Passaggio 6: scorrere i paragrafi
Passa attraverso i paragrafi estratti per accedere al contenuto del testo. Utilizza loop annidati per attraversare sezioni e righe all'interno di ogni paragrafo.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### Esempio di codice sorgente per estrarre paragrafi utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Aprire un file PDF esistente
Document doc = new Document(dataDir + "input.pdf");
// Crea un'istanza di ParagraphAbsorber
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## Conclusione
Hai estratto correttamente i paragrafi da un documento PDF utilizzando Aspose.PDF per .NET. I paragrafi estratti sono stati visualizzati nella finestra della console.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

A: Questo tutorial ha lo scopo di guidarti attraverso il processo di estrazione di paragrafi da un file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# allegato fornisce passaggi pratici per raggiungere questo obiettivo.

#### D: Quali namespace dovrei importare?

A: Nel file di codice in cui intendi estrarre i paragrafi, includi le seguenti direttive all'inizio del file:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### D: Come faccio a specificare la directory dei documenti?

 A: Individua la linea`string dataDir = "YOUR DOCUMENT DIRECTORY";` nel codice e sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory del documento.

#### D: Come faccio ad aprire un documento PDF esistente?

 A: Nel passaggio 4, aprirai un documento PDF esistente utilizzando`Document` costruttore e fornendo il percorso al file PDF di input.

#### D: Come faccio a estrarre i paragrafi dal documento?

 A: Il passaggio 5 prevede la creazione di un'istanza di`ParagraphAbsorber` classe e usando il suo`Visit` metodo per estrarre paragrafi dal documento PDF.

#### D: Come posso scorrere i paragrafi estratti?

A: Il passaggio 6 ti guida attraverso il looping attraverso i paragrafi estratti. I loop annidati vengono utilizzati per attraversare sezioni e righe all'interno di ogni paragrafo, accedendo e visualizzando infine il contenuto del testo.

#### D: Qual è il messaggio più importante da trarre da questo tutorial?

R: Seguendo questo tutorial, hai imparato come estrarre paragrafi da un documento PDF usando Aspose.PDF per .NET. I paragrafi estratti sono stati visualizzati nella finestra della console, fornendoti preziose informazioni sulla struttura del contenuto del documento.