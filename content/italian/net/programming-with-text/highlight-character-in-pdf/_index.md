---
title: Evidenzia il carattere nel file PDF
linktitle: Evidenzia il carattere nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come evidenziare i caratteri nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 240
url: /it/net/programming-with-text/highlight-character-in-pdf/
---
In questo tutorial spiegheremo come evidenziare i caratteri in un file PDF utilizzando la libreria Aspose.PDF per .NET. Seguiremo il processo passo passo per evidenziare i caratteri in un PDF utilizzando il codice sorgente C# fornito.

## Requisiti

Prima di iniziare, assicurati di avere quanto segue:

- La libreria Aspose.PDF per .NET installata.
- Una conoscenza di base della programmazione C#.

## Passaggio 1: impostare la directory dei documenti

 Innanzitutto, devi impostare il percorso della directory in cui si trova il file PDF di input. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso del file PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: carica il documento PDF

 Successivamente, carichiamo il documento PDF di input utilizzando il file`Aspose.Pdf.Document` classe.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Passaggio 3: converti PDF in immagine

 Per evidenziare i caratteri, convertiamo il documento PDF in un'immagine utilizzando il file`PdfConverter` classe. Impostiamo la risoluzione per la conversione e recuperiamo l'immagine come a`Bitmap` oggetto.

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

 Esaminiamo ciascuna pagina del documento PDF e utilizziamo a`TextFragmentAbsorber` oggetto per trovare tutte le parole nella pagina. Quindi iteriamo sui frammenti di testo, sui segmenti e sui caratteri per evidenziarli utilizzando rettangoli.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //Imposta scala e trasformazione
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Passa attraverso le pagine
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         // Trova tutte le parole nella pagina
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Passa in rassegna i frammenti di testo
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

                 // Passa attraverso i segmenti
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Evidenzia il segmento
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Passa attraverso i personaggi
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Evidenzia il carattere
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

## Passaggio 5: salva l'immagine di output

Infine, salviamo l'immagine modificata con i caratteri evidenziati nel file di output specificato.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Codice sorgente di esempio per Evidenzia carattere in PDF utilizzando Aspose.PDF per .NET 
```csharp
try
{
	// Il percorso della directory dei documenti.
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
				// Passa in rassegna i frammenti
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

In questo tutorial hai imparato come evidenziare i caratteri in un documento PDF utilizzando la libreria Aspose.PDF per .NET. Seguendo la guida passo passo ed eseguendo il codice C# fornito, puoi evidenziare i caratteri in un PDF e salvare l'output come immagine.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Evidenzia carattere nel file PDF"?

R: Il tutorial "Evidenzia carattere nel file PDF" spiega come utilizzare la libreria Aspose.PDF per .NET per evidenziare i caratteri all'interno di un documento PDF. L'esercitazione fornisce una guida passo passo e il codice sorgente C# per raggiungere questo obiettivo.

#### D: Perché dovrei evidenziare i caratteri in un documento PDF?

R: Evidenziare i caratteri in un documento PDF può essere utile per vari scopi, ad esempio enfatizzare contenuti specifici o rendere determinati testi più visibili e distinguibili.

#### D: Come posso impostare la directory dei documenti?

R: Per impostare la directory dei documenti:

1.  Sostituire`"YOUR DOCUMENT DIRECTORY"` nel`dataDir` variabile con il percorso della directory in cui si trova il file PDF di input.

#### D: Come carico il documento PDF e lo converto in un'immagine?

 R: Nel tutorial, il`Aspose.Pdf.Document` viene utilizzata per caricare il documento PDF di input. Poi il`PdfConverter` viene utilizzata per convertire il documento PDF in un'immagine. La risoluzione dell'immagine viene impostata e l'immagine viene recuperata come file`Bitmap` oggetto.

#### D: Come faccio a evidenziare i caratteri nell'immagine del documento PDF?

R: Il tutorial ti guida attraverso il processo di scorrimento di ciascuna pagina del documento PDF, trovando le parole utilizzando a`TextFragmentAbsorber`e scorrere frammenti di testo, segmenti e caratteri per evidenziarli utilizzando rettangoli.

#### D: Posso personalizzare l'aspetto dei caratteri e dei segmenti evidenziati?

R: Sì, puoi personalizzare l'aspetto dei caratteri e dei segmenti evidenziati modificando i colori e gli stili utilizzati nelle operazioni di disegno.

#### D: Come salvo l'immagine modificata con i caratteri evidenziati?

 R: Il tutorial mostra come salvare l'immagine modificata con i caratteri evidenziati nel file di output specificato utilizzando il file`Save` metodo del`Bitmap` classe.

#### D: Per questo tutorial è necessaria una licenza Aspose valida?

R: Sì, è necessaria una licenza Aspose valida affinché questo tutorial funzioni correttamente. È possibile acquistare una licenza completa o ottenere una licenza temporanea di 30 giorni dal sito Web Aspose.