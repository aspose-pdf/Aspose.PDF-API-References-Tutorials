---
title: Evidenzia il carattere nel file PDF
linktitle: Evidenzia il carattere nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come evidenziare i caratteri in un file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 240
url: /it/net/programming-with-text/highlight-character-in-pdf/
---
In questo tutorial, spiegheremo come evidenziare i caratteri in un file PDF usando la libreria Aspose.PDF per .NET. Esamineremo passo dopo passo il processo di evidenziazione dei caratteri in un PDF usando il codice sorgente C# fornito.

## Requisiti

Prima di iniziare, assicurati di avere quanto segue:

- È stata installata la libreria Aspose.PDF per .NET.
- Conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Per prima cosa, devi impostare il percorso della directory in cui si trova il tuo file PDF di input. Sostituisci`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso del file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento PDF

 Successivamente, carichiamo il documento PDF di input utilizzando`Aspose.Pdf.Document` classe.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Passaggio 3: Converti PDF in immagine

 Per evidenziare i caratteri, convertiamo il documento PDF in un'immagine utilizzando`PdfConverter` classe. Impostiamo la risoluzione per la conversione e recuperiamo l'immagine come`Bitmap` oggetto.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Passaggio 4: evidenzia i caratteri

 Eseguiamo un ciclo su ogni pagina del documento PDF e utilizziamo un`TextFragmentAbsorber` oggetto per trovare tutte le parole nella pagina. Quindi eseguiamo un'iterazione sui frammenti di testo, segmenti e caratteri per evidenziarli usando rettangoli.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // Imposta la scala e trasforma
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Passare attraverso le pagine
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //Trova tutte le parole nella pagina
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Passa attraverso frammenti di testo
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Evidenzia i caratteri
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Eseguire un ciclo attraverso i segmenti
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Evidenziare il segmento
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Passa attraverso i personaggi
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Evidenziare il carattere
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## Passaggio 5: salvare l'immagine di output

Infine, salviamo l'immagine modificata con i caratteri evidenziati nel file di output specificato.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Esempio di codice sorgente per evidenziare i caratteri in PDF utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Percorso verso la directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				// Crea un oggetto TextAbsorber per trovare tutte le parole
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Ottieni i frammenti di testo estratti
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Fai un giro tra i frammenti
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusione

In questo tutorial, hai imparato come evidenziare i caratteri in un documento PDF usando la libreria Aspose.PDF per .NET. Seguendo la guida passo passo ed eseguendo il codice C# fornito, puoi evidenziare i caratteri in un PDF e salvare l'output come immagine.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Evidenzia carattere in file PDF"?

R: Il tutorial "Highlight Character In PDF File" spiega come usare la libreria Aspose.PDF per .NET per evidenziare i caratteri all'interno di un documento PDF. Il tutorial fornisce una guida passo passo e il codice sorgente C# per raggiungere questo obiettivo.

#### D: Perché dovrei voler evidenziare i caratteri in un documento PDF?

R: Evidenziare i caratteri in un documento PDF può essere utile per vari scopi, ad esempio per enfatizzare contenuti specifici o rendere più visibile e distinguibile un determinato testo.

#### D: Come faccio a impostare la directory dei documenti?

A: Per impostare la directory dei documenti:

1.  Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory in cui si trova il file PDF di input.

#### D: Come faccio a caricare il documento PDF e convertirlo in un'immagine?

 A: Nel tutorial, il`Aspose.Pdf.Document` la classe viene utilizzata per caricare il documento PDF di input. Quindi, il`PdfConverter` classe viene utilizzata per convertire il documento PDF in un'immagine. La risoluzione dell'immagine viene impostata e l'immagine viene recuperata come`Bitmap` oggetto.

#### D: Come faccio a evidenziare i caratteri nell'immagine del documento PDF?

A: Il tutorial ti guida attraverso il processo di scorrimento di ogni pagina del documento PDF, trovando le parole utilizzando un`TextFragmentAbsorber`e scorrere frammenti di testo, segmenti e caratteri per evidenziarli mediante rettangoli.

#### D: Posso personalizzare l'aspetto dei caratteri e dei segmenti evidenziati?

R: Sì, è possibile personalizzare l'aspetto dei caratteri e dei segmenti evidenziati modificando i colori e gli stili utilizzati nelle operazioni di disegno.

#### D: Come faccio a salvare l'immagine modificata con i caratteri evidenziati?

 A: Il tutorial mostra come salvare l'immagine modificata con i caratteri evidenziati nel file di output specificato utilizzando`Save` metodo del`Bitmap` classe.

#### D: Per questo tutorial è richiesta una licenza Aspose valida?

R: Sì, è richiesta una licenza Aspose valida affinché questo tutorial funzioni correttamente. Puoi acquistare una licenza completa o ottenere una licenza temporanea di 30 giorni dal sito Web di Aspose.