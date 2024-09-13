---
title: Nascondi i numeri di pagina nel sommario
linktitle: Nascondi i numeri di pagina nel sommario
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come nascondere i numeri di pagina nell'indice usando Aspose.PDF per .NET. Segui questa guida dettagliata con esempi di codice per creare PDF professionali.
type: docs
weight: 220
url: /it/net/programming-with-document/hidepagenumbersintoc/
---
## Introduzione

Quando lavori con i PDF, a volte potresti voler generare un indice (TOC) ma mantenere le cose eleganti nascondendo i numeri di pagina. Forse il documento scorre meglio senza di essi, o forse è una scelta estetica. Qualunque sia la tua ragione, se stai lavorando con Aspose.PDF per .NET, questo tutorial ti mostrerà esattamente come nascondere i numeri di pagina nel tuo TOC.

## Prerequisiti

Prima di iniziare, ci sono alcune cose che dovrai mettere a posto. Ecco una rapida checklist:

- Visual Studio installato: per scrivere il codice sarà necessaria una versione funzionante di Visual Studio.
- Libreria Aspose.PDF per .NET: assicurati di aver installato la libreria Aspose.PDF per .NET.
  -  Link per il download:[Aspose.PDF per .NET](https://releases.aspose.com/pdf/net/)
- Licenza temporanea: se vuoi testare le funzionalità, è utile avere una licenza temporanea.
  -  Licenza temporanea:[Ottienilo qui](https://purchase.aspose.com/temporary-license/)

## Importa pacchetti

Prima di passare al codice, assicurati di importare i seguenti namespace nel tuo progetto C#. Questi forniranno le classi e i metodi necessari per lavorare con documenti PDF e creare il tuo indice (TOC).

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Ora che il tuo ambiente è pronto e i pacchetti sono importati, analizziamo ogni passaggio del processo. Tratteremo ogni parte del codice per garantire chiarezza, così potrai seguire facilmente.

## Passaggio 1: inizializza il tuo documento PDF

La prima cosa che dobbiamo fare è creare un nuovo documento PDF e aggiungere una pagina per l'indice (TOC).


```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir: questa è la directory in cui verrà salvato il file di output.
- Document(): Inizializza un nuovo documento PDF.
- Pages.Add(): aggiunge una nuova pagina vuota al documento, che in seguito conterrà l'indice.

## Passaggio 2: imposta le informazioni del sommario e il titolo

Successivamente, definiremo le informazioni dell'indice, inclusa l'impostazione del titolo che apparirà nella parte superiore dell'indice.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo: questo oggetto contiene tutte le informazioni sul TOC.
- TextFragment: rappresenta il testo del titolo dell'indice, qui lo impostiamo come "Indice".
- FontStyle: diamo uno stile al titolo dell'indice impostandone la dimensione a 20 e rendendolo in grassetto.
- tocPage.TocInfo: assegniamo le informazioni del sommario alla pagina che lo visualizzerà.

## Passaggio 3: nascondere i numeri di pagina nel sommario

Ora la parte divertente! Ecco dove configuriamo il TOC per nascondere i numeri di pagina.

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

-  IsShowPageNumbers: Questo è l'interruttore magico che nasconde i numeri di pagina. Impostalo su`false`e i numeri di pagina non appariranno nell'indice.
- FormatArrayLength: impostiamo questo valore su 4, per indicare che vogliamo definire la formattazione per quattro livelli di intestazioni del sommario.

## Passaggio 4: personalizzare la formattazione del sommario

Per aggiungere più stile al tuo indice, definiremo ora la formattazione per i diversi livelli di titoli.

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray: questo array controlla la formattazione delle voci del TOC. Ogni indice rappresenta un diverso livello di intestazione.
- Margini e stile del testo: impostiamo i margini e applichiamo stili di carattere quali grassetto, corsivo e sottolineato per ogni livello di intestazione.

## Passaggio 5: aggiungere intestazioni al documento

Infine, aggiungiamo i titoli veri e propri che faranno parte dell'indice.

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- Heading e TextSegment: rappresentano i titoli che appariranno nel tuo TOC. Ogni livello ha il suo titolo.
- IsAutoSequence: numera automaticamente le intestazioni.
- IsInList: assicura che ogni intestazione venga visualizzata nell'indice.

## Passaggio 6: Salvare il documento

Una volta impostato tutto, salva il documento PDF nel file di output specificato.

```csharp
doc.Save(outFile);
```

Ed ecco fatto! Hai creato con successo un PDF con un indice e i numeri di pagina sono nascosti!

## Conclusione

Creare un indice in un PDF e nascondere i numeri di pagina potrebbe sembrare complicato, ma con Aspose.PDF per .NET è un gioco da ragazzi. Seguendo questa guida passo passo, hai imparato come personalizzare il formato dell'indice, nascondere i numeri di pagina e applicare stili diversi alle tue intestazioni. Ora puoi creare PDF professionali su misura per le tue esigenze specifiche.

## Domande frequenti

### Posso mostrare i numeri di pagina per titoli specifici nell'indice?
No, Aspose.PDF nasconde o mostra i numeri di pagina per l'intero indice. Non puoi nasconderli selettivamente per voci specifiche.

### È possibile aggiungere altri livelli al TOC?
 Sì, puoi aumentare il`FormatArrayLength` per definire più livelli di titoli dell'indice.

### Come posso cambiare il carattere per tutte le voci dell'indice?
 È possibile cambiare il font modificando il`TextState.Font` proprietà per ogni livello nel`FormatArray`.

### Posso inserire collegamenti ipertestuali nell'indice?
 Sì, puoi collegare ogni voce del sommario a una sezione specifica del documento utilizzando`Heading.TocPage` proprietà.

### Ho bisogno di una licenza per Aspose.PDF?
Sì, è richiesta una licenza valida per l'uso in produzione. Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/) per testare le funzionalità.