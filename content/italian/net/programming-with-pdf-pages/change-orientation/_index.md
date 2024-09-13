---
title: Cambia orientamento
linktitle: Cambia orientamento
second_title: Riferimento API Aspose.PDF per .NET
description: Guida passo passo per cambiare l'orientamento della pagina di un PDF con Aspose.PDF per .NET. Facile da seguire e implementare nei tuoi progetti.
type: docs
weight: 10
url: /it/net/programming-with-pdf-pages/change-orientation/
---
## Introduzione

Ti è mai capitato di avere difficoltà con un file PDF in cui l'orientamento della pagina è semplicemente... sbagliato? Forse hai a che fare con un documento che è stato scansionato o creato in modo errato e le pagine devono essere ruotate per avere senso. Fortunatamente per noi, Aspose.PDF per .NET fornisce un modo semplice e potente per manipolare i file PDF in qualsiasi modo immaginabile, incluso il cambio dell'orientamento delle tue pagine. Che tu voglia passare da verticale a orizzontale o viceversa, questa guida ti guiderà passo dopo passo nel processo.

Quindi, se sei pronto a tuffarti e ruotare le pagine del PDF con facilità, cominciamo!

## Prerequisiti

Prima di entrare nei dettagli della modifica dell'orientamento della pagina nel tuo PDF, vediamo brevemente cosa ti servirà:

-  Aspose.PDF per .NET: assicurati di aver installato la libreria Aspose.PDF per .NET. In caso contrario, puoi[scaricalo qui](https://releases.aspose.com/pdf/net/).
- Un ambiente di sviluppo .NET: puoi utilizzare Visual Studio, JetBrains Rider o qualsiasi IDE preferito per lavorare con .NET.
- Conoscenza di base di C#: sebbene questa guida sia semplice, una conoscenza di base di C# renderà il tutto ancora più semplice da seguire.
- Un file PDF: l'esempio seguente presuppone che tu abbia un file PDF con più pagine. Se non ne hai uno a portata di mano, crea o scarica un PDF di esempio con cui lavorare.

 Inoltre, se hai appena iniziato, puoi provare Aspose.PDF con un[licenza temporanea gratuita](https://purchase.aspose.com/temporary-license/) prima di decidere di[acquista la versione completa](https://purchase.aspose.com/buy).

## Importazione degli spazi dei nomi

Prima di poter manipolare l'orientamento delle pagine nel tuo PDF, dovrai importare i namespace necessari nel tuo progetto C#. Assicurati di avere quanto segue:

```csharp
using System.IO;
using Aspose.Pdf;
```

Dopo aver importato questo, passiamo alla parte principale del tutorial.

## Passaggio 1: caricare il documento PDF

 La prima cosa che dobbiamo fare è caricare il file PDF che desideri modificare. Puoi usare il`Document` classe dallo spazio dei nomi Aspose.PDF per aprire il PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Questa riga carica il PDF dalla directory specificata. Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo del tuo file. Il`"input.pdf"` è il PDF di cui vuoi modificare l'orientamento.

## Passaggio 2: scorrere ogni pagina

 Ora che abbiamo caricato il documento, facciamo un ciclo attraverso ogni pagina del PDF. Useremo un`foreach` per scorrere ogni pagina, consentendoci di applicare la modifica di orientamento a tutte.

```csharp
foreach (Page page in doc.Pages)
{
    // Manipola ogni pagina
}
```

Questo ciclo itererà attraverso tutte le pagine del documento.

## Passaggio 3: Ottieni il MediaBox della pagina

 Ogni pagina di un PDF ha un`MediaBox` che definisce i confini della pagina. Dobbiamo accedervi per determinare l'orientamento corrente e modificarlo.

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

 IL`MediaBox` ci fornisce le dimensioni della pagina, come larghezza, altezza e posizionamento.

## Passaggio 4: scambia larghezza e altezza

Per cambiare l'orientamento della pagina da verticale a orizzontale o da orizzontale a verticale, basta scambiare i valori di larghezza e altezza. Questo passaggio regolerà le dimensioni della pagina.

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Questo codice scambia l'altezza e la larghezza e riposiziona l'angolo inferiore sinistro (`LLY`) in modo che il contenuto si adatti perfettamente dopo la rotazione.

## Passaggio 5: Aggiorna MediaBox e CropBox

Ora che abbiamo la nuova altezza e larghezza, applichiamo le modifiche alla pagina`MediaBox` E`CropBox` . IL`CropBox` è essenziale se il documento originale ne aveva uno, assicurando la corretta visualizzazione dell'intera pagina.

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

Questo passaggio ridimensiona la pagina in base alle nuove dimensioni appena calcolate.

## Passaggio 6: ruota la pagina

Infine, impostiamo l'angolo di rotazione della pagina. Aspose.PDF rende tutto molto semplice. Possiamo ruotare la pagina di 90 gradi per passare da verticale a orizzontale o viceversa.

```csharp
page.Rotate = Rotation.on90;
```

Questo codice ruota la pagina di 90 gradi, orientandola secondo l'orientamento desiderato.

## Passaggio 7: Salvare il PDF di output

Dopo aver applicato le modifiche di orientamento a tutte le pagine, salviamo il documento modificato in un nuovo file. 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

 Assicurati di fornire un nuovo nome file (in questo caso,`ChangeOrientation_out.pdf`) per salvare l'output. In questo modo, non sovrascrivi il tuo file originale.

### Conclusione

Ed ecco fatto! Cambiare l'orientamento della pagina di un file PDF usando Aspose.PDF per .NET è semplice come caricare il documento, scorrere le pagine, regolare MediaBox e salvare il file aggiornato. Che tu abbia a che fare con un documento scansionato male o che tu abbia bisogno di ruotare le pagine per adattarle alle tue esigenze di formattazione, questa guida passo passo dovrebbe aiutarti.

## Domande frequenti

### Posso ruotare pagine specifiche invece di tutte le pagine del PDF?  
Sì, puoi modificare il ciclo per indirizzare pagine specifiche utilizzando il loro indice anziché eseguire il ciclo su tutte le pagine.

###  Che cosa è il`MediaBox`?  
 IL`MediaBox` definisce la dimensione e la forma della pagina in un file PDF. È dove viene inserito il contenuto della pagina.

### Aspose.PDF per .NET funziona con altri formati di file?  
Sì, Aspose.PDF può gestire diversi formati di file, tra cui HTML, XML, XPS e altri.

### Esiste una versione gratuita di Aspose.PDF per .NET?  
 Sì, puoi iniziare con un[prova gratuita](https://releases.aspose.com/) o richiedi un[licenza temporanea](https://purchase.aspose.com/temporary-license/).

### Posso annullare le modifiche una volta salvate?  
Una volta salvato il documento, le modifiche sono permanenti. Assicurati di lavorare su una copia o di conservare un backup del file originale.