---
title: Aggiungi indice al file PDF
linktitle: Aggiungi indice al file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere un indice a un PDF usando Aspose.PDF per .NET. Questa guida passo passo semplifica il processo e assicura una facile navigazione all'interno dei tuoi documenti.
type: docs
weight: 40
url: /it/net/programming-with-document/addtoc/
---
## Introduzione

Hai mai scorretto all'infinito un PDF lungo, desiderando che avesse un indice ben organizzato? Bene, oggi è il tuo giorno fortunato! In questo tutorial, imparerai come aggiungere un indice al tuo file PDF usando Aspose.PDF per .NET. Che tu stia lavorando a un report complesso, un eBook o una proposta commerciale, un indice può trasformare il tuo documento in un capolavoro professionale e navigabile.

## Prerequisiti

Prima di passare al codice, assicuriamoci di avere tutto ciò di cui hai bisogno:

1. Aspose.PDF per .NET: assicurati di aver scaricato e installato la libreria Aspose.PDF. Puoi scaricarla da[Qui](https://releases.aspose.com/pdf/net/).
   
2. Ambiente di sviluppo: assicurati di avere installato sul tuo computer un ambiente di sviluppo .NET come Visual Studio.

3.  Licenza: se non hai una licenza, puoi ottenere una prova gratuita o richiedere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).

## Importa pacchetti

Per iniziare, assicurati di importare i namespace necessari all'inizio del tuo file di codice. Ecco come:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Questi namespace consentono di accedere alle funzionalità specifiche dei PDF e di manipolare gli elementi di testo all'interno del documento.

Suddividiamo questo compito in piccoli passaggi. Ogni passaggio ti guiderà attraverso il processo di creazione e inserimento di un TOC nel tuo documento PDF.

## Passaggio 1: caricare il documento PDF

La prima cosa che dobbiamo fare è caricare il file PDF esistente in cui vogliamo aggiungere l'indice.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

 In questo passaggio, specifichiamo il percorso alla directory del documento e carichiamo il PDF utilizzando`Document` oggetto. Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo del file.

## Passaggio 2: inserire una nuova pagina per il sommario

Poi, inseriamo una nuova pagina all'inizio del documento PDF. Questa pagina ospiterà l'indice.

```csharp
Page tocPage = doc.Pages.Insert(1);
```

Inserendo la pagina dell'indice all'inizio, ci assicuriamo che sia la prima cosa che i lettori vedono nel PDF.

## Passaggio 3: creare un oggetto informativo TOC

Ora, creiamo un oggetto che rappresenterà le informazioni del TOC. Aggiungeremo anche un titolo al TOC per farlo risaltare.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

Qui abbiamo impostato il titolo dell'indice come "Indice", aumentato la dimensione del carattere e reso il testo in grassetto per dargli maggiore enfasi.

## Passaggio 4: definire gli elementi del sommario

In questa fase, definiamo gli elementi (o titoli) che saranno visualizzati nel TOC. Questi elementi aiuteranno i lettori a navigare verso sezioni specifiche del documento.

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
```

Abbiamo creato una serie di stringhe che fungeranno da elementi dell'indice, corrispondenti alle diverse pagine del PDF.

## Passaggio 5: creare titoli di indice

Ora arriva la parte cruciale: aggiungere i titoli all'indice e collegarli alle rispettive pagine.

```csharp
for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;
    segment2.Text = titles[i];

    tocPage.Paragraphs.Add(heading2);
}
```

Ecco cosa sta succedendo:
- Titolo: Creiamo un`Heading` oggetto e aggiungi un`TextSegment` ad esso.
- Pagina di destinazione: impostiamo la pagina a cui verrà collegato ogni titolo.
- Posizione superiore: specifichiamo la posizione nella pagina a cui punterà l'intestazione.
- Testo: Ogni intestazione ottiene il rispettivo titolo dalla matrice creata in precedenza.

Questo ciclo crea titoli per i primi due elementi dell'indice e li collega alle pagine corrispondenti.

## Passaggio 6: Salvare il PDF con l'indice

Infine, dopo aver aggiunto tutti gli elementi dell'indice, è il momento di salvare il PDF aggiornato.

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
```

Il file è ora salvato con il TOC aggiunto al PDF. Congratulazioni: hai aggiunto con successo un indice!

## Passaggio 7: messaggio di conferma

Per far sapere all'utente che il processo è completato, visualizzeremo un semplice messaggio nella console.

```csharp
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Conclusione

Ed ecco fatto! Con Aspose.PDF per .NET, aggiungere un indice a un PDF non è solo facile, ma anche personalizzabile. Che tu debba creare semplici link di navigazione o strutture complesse, questo strumento ti copre. Quindi, la prossima volta che lavori su un PDF lungo, non dimenticare di aggiungere un indice per quel tocco professionale!

## Domande frequenti

### Posso personalizzare l'aspetto del sommario in Aspose.PDF?  
Sì, puoi personalizzare completamente l'aspetto del sommario, inclusi stile, dimensione e allineamento del carattere.

### Come posso aggiungere sottotitoli all'indice?  
 È possibile aggiungere sottotitoli modificando il`Heading` livello (ad esempio,`Heading(2)`) per creare un indice gerarchico.

### È possibile aggiornare automaticamente l'indice se il documento cambia?  
No, il TOC non si aggiornerà automaticamente. Dovrai ricrearlo se la struttura del documento cambia.

### Posso collegare le voci dell'indice a documenti esterni?  
Sì, puoi utilizzare i collegamenti ipertestuali per collegare le voci dell'indice a PDF o URL esterni.

### Aspose.PDF supporta TOC multilivello?  
Sì, Aspose.PDF supporta indice multilivello per documenti complessi con sottosezioni.