---
title: Cambia orientamento
linktitle: Cambia orientamento
second_title: Aspose.PDF per riferimento all'API .NET
description: Guida passo passo per modificare l'orientamento della pagina di un PDF con Aspose.PDF per .NET. Facile da seguire e implementare nei tuoi progetti.
type: docs
weight: 10
url: /it/net/programming-with-pdf-pages/change-orientation/
---
In questo tutorial ti guideremo attraverso il processo passo passo per modificare l'orientamento della pagina di un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come modificare l'orientamento della pagina dei tuoi documenti PDF utilizzando Aspose.PDF per .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Conoscenza base del linguaggio di programmazione C#
- Aspose.PDF per .NET installato nel tuo ambiente di sviluppo

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui si trova il file PDF di input e dove desideri salvare il file PDF di output modificato. Sostituisci "DIRECTORY DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: carica il documento PDF
 Quindi puoi caricare il documento PDF dal file di input utilizzando il file`Document` classe di Aspose.PDF. Assicurati di specificare il percorso corretto del file PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 3: modifica l'orientamento della pagina
Ora esamineremo ogni pagina del documento e ne cambieremo l'orientamento. Per ogni pagina, modifichiamo le dimensioni del media box (`MediaBox`) scambiando larghezza e altezza, quindi regoliamo le coordinate del media box per mantenere la posizione della pagina. Infine, impostiamo la rotazione della pagina su 90 gradi.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## Passaggio 4: salva il documento PDF modificato
 Infine, puoi salvare il documento PDF modificato in un file di output utilizzando il file`Save()` metodo del`Document`classe. Assicurati di specificare il percorso e il nome file corretti.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Codice sorgente di esempio per l'orientamento del cambiamento utilizzando Aspose.PDF per .NET 

```csharp

// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Dobbiamo spostare la pagina in alto per compensare la modifica delle dimensioni della pagina
	// (il bordo inferiore della pagina è 0,0 e le informazioni vengono solitamente inserite dal file
	// In cima alla pagina. Ecco perché spostiamo il bordo dell'amante in alto sulla differenza tra
	// Vecchia e nuova altezza.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// A volte dobbiamo anche impostare CropBox (se era impostato nel file originale)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Impostazione dell'angolo di rotazione della pagina
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Salva il file di output
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Conclusione
In questo tutorial, abbiamo imparato come modificare l'orientamento della pagina di un documento PDF utilizzando Aspose.PDF per .NET. Seguendo i passaggi sopra descritti, puoi facilmente implementare questa funzionalità nei tuoi progetti. Sentiti libero di esplorare ulteriormente la documentazione di Aspose.PDF per scoprire altre utili funzionalità per lavorare con i file PDF.

### Domande frequenti

#### D: Qual è lo scopo di modificare l'orientamento della pagina in un documento PDF?

R: La modifica dell'orientamento della pagina in un documento PDF consente di ruotare il contenuto della pagina di 90 gradi. Ciò può essere utile negli scenari in cui il contenuto originale deve essere visualizzato o stampato con un orientamento diverso, ad esempio passando dalla modalità verticale a quella orizzontale o viceversa.

#### D: Posso modificare l'orientamento di pagine specifiche nel documento PDF?

 R: Sì, puoi modificare l'orientamento di pagine specifiche nel documento PDF. Nel codice sorgente C# fornito, il file`foreach` loop viene utilizzato per scorrere ciascuna pagina del documento e modificarne l'orientamento. Se desideri modificare solo l'orientamento di pagine specifiche, puoi modificare il ciclo per indirizzare tali pagine in base ai numeri di pagina o ad altri criteri.

#### D: La modifica dell'orientamento della pagina influisce sul layout del contenuto della pagina?

R: Sì, la modifica dell'orientamento della pagina influirà sul layout del contenuto della pagina. Il contenuto verrà ruotato di 90 gradi e la larghezza e l'altezza della pagina verranno invertite. Di conseguenza, il posizionamento e l'allineamento del contenuto sulla pagina potrebbero cambiare.

#### D: Posso ruotare la pagina di un angolo diverso da 90 gradi?

 R: Nel codice sorgente C# fornito, la rotazione della pagina è impostata su 90 gradi utilizzando`page.Rotate = Rotate.on90;` . Tuttavia, se necessario, è possibile modificare l'angolo di rotazione su altri valori. Ad esempio, puoi usare`Rotate.on180` per ruotare la pagina di 180 gradi o`Rotate.on270` per ruotarlo di 270 gradi.

#### D: Come posso gestire il contenuto della pagina che va in overflow dopo aver modificato l'orientamento?

R: Quando si modifica l'orientamento della pagina, le dimensioni della pagina potrebbero cambiare, il che può provocare un overflow del contenuto. Per gestire questo problema, potrebbe essere necessario modificare il layout e la formattazione del contenuto della pagina. È possibile utilizzare le funzionalità fornite da Aspose.PDF per .NET, come il ridimensionamento degli elementi, la regolazione dei margini o la riorganizzazione del contenuto, per garantire che il contenuto della pagina si adatti correttamente dopo la modifica dell'orientamento.