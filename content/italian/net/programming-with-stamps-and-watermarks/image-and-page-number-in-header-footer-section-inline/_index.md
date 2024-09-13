---
title: Immagine e numero di pagina nella sezione intestazione/piè di pagina in linea
linktitle: Immagine e numero di pagina nella sezione intestazione/piè di pagina in linea
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere un'immagine e un numero di pagina in linea nella sezione dell'intestazione di un PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata.
type: docs
weight: 120
url: /it/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## Introduzione

Aspose.PDF per .NET è un potente strumento che offre ampie capacità per la manipolazione e la generazione di file PDF. Che tu abbia bisogno di aggiungere immagini, personalizzare intestazioni e piè di pagina o gestire il testo, Aspose.PDF ha tutto ciò che ti serve. In questo tutorial, esploreremo come aggiungere un'immagine e un numero di pagina in linea nell'intestazione o nel piè di pagina di un documento PDF. Immergiamoci subito e analizziamo il processo passo dopo passo.

## Prerequisiti

Prima di passare al codice, assicuriamoci di avere tutto a posto per seguire:

-  Aspose.PDF per .NET: Scarica l'ultima versione da[Pagina di download del PDF Aspose](https://releases.aspose.com/pdf/net/).
- Ambiente di sviluppo: ti servirà un IDE C# come Visual Studio.
-  Licenza: se non hai ancora una licenza, puoi ottenerne una[licenza temporanea qui](https://purchase.aspose.com/temporary-license/) o acquistarne uno completo dal[Negozio Aspose](https://purchase.aspose.com/buy).

Ora che hai tutti i prerequisiti, possiamo cominciare.

## Importa pacchetti

Prima di iniziare a scrivere il codice, assicurati di importare gli spazi dei nomi necessari:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Questi pacchetti consentono di lavorare con file PDF e di manipolare il testo.

## Passaggio 1: impostare la directory dei documenti

La prima cosa che dobbiamo fare è definire il percorso della directory in cui verrà salvato il nostro file PDF. Questo percorso può essere personalizzato nella cartella del tuo progetto o in qualsiasi posizione sul tuo computer.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Questa variabile contiene la posizione in cui verrà archiviato il tuo documento. Sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo.

## Passaggio 2: creare un'istanza del documento PDF

 In questo passaggio, creiamo una nuova istanza di`Aspose.Pdf.Document` oggetto. Questo oggetto fungerà da spina dorsale del tuo file PDF.

```csharp
// Crea un'istanza di un oggetto Document chiamando il suo costruttore vuoto
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

In questo caso creiamo un file PDF vuoto che potremo poi riempire con i contenuti.

## Passaggio 3: aggiungere una pagina al PDF

Il tuo PDF ha bisogno di almeno una pagina in cui puoi aggiungere intestazioni, piè di pagina e contenuto. Aggiungiamo una pagina vuota al nostro documento.

```csharp
// Crea una pagina nell'oggetto Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

 Chiamando`pdf1.Pages.Add()`viene aggiunta una nuova pagina al documento, pronta per la personalizzazione dell'intestazione e del piè di pagina.

## Passaggio 4: creare e impostare l'intestazione

Ora è il momento di creare l'intestazione per il documento. Qui aggiungeremo il testo, l'immagine e il numero di pagina.

```csharp
// Crea la sezione intestazione del documento
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
// Imposta l'intestazione per il file PDF
page.Header = header;
```

 Creiamo un`HeaderFooter` oggetto e assegnarlo al`Header` proprietà della pagina, assicurando che tutto ciò che aggiungiamo all'intestazione apparirà nella parte superiore della pagina.

## Passaggio 5: aggiungere testo in linea all'intestazione

 Aggiungere testo è semplice come creare un`TextFragment` e specificandone le proprietà. Aggiungiamo del testo colorato alla nostra intestazione.

```csharp
// Crea un oggetto Testo
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
// Specificare il colore
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

 In questo passaggio creiamo un`TextFragment` con il contenuto "Aspose.Pdf è un componente robusto di" e imposta il suo colore su blu. Il`IsInLineParagraph` La proprietà assicura che il testo sia in linea, ovvero che apparirà sulla stessa riga degli altri elementi (come l'immagine e il testo aggiuntivo).

## Passaggio 6: inserire un'immagine in linea nell'intestazione

Per rendere la tua intestazione visivamente accattivante, puoi aggiungere un'immagine in linea con il testo. Potrebbe essere il logo della tua azienda o qualsiasi altra grafica.

```csharp
// Crea un oggetto immagine nella sezione
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Imposta il percorso del file immagine
image1.File = dataDir + "aspose-logo.jpg";
// Imposta la larghezza dell'immagine Informazioni
image1.FixWidth = 50;
image1.FixHeight = 20;
// Indica che l'InlineParagraph di seg1 è un'immagine.
image1.IsInLineParagraph = true;
```

 Qui aggiungiamo un'immagine all'intestazione creando un`Image` oggetto, impostandone il percorso e regolandone la larghezza e l'altezza.`IsInLineParagraph` assicura che l'immagine sia allineata con il testo.

## Passaggio 7: aggiungere testo in linea aggiuntivo per completare l'intestazione

Aggiungiamo altro testo per completare l'intestazione incorporata.

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

 In questa parte, ne creiamo un altro`TextFragment` con il contenuto "Pty Ltd." e imposta il suo colore su marrone. Sia i frammenti di testo che l'immagine vengono aggiunti all'intestazione.

## Passaggio 8: Salva il PDF

Dopo aver impostato l'intestazione, è il momento di salvare il PDF.

```csharp
// Salva il PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

 IL`Save` Il metodo scrive il file PDF finale nella posizione specificata.

## Conclusione

Congratulazioni! Hai aggiunto con successo un'immagine e del testo all'intestazione di un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ti ha guidato attraverso i passaggi essenziali, tra cui la creazione di un documento, l'aggiunta di pagine, l'inserimento di intestazioni e il posizionamento di contenuti in linea come testo e immagini. Aspose.PDF ti offre un'incredibile flessibilità per gestire i tuoi PDF, sia che si tratti di manipolare intestazioni, piè di pagina o contenuti complessi. 

## Domande frequenti

### Posso aggiungere un numero di pagina anche all'intestazione?
 Sì! Puoi aggiungere facilmente un numero di pagina utilizzando`TextFragment` classe e formattandola come necessario. Basta inserirla nella sezione header come contenuto in linea.

### Come faccio a impostare un'immagine di sfondo nell'intestazione?
 Puoi usare il`BackgroundImage` proprietà del`HeaderFooter` classe per impostare un'immagine di sfondo. Tuttavia, questo non è contenuto in linea e coprirà l'intera area dell'intestazione.

### È possibile utilizzare altri formati di immagine oltre al JPEG?
Assolutamente! Aspose.PDF supporta vari formati di immagine come PNG, BMP e GIF.

### Posso personalizzare il carattere del testo nell'intestazione?
 Sì, puoi usare il`TextState`oggetto per modificare il carattere, la dimensione e lo stile del testo.

### Ho bisogno di una licenza per utilizzare Aspose.PDF per .NET?
 Sì, Aspose.PDF richiede una licenza per l'uso in produzione, ma puoi iniziare con una[prova gratuita qui](https://releases.aspose.com/).