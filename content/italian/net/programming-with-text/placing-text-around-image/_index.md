---
title: Posizionamento del testo attorno all'immagine nel file PDF
linktitle: Posizionamento del testo attorno all'immagine nel file PDF
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come posizionare il testo attorno alle immagini nei PDF usando Aspose.PDF per .NET. Segui la nostra guida passo passo per creare PDF professionali con immagini e testo affiancati.
type: docs
weight: 260
url: /it/net/programming-with-text/placing-text-around-image/
---
## Introduzione

Hai mai provato a posizionare del testo attorno a un'immagine in un file PDF ma l'hai trovato impegnativo? Se sì, sei nel posto giusto! Aspose.PDF per .NET semplifica questo processo, consentendoti di posizionare del testo accanto alle immagini con solo poche righe di codice. Che tu stia creando report, documenti o presentazioni, questa funzionalità è un modo fantastico per migliorare il layout del tuo contenuto e renderlo più accattivante visivamente. Oggi, ti mostreremo come utilizzare Aspose.PDF per .NET per posizionare del testo attorno alle immagini in un documento PDF.

## Prerequisiti

Prima di buttarci nel codice, assicuriamoci di aver impostato tutto. Ecco cosa ti servirà:

-  Aspose.PDF per .NET: puoi scaricarlo da[Qui](https://releases.aspose.com/pdf/net/).
- Visual Studio: assicurati di avere installata la versione più recente per procedere senza problemi.
- .NET Framework: questo esempio utilizza .NET, quindi assicurati che il tuo ambiente sia configurato per lo sviluppo .NET.
-  Una licenza temporanea: puoi richiedere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/) se stai valutando il prodotto.

Se non hai ancora configurato Aspose.PDF per .NET, segui le istruzioni di installazione in[documentazione](https://reference.aspose.com/pdf/net/).

## Importazione degli spazi dei nomi

Prima di iniziare a scrivere codice, dobbiamo importare i namespace necessari. Ecco il frammento di codice per farlo:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

 Questi namespace sono essenziali in quanto forniscono l'accesso a classi come`Document`, `Page`, `Image` , E`HtmlFragment`, che utilizzeremo per creare e manipolare il PDF.

Ora che abbiamo impostato la scena, analizziamo come posizionare il testo attorno a un'immagine nel tuo file PDF usando Aspose.PDF per .NET. Ti guideremo passo dopo passo.

## Passaggio 1: creare un'istanza dell'oggetto documento

 Per prima cosa, devi creare un documento PDF. In Aspose.PDF, questo viene fatto istanziando un`Document` oggetto. Questo oggetto servirà come base per tutto il contenuto che aggiungeremo.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Qui abbiamo creato un documento PDF vuoto. Non ha ancora pagine, ma non preoccuparti, ne aggiungeremo una nel prossimo passaggio.

## Passaggio 2: aggiungere una pagina al documento

Ora che abbiamo il nostro documento, è il momento di aggiungere una pagina. Immagina di creare un foglio bianco su cui aggiungere il tuo contenuto.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Questo codice aggiunge una nuova pagina al documento. Di default, la pagina è vuota, ma stiamo per cambiarla.

## Passaggio 3: creare una tabella per organizzare i contenuti

Per mantenere la nostra immagine e il testo correttamente allineati, useremo una tabella. Le tabelle nei PDF possono aiutare a strutturare il tuo layout, proprio come nei documenti Word o HTML.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

Questo frammento crea una tabella e la aggiunge alla pagina. Pensa alla tabella come al framework per allineare la tua immagine e il tuo testo.

## Passaggio 4: impostare la larghezza delle colonne per la tabella

Ora che abbiamo aggiunto una tabella, dobbiamo definire quanto devono essere larghe le colonne. Questo assicura che l'immagine e il testo siano dimensionati in modo appropriato sulla pagina.

```csharp
table1.ColumnWidths = "120 270";
```

Questa riga imposta la larghezza di due colonne, una per l'immagine e una per il testo. Regola questi valori se l'immagine o il testo necessitano di più o meno spazio.

## Passaggio 5: definire margini e spaziatura

Per assicurarci che tutto sia in ordine, aggiungiamo margini e spaziatura alla tabella.

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

Queste impostazioni garantiscono che la spaziatura della tabella sia uniforme, rendendo il contenuto visivamente accattivante.

## Passaggio 6: inserire un'immagine nella tabella

Ora, passiamo alla parte divertente: aggiungere un'immagine. In questo caso, aggiungeremo il logo di Aspose, ma sentiti libero di usare qualsiasi immagine tu voglia.

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

Ecco cosa sta succedendo:
- Carichiamo l'immagine dalla directory specificata.
- Impostiamo l'altezza e la larghezza dell'immagine.
- Infine, aggiungiamo l'immagine alla prima cella della tabella.

## Passaggio 7: aggiungere testo accanto all'immagine

Ora che l'immagine è al suo posto, aggiungiamo del testo accanto. Per questo esempio, useremo testo formattato in HTML per definire lo stile del contenuto.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

Questo blocco aggiunge un titolo e una descrizione stilizzati nella cella accanto all'immagine. Puoi formattare il testo usando tag HTML per una maggiore personalizzazione.

## Passaggio 8: Regola l'allineamento verticale

Di default, il contenuto nelle celle della tabella potrebbe non essere allineato come desideri. In questo caso, vogliamo assicurarci che il testo sia allineato alla parte superiore della cella.

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

In questo modo il testo viene visualizzato nella parte superiore della cella, mantenendo un layout pulito e professionale.

## Passaggio 9: aggiungere altro testo sotto l'immagine e la descrizione

Potresti voler includere più contenuto sotto l'immagine e il testo. Aggiungiamo un'altra riga alla tabella per questo scopo.

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

Qui abbiamo aggiunto un'altra riga con testo aggiuntivo, che si estende su entrambe le colonne per mantenere l'equilibrio nel layout.

## Passaggio 10: Salvare il documento PDF

Infine, dobbiamo salvare il documento in modo da poter visualizzare le modifiche.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

In questo modo il PDF verrà salvato con l'immagine e il testo formattati esattamente come li desideriamo.

## Conclusione

Posizionare il testo attorno alle immagini in un PDF potrebbe sembrare un compito arduo, ma Aspose.PDF per .NET semplifica il processo. Sfruttando tabelle, immagini e testo formattato, puoi creare PDF dall'aspetto professionale con il minimo sforzo. Con solo poche righe di codice, puoi posizionare il contenuto esattamente dove vuoi, dando ai tuoi documenti un aspetto raffinato e ben organizzato.

## Domande frequenti

### Posso usare questo metodo per inserire più immagini con testo?
Sì, basta aggiungere più righe e celle alla tabella per includere immagini e testo aggiuntivi.

### Posso modificare l'allineamento dell'immagine?
Assolutamente! Puoi modificare l'allineamento dell'immagine regolando le proprietà di allineamento della cella.

### Come posso formattare ulteriormente il testo?
 È possibile utilizzare i tag HTML all'interno di`HtmlFragment` oggetto per applicare vari stili come grassetto, corsivo o tipi di carattere diversi.

### Posso controllare la spaziatura tra il testo e l'immagine?
 Sì, utilizzando il`MarginInfo` L'oggetto consente di controllare la spaziatura e i margini tra gli elementi.

### È possibile aggiungere dei link al testo?
 Certamente! Puoi incorporare collegamenti ipertestuali nel testo formattato in HTML utilizzando`<a>` etichetta.