---
title: Estrai paragrafi nel file PDF
linktitle: Estrai paragrafi nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come estrarre i paragrafi nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 160
url: /it/net/programming-with-text/extract-paragraphs/
---
Questo tutorial ti guiderà attraverso il processo di estrazione dei paragrafi nel file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra i passaggi necessari.

## Requisiti
Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi altro compilatore C# installato sul tuo computer.
- Aspose.PDF per la libreria .NET. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare un gestore di pacchetti come NuGet per installarlo.

## Passaggio 1: impostare il progetto
1. Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito.
2. Aggiungere un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi richiesti
Nel file di codice in cui desideri estrarre i paragrafi, aggiungi le seguenti direttive using nella parte superiore del file:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Passaggio 3: imposta la directory dei documenti
 Nel codice, individua la riga che dice`string dataDir = "YOUR DOCUMENT DIRECTORY";` e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso della directory in cui sono archiviati i tuoi documenti.

## Passaggio 4: apri il documento PDF
 Apri un documento PDF esistente utilizzando il file`Document`costruttore e passando il percorso al file PDF di input.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 5: estrai i paragrafi
 Istanziare il`ParagraphAbsorber` class e usalo`Visit` metodo per estrarre paragrafi dal documento.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Passaggio 6: scorrere i paragrafi
Scorri i paragrafi estratti per accedere ai contenuti del testo. Utilizza cicli nidificati per attraversare sezioni e righe all'interno di ciascun paragrafo.

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

### Codice sorgente di esempio per Estrai paragrafi utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Apri un file PDF esistente
Document doc = new Document(dataDir + "input.pdf");
// Istanzia ParagraphAbsorber
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
Hai estratto con successo i paragrafi da un documento PDF utilizzando Aspose.PDF per .NET. I paragrafi estratti sono stati visualizzati nella finestra della console.

### Domande frequenti

#### D: Qual è lo scopo di questo tutorial?

R: Questo tutorial ha lo scopo di guidarti attraverso il processo di estrazione dei paragrafi da un file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# allegato fornisce passaggi pratici per eseguire questa attività.

#### D: Quali spazi dei nomi devo importare?

R: Nel file di codice in cui intendi estrarre i paragrafi, includi le seguenti direttive using all'inizio del file:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### D: Come posso specificare la directory dei documenti?

 R: Individua la linea`string dataDir = "YOUR DOCUMENT DIRECTORY";` nel codice e sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

#### D: Come posso aprire un documento PDF esistente?

 R: Nel passaggio 4, aprirai un documento PDF esistente utilizzando il file`Document` costruttore e fornendo il percorso del file PDF di input.

#### D: Come estraggo i paragrafi dal documento?

 R: Il passaggio 5 prevede la creazione di un'istanza del file`ParagraphAbsorber` class e utilizzando its`Visit` metodo per estrarre paragrafi dal documento PDF.

#### D: Come posso scorrere i paragrafi estratti?

R: Il passaggio 6 ti guida attraverso il ciclo dei paragrafi estratti. I cicli nidificati vengono utilizzati per attraversare sezioni e righe all'interno di ciascun paragrafo, accedendo e visualizzando infine il contenuto del testo.

#### D: Qual è il punto chiave di questo tutorial?

R: Seguendo questo tutorial, hai imparato come estrarre paragrafi da un documento PDF utilizzando Aspose.PDF per .NET. I paragrafi estratti sono stati visualizzati nella finestra della console, fornendoti preziose informazioni sulla struttura del contenuto del documento.