---
title: Parole cancellate
linktitle: Parole cancellate
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come barrare le parole in un PDF usando Aspose.PDF per .NET con questa guida completa passo dopo passo. Migliora le tue capacità di modifica dei documenti.
type: docs
weight: 150
url: /it/net/annotations/strikeoutwords/
---
## Introduzione

Ti è mai capitato di dover enfatizzare un testo specifico in un PDF barrandolo? Che tu stia rivedendo documenti, contrassegnando del testo o semplicemente evidenziando determinate sezioni, barrare le parole può essere uno strumento prezioso. In questo tutorial, esploreremo come fare proprio questo usando Aspose.PDF per .NET. Questa guida completa ti guiderà attraverso ogni passaggio, assicurandoti di avere tutte le informazioni necessarie per implementare efficacemente questa funzionalità nelle tue applicazioni .NET. 

## Prerequisiti

Prima di passare al codice, ecco alcuni prerequisiti che dovrai soddisfare per seguire questo tutorial:

1.  Libreria Aspose.PDF per .NET: assicurati di avere installata la libreria Aspose.PDF per .NET. Puoi[scaricalo qui](https://releases.aspose.com/pdf/net/).

2. .NET Framework: assicurati di avere .NET Framework installato sul tuo computer. Questo tutorial è progettato per le applicazioni .NET.

3. Ambiente di sviluppo: per scrivere ed eseguire il codice avrai bisogno di un IDE come Visual Studio.

4. Documento PDF: Tieni pronto un file PDF di esempio con cui vuoi lavorare. Questo sarà il documento in cui cancelleremo il testo.

5. Conoscenze di base del linguaggio C#: per comprendere e implementare i passaggi di questo tutorial è necessaria una certa familiarità con la programmazione C#.

## Importa pacchetti

Prima di poter iniziare a programmare, dobbiamo importare i namespace necessari nel nostro progetto .NET. Questo ci darà accesso alle classi e ai metodi richiesti per manipolare i file PDF usando Aspose.PDF.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Questi namespace sono essenziali per lavorare con documenti PDF, gestire il testo e aggiungere annotazioni come le barre.

In questa sezione, suddivideremo il processo di cancellazione delle parole in un documento PDF in semplici passaggi gestibili. Ogni passaggio sarà accompagnato da una spiegazione dettagliata per assicurarti di capire come funziona il tutto.

## Passaggio 1: caricare il documento PDF

Il primo passo è caricare il documento PDF che vuoi modificare. Questo documento sarà quello in cui cancellerai parole o frasi specifiche.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Apri il documento PDF
Document document = new Document(dataDir + "input.pdf");
```

- `dataDir` : Questa variabile contiene il percorso alla directory del documento. Sostituisci`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo in cui si trova il file PDF.
- `Document` : IL`Document` class rappresenta un documento PDF. Passando il percorso del file al suo costruttore, apriamo il file PDF per l'elaborazione.

## Passaggio 2: creare un assorbitore di frammenti di testo per trovare un testo specifico

 Successivamente, creeremo un'istanza di`TextFragmentAbsorber` per cercare un frammento di testo specifico nel documento PDF. Questo ci consente di individuare il testo che vogliamo barrare.

```csharp
// Crea un'istanza di TextFragment Absorber per cercare un frammento di testo specifico
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

- `TextFragmentAbsorber`Questa classe è usata per trovare e lavorare con frammenti di testo specifici all'interno del documento PDF. In questo esempio, stiamo cercando la parola "Estoque". Sostituisci "Estoque" con la parola o la frase che vuoi trovare nel tuo documento.

## Passaggio 3: scorrere le pagine del documento PDF

 Ora che abbiamo il nostro`TextFragmentAbsorber`, dobbiamo scorrere ogni pagina del documento PDF per trovare il testo specificato.

```csharp
// Scorrere le pagine del documento PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
    // Ottieni la pagina corrente del documento PDF
    Page page = document.Pages[i];
    page.Accept(textFragmentAbsorber);
}
```

- `for (int i = 1; i <= document.Pages.Count; i++)`: Questo ciclo scorre ogni pagina del documento PDF.
- `document.Pages[i]`: Recupera la pagina corrente in fase di elaborazione.
- `page.Accept(textFragmentAbsorber)` : Questo metodo applica il`TextFragmentAbsorber` alla pagina corrente, cercando il testo specificato.

## Fase 4: Raccogliere ed elaborare i frammenti di testo

Dopo aver esaminato le pagine, raccoglieremo i frammenti di testo trovati e li prepareremo per un'ulteriore elaborazione.

```csharp
// Crea una raccolta di frammenti di testo assorbiti
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`Questa raccolta memorizza tutti i frammenti di testo che sono stati trovati nel documento. Utilizzeremo questa raccolta nel passaggio successivo per barrare il testo.

## Passaggio 5: scorrere i frammenti di testo e cancellarli

In questa fase, analizzeremo ogni frammento di testo nella nostra raccolta e applicheremo un'annotazione barrata.

```csharp
// Eseguire l'iterazione sulla raccolta di frammenti di testo
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

    // Ottieni le dimensioni rettangolari dell'oggetto TextFragment
    Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
        (float)textFragment.Position.XIndent,
        (float)textFragment.Position.YIndent,
        (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width,
        (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

    // Crea un'istanza di annotazione StrikeOut
    StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);

    // Imposta le proprietà dell'annotazione barrata
    strikeOut.Opacity = .80f;
    strikeOut.Border = new Border(strikeOut);
    strikeOut.Color = Aspose.Pdf.Color.Red;

    // Aggiungere l'annotazione alla raccolta di annotazioni della pagina del frammento di testo
    textFragment.Page.Annotations.Add(strikeOut);
}
```

- `TextFragment textFragment = textFragmentCollection[j]`: Questa riga recupera il frammento di testo corrente.
- `Aspose.Pdf.Rectangle`: Calcoliamo le dimensioni rettangolari del frammento di testo per determinare dove applicare la barratura.
- `StrikeOutAnnotation`: Questa classe rappresenta l'annotazione barrata. La istanziamo con il rettangolo calcolato e la pagina corrente.
- `strikeOut.Opacity`: Questa proprietà imposta l'opacità della barratura, rendendola visibile all'80%.
- `strikeOut.Color`Abbiamo impostato il colore del barrato su rosso. Puoi cambiarlo con qualsiasi colore tu preferisca.
- `textFragment.Page.Annotations.Add(strikeOut)`: Questo aggiunge l'annotazione barrata alla pagina.

## Passaggio 6: Salvare il documento PDF modificato

Il passaggio finale consiste nel salvare il documento PDF modificato con le barre applicate.

```csharp
// Salva il documento PDF aggiornato
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

- `dataDir + "StrikeOutWords_out.pdf"`: Questo crea un nuovo nome file per il documento modificato. Il file originale rimane invariato.
- `document.Save(dataDir)`: Salva il documento PDF barrato nella posizione specificata.

## Conclusione

Congratulazioni! Hai barrato con successo parole specifiche in un documento PDF usando Aspose.PDF per .NET. Seguendo questa guida passo passo, ora puoi personalizzare i documenti PDF evidenziando o barrando il testo, rendendoli più dinamici e adatti alle tue esigenze. Che tu stia annotando documenti legali, preparando report o semplicemente contrassegnando il testo per la revisione, questo tutorial ti ha fornito le competenze per farlo in modo efficiente.

## Domande frequenti

### Posso cambiare il colore della barratura?

 Sì, puoi cambiare il colore modificando il`strikeOut.Color`proprietà. Ad esempio, puoi impostarlo su`Aspose.Pdf.Color.Blue` per uno strikeout blu.

### È possibile barrare più parole contemporaneamente?

 Assolutamente! Il`TextFragmentAbsorber` può essere utilizzato per cercare qualsiasi parola o frase nel documento. È possibile applicare la barratura a più istanze iterando attraverso il`TextFragmentCollection`.

### Cosa succede se voglio barrare il testo solo su pagine specifiche?

 Puoi modificare il ciclo che scorre le pagine per includere solo le pagine che vuoi modificare. Ad esempio,`for (int i = 1; i <= 3; i++)` applicherebbe la barratura solo alle prime tre pagine.

### Come posso regolare lo spessore della linea barrata?

 È possibile regolare lo spessore della linea barrata modificando il`Border` proprietà del`StrikeOutAnnotation`Ciò consente di personalizzare l'aspetto della barratura.

### C'è un modo per annullare la barratura dopo aver salvato il documento?

Una volta salvato il documento, il barrato è permanente. Se hai bisogno di conservare il testo originale senza barrato, prendi in considerazione di salvare un backup del documento originale prima di applicare qualsiasi modifica.