---
title: Cambia orientamento
linktitle: Cambia orientamento
second_title: Riferimento API Aspose.PDF per .NET
description: Guida passo passo per cambiare l'orientamento della pagina di un PDF con Aspose.PDF per .NET. Facile da seguire e implementare nei tuoi progetti.
type: docs
weight: 10
url: /it/net/programming-with-pdf-pages/change-orientation/
---
In questo tutorial, ti guideremo passo dopo passo nel processo per modificare l'orientamento della pagina di un documento PDF utilizzando Aspose.PDF per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come modificare l'orientamento della pagina dei tuoi documenti PDF utilizzando Aspose.PDF per .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Una conoscenza di base del linguaggio di programmazione C#
- Aspose.PDF per .NET installato nel tuo ambiente di sviluppo

## Passaggio 1: definire la directory dei documenti
Per prima cosa, devi impostare il percorso per la tua directory dei documenti. Questa è la posizione in cui si trova il tuo file PDF di input e dove vuoi salvare il tuo file PDF di output modificato. Sostituisci "YOUR DOCUMENTS DIRECTORY" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricare il documento PDF
 Quindi puoi caricare il documento PDF dal file di input utilizzando`Document` classe di Aspose.PDF. Assicurati di specificare il percorso corretto per il file PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Passaggio 3: modifica l'orientamento della pagina
Ora esamineremo ogni pagina del documento e ne cambieremo l'orientamento. Per ogni pagina, modifichiamo le dimensioni del box multimediale (`MediaBox`) scambiando larghezza e altezza, quindi regoliamo le coordinate del box multimediale per mantenere la posizione della pagina. Infine, impostiamo la rotazione della pagina a 90 gradi.

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

## Passaggio 4: salvare il documento PDF modificato
 Infine, puoi salvare il documento PDF modificato in un file di output utilizzando`Save()` metodo del`Document`classe. Assicurati di specificare il percorso e il nome file corretti.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Esempio di codice sorgente per modificare l'orientamento utilizzando Aspose.PDF per .NET 

```csharp

// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Dobbiamo spostare la pagina verso l'alto per compensare la modifica delle dimensioni della pagina
	// (il bordo inferiore della pagina è 0,0 e le informazioni sono solitamente posizionate dal
	// Inizio pagina. Ecco perché spostiamo il bordo dell'amante verso l'alto sulla differenza tra
	// Altezza vecchia e nuova.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// A volte dobbiamo anche impostare CropBox (se è stato impostato nel file originale)
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
In questo tutorial, abbiamo imparato come cambiare l'orientamento della pagina di un documento PDF usando Aspose.PDF per .NET. Seguendo i passaggi descritti sopra, puoi facilmente implementare questa funzionalità nei tuoi progetti. Sentiti libero di esplorare ulteriormente la documentazione di Aspose.PDF per scoprire altre utili funzionalità per lavorare con i file PDF.

### Domande frequenti

#### D: Qual è lo scopo di cambiare l'orientamento della pagina in un documento PDF?

R: Cambiare l'orientamento della pagina in un documento PDF consente di ruotare il contenuto della pagina di 90 gradi. Ciò può essere utile in scenari in cui il contenuto originale deve essere visualizzato o stampato in un orientamento diverso, ad esempio passando dalla modalità verticale a quella orizzontale o viceversa.

#### D: Posso modificare l'orientamento di pagine specifiche nel documento PDF?

 A: Sì, puoi modificare l'orientamento di pagine specifiche nel documento PDF. Nel codice sorgente C# fornito, il`foreach` loop viene utilizzato per scorrere ogni pagina del documento e modificarne l'orientamento. Se vuoi modificare solo l'orientamento di pagine specifiche, puoi modificare il loop per indirizzare quelle pagine in base ai loro numeri di pagina o ad altri criteri.

#### D: La modifica dell'orientamento della pagina influisce sul layout del contenuto della pagina?

R: Sì, cambiare l'orientamento della pagina inciderà sul layout del contenuto della pagina. Il contenuto verrà ruotato di 90 gradi e la larghezza e l'altezza della pagina verranno scambiate. Di conseguenza, il posizionamento e l'allineamento del contenuto sulla pagina potrebbero cambiare.

#### D: Posso ruotare la pagina di un angolo diverso da 90 gradi?

 A: Nel codice sorgente C# fornito, la rotazione della pagina è impostata a 90 gradi utilizzando`page.Rotate = Rotate.on90;` . Tuttavia, puoi modificare l'angolo di rotazione in altri valori se necessario. Ad esempio, puoi usare`Rotate.on180` per ruotare la pagina di 180 gradi o`Rotate.on270` per ruotarlo di 270 gradi.

#### D: Come faccio a gestire il contenuto della pagina che fuoriesce dopo aver modificato l'orientamento?

R: Quando si modifica l'orientamento della pagina, le dimensioni della pagina potrebbero cambiare, il che potrebbe causare un overflow di contenuto. Per gestire questo problema, potrebbe essere necessario modificare il layout e la formattazione del contenuto della pagina. È possibile utilizzare le funzionalità fornite da Aspose.PDF per .NET, come il ridimensionamento degli elementi, la regolazione dei margini o la riorganizzazione del contenuto, per garantire che il contenuto della pagina si adatti correttamente dopo la modifica dell'orientamento.