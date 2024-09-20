---
title: Aggiungi Java Script al file PDF
linktitle: Aggiungi file PDF Java Script
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere JavaScript al file PDF utilizzando Aspose.PDF per .NET. Guida dettagliata con tutorial di codice per la creazione di script a livello di documento e di pagina.
type: docs
weight: 10
url: /it/net/programming-with-document/addjavascripttopage/
---
## Introduzione

Ti sei mai chiesto come migliorare i tuoi PDF con elementi interattivi come avvisi pop-up o funzioni di stampa automatica? Bene, buone notizie: puoi farlo! Utilizzando Aspose.PDF per .NET, puoi aggiungere JavaScript ai tuoi documenti PDF senza problemi. Che tu stia automatizzando attività o creando esperienze utente dinamiche, l'incorporamento di JavaScript nei PDF fornisce ai tuoi file quel livello extra di funzionalità.

## Prerequisiti

Prima di passare alla parte di codifica, ci sono alcune cose che dovrai impostare:

-  Aspose.PDF per .NET: Scarica la libreria da[Rilasci di Aspose](https://releases.aspose.com/pdf/net/) o ottenere un[prova gratuita](https://releases.aspose.com/).
- Ambiente di sviluppo: qualsiasi IDE compatibile con .NET come Visual Studio.
- Conoscenze di base del linguaggio C#: questa guida presuppone che tu abbia familiarità con la sintassi di base del linguaggio C#.
-  Patente temporanea (facoltativa): puoi ottenere una[licenza temporanea](https://purchase.aspose.com/temporary-license/) se vuoi evitare limitazioni durante il tuo sviluppo.

## Importa pacchetti

Prima di iniziare a scrivere codice, dovrai importare i namespace necessari dalla libreria Aspose.PDF. Questi namespace ti consentiranno di manipolare i PDF e aggiungere azioni JavaScript facilmente.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Ora che hai importato gli spazi dei nomi corretti, sei pronto per iniziare a scrivere il codice.

## Passaggio 1: carica un PDF esistente

Prima di tutto, devi caricare il documento PDF a cui vuoi aggiungere JavaScript. Questo passaggio prepara il terreno per tutte le modifiche successive. Immagina di avere un PDF che vuoi migliorare con funzionalità dinamiche, come la stampa automatica del documento quando lo apri.

Ecco come puoi caricare il file PDF:

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carica un file PDF esistente
Document doc = new Document(dataDir + "input.pdf");
```

 In questo frammento di codice, stiamo utilizzando il`Document` classe per caricare un file PDF esistente dalla directory specificata. Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo del file PDF.

## Passaggio 2: aggiungere JavaScript a livello di documento

Ora, aggiungiamo un po' di JavaScript che si attiverà quando si apre il documento. In questo esempio, scriveremo uno script che apre la finestra di dialogo di stampa non appena l'utente apre il PDF.

Il JavaScript a livello di documento è perfetto per le azioni che vuoi applicare all'intero PDF. Immagina di impostare una regola globale per il tuo documento.

Ecco il codice:

```csharp
// Aggiungere JavaScript a livello di documento
// Crea un'istanza di JavascriptAction con l'istruzione JavaScript desiderata
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Assegna l'oggetto JavascriptAction all'OpenAction del Documento
doc.OpenAction = javaScript;
```

 In questo passaggio creiamo un`JavascriptAction` oggetto che definisce una funzione JavaScript per aprire la finestra di dialogo di stampa quando il documento viene aperto.`doc.OpenAction` alla proprietà viene quindi assegnata questa azione JavaScript.

## Passaggio 3: aggiungere JavaScript a livello di pagina

Non tutte le azioni devono avere effetto sull'intero documento. A volte, vuoi che azioni specifiche si verifichino quando determinate pagine vengono aperte o chiuse. Qui, imposteremo azioni JavaScript per quando una pagina specifica (diciamo la pagina 2) viene aperta e chiusa.

Il JavaScript a livello di pagina è utile per interazioni mirate. Potrebbe essere qualsiasi cosa, dalla visualizzazione di un messaggio quando un utente naviga verso una pagina, ad azioni personalizzate come il riempimento automatico dei campi del modulo.

Ecco come fare:

```csharp
// Aggiungere JavaScript a livello di pagina
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('Page 2 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('Page 2 closed')");
```

In questo frammento di codice aggiungiamo due azioni JavaScript:
1. Azione OnOpen: visualizza un avviso con il messaggio "Pagina 2 aperta" quando l'utente apre la pagina 2.
2. Azione OnClose: visualizza un avviso con il messaggio "Pagina 2 chiusa" quando l'utente esce dalla pagina 2.

Questo aggiunge un livello di interattività al tuo PDF. Immagina di guidare l'utente attraverso una serie di passaggi su diverse pagine, con avvisi che compaiono quando entra o esce da una pagina.

## Passaggio 4: Salvare il documento PDF

Ora hai aggiunto JavaScript sia al documento che a pagine specifiche. Il passaggio finale è salvare il PDF modificato nella posizione desiderata. Questa parte è semplice ma cruciale: non dimenticare di salvare il tuo lavoro!

Ecco il codice:

```csharp
// Specificare il percorso del file di output
dataDir = dataDir + "JavaScript-Added_out.pdf";

// Salva il documento PDF aggiornato
doc.Save(dataDir);

Console.WriteLine("\nJavaScript added successfully to the PDF.\nFile saved at " + dataDir);
```

 In questo frammento, salviamo il documento aggiornato con il JavaScript aggiunto in un nuovo file denominato`"JavaScript-Added_out.pdf"`In questo modo sarai sicuro di non sovrascrivere il file originale e avrai a disposizione un backup su cui lavorare.

## Conclusione

Aggiungere JavaScript ai file PDF usando Aspose.PDF per .NET è un modo potente per creare PDF interattivi e dinamici. Che tu stia automatizzando attività come la stampa o creando avvisi personalizzati, la possibilità di incorporare JavaScript nel tuo PDF rende i tuoi documenti più coinvolgenti e funzionali.

## Domande frequenti

### Posso aggiungere più azioni JavaScript a pagine diverse di un PDF?
Sì, puoi assegnare diverse azioni JavaScript a singole pagine o all'intero documento.

### È possibile rimuovere JavaScript da un PDF dopo averlo aggiunto?
Sì, puoi rimuovere o modificare le azioni JavaScript esistenti cancellando il`Actions` proprietà del documento o della pagina.

### Quali tipi di funzioni JavaScript posso utilizzare in un PDF?
È possibile utilizzare qualsiasi codice JavaScript supportato dal motore JavaScript di Adobe Acrobat, ad esempio per la stampa, gli avvisi e la manipolazione dei moduli.

### JavaScript funziona in tutti i visualizzatori PDF?
La maggior parte delle azioni JavaScript funzionerà nei visualizzatori PDF che supportano PDF interattivi, come Adobe Acrobat. Tuttavia, alcuni lettori PDF di base potrebbero non supportare JavaScript.

### Posso attivare azioni JavaScript in base all'input dell'utente nel PDF?
Sì, puoi associare JavaScript ai campi del modulo per attivare azioni in base all'input dell'utente.