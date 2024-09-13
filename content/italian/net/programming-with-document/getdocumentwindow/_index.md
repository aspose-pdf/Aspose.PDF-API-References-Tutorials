---
title: Ottieni finestra documento
linktitle: Ottieni finestra documento
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come utilizzare la funzionalità GetDocumentWindow di Aspose.PDF per .NET per recuperare informazioni sulle proprietà della finestra di un documento PDF.
type: docs
weight: 170
url: /it/net/programming-with-document/getdocumentwindow/
---
# Introduzione

Stai lavorando con i PDF e vuoi avere più controllo su come appaiono quando vengono aperti? Che si tratti di nascondere la barra dei menu o di ridimensionare la finestra per adattarla alla prima pagina, Aspose.PDF per .NET ti offre tutti gli strumenti necessari per personalizzare il comportamento di un PDF quando viene aperto in un visualizzatore. In questo tutorial, spiegheremo come recuperare e manipolare le impostazioni della finestra del documento in Aspose.PDF per .NET.


# Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

- Aspose.PDF per .NET installato nel tuo ambiente di sviluppo.
  - [Scarica Aspose.PDF per .NET](https://releases.aspose.com/pdf/net/)
-  Una licenza valida per Aspose.PDF, oppure puoi ottenere una[prova gratuita](https://releases.aspose.com/) O[licenza temporanea](https://purchase.aspose.com/temporary-license/).
- Conoscenza di base di .NET e C#.
- Visual Studio o un altro IDE idoneo.

# Importa pacchetti

Prima di iniziare a scrivere qualsiasi codice, dovrai importare i pacchetti necessari. Apri il tuo progetto e, in cima al tuo file C#, aggiungi il seguente namespace:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Questo ti darà accesso a tutte le classi e ai metodi necessari per manipolare documenti PDF utilizzando Aspose.PDF per .NET.

 Ora analizziamo il processo di recupero delle diverse impostazioni della finestra del documento. Per questo esempio, useremo un file PDF di esempio denominato`GetDocumentWindow.pdf`.

## Passaggio 1: impostare il percorso della directory dei documenti

Per prima cosa, dobbiamo definire il percorso del nostro file PDF. È fondamentale che tu abbia il percorso file corretto per evitare errori durante l'esecuzione.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Qui, sostituisci`"YOUR DOCUMENT DIRECTORY"` con la directory effettiva in cui si trova il tuo file PDF. Questa è la tua directory di lavoro da cui caricherai il documento PDF.

## Passaggio 2: aprire il documento PDF

Ora che il percorso del file è impostato, il passo successivo è aprire il documento PDF usando Aspose.PDF. Questo caricherà il documento in memoria, consentendoti di recuperarne le proprietà.

```csharp
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

Con questa semplice riga di codice, hai caricato con successo il tuo file PDF nel`pdfDocument` oggetto, che ora ti consentirà di accedere a tutte le sue proprietà.

## Passaggio 3: recuperare lo stato di centratura della finestra

 Ora, controlliamo se la finestra del documento deve essere centrata quando viene aperta. Il valore predefinito per questo è`false`.

```csharp
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
```

 Se l'uscita è`true`, la finestra del documento si aprirà al centro dello schermo. Altrimenti, si aprirà nella sua posizione predefinita.

## Passaggio 4: controllare la direzione del testo

Un altro aspetto cruciale dell'aspetto di un PDF è la direzione del testo, che determina se il testo viene letto da sinistra a destra (L2R) o da destra a sinistra (R2L). Puoi recuperare questa informazione usando il seguente codice:

```csharp
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
```

 L'output sarà`L2R` per il testo da sinistra a destra e`R2L` per testo da destra a sinistra. Questa impostazione è particolarmente utile per documenti in lingue come l'arabo o l'ebraico.

## Passaggio 5: visualizzare il titolo del documento nella finestra

La proprietà successiva consente di controllare se il titolo del documento o il nome del file debbano essere visualizzati sulla barra del titolo della finestra. Per impostazione predefinita, è impostato su`false`, il che significa che verrà visualizzato il nome del file.

```csharp
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
```

Se si desidera che venga visualizzato il titolo del documento anziché il nome del file, è necessario abilitare questa impostazione.

## Passaggio 6: ridimensionare la finestra per adattarla alla prima pagina

A volte, potresti voler ridimensionare automaticamente la finestra del documento per adattarla alla prima pagina del PDF quando viene aperto. Ecco come verificare se questa funzionalità è abilitata:

```csharp
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
```

 Per impostazione predefinita, questa impostazione è impostata su`false`, il che significa che le dimensioni della finestra rimarranno invariate indipendentemente dalle dimensioni della prima pagina.

## Passaggio 7: nascondere la barra dei menu

Per un'esperienza di lettura più mirata, potresti voler nascondere la barra dei menu dell'applicazione viewer. Puoi recuperare questa impostazione usando la seguente riga:

```csharp
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
```

 Questo tornerà`true` se la barra dei menu è nascosta, e`false` Altrimenti.

## Passaggio 8: nascondere la barra degli strumenti

Allo stesso modo, potresti anche voler nascondere la barra degli strumenti nel visualizzatore PDF per un'interfaccia utente più pulita. Questa impostazione può essere recuperata come segue:

```csharp
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
```

Se questa impostazione è abilitata, la barra degli strumenti verrà nascosta quando il PDF viene aperto.

## Passaggio 9: nascondere le barre di scorrimento e gli elementi dell'interfaccia utente

Se desideri visualizzare solo il contenuto della pagina senza elementi aggiuntivi dell'interfaccia utente come le barre di scorrimento, questa impostazione controlla tale comportamento:

```csharp
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
```

 Quando impostato su`true`, il visualizzatore PDF nasconderà le barre di scorrimento e altri elementi dell'interfaccia utente, lasciando solo il contenuto del documento.

## Passaggio 10: Imposta la modalità di pagina non a schermo intero

 È possibile controllare l'aspetto del documento quando si esce dalla modalità a schermo intero utilizzando`NonFullScreenPageMode` proprietà. Questa impostazione è utile per definire come l'utente deve interagire con il documento in modalità non a schermo intero.

```csharp
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
```

L'output può essere impostato su diverse modalità, come miniature, contorni o pannello allegati.

## Passaggio 11: definire il layout della pagina

Questa impostazione ti consente di controllare il modo in cui sono disposte le pagine del documento. Ad esempio, puoi optare per una visualizzazione a pagina singola o una visualizzazione a colonna continua:

```csharp
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
```

Ciò offre agli utenti flessibilità nel modo in cui leggono o visualizzano il contenuto del documento.

## Passaggio 12: specificare la modalità pagina

 Infine, il`PageMode` proprietà definisce come il documento deve essere visualizzato quando viene aperto. Le opzioni includono la visualizzazione delle miniature, l'ingresso in modalità a schermo intero o la visualizzazione del pannello degli allegati.

```csharp
Console.WriteLine("PageMode : {0}", pdfDocument.PageMode);
```

A seconda delle tue esigenze, puoi impostare la modalità più adatta allo scopo del tuo PDF.

## Conclusione

Come puoi vedere, Aspose.PDF per .NET fornisce strumenti completi per manipolare il modo in cui i tuoi documenti PDF vengono visualizzati in vari visualizzatori PDF. Che tu voglia nascondere la barra degli strumenti, centrare la finestra o controllare la direzione del testo, Aspose.PDF offre la flessibilità per migliorare l'esperienza di visualizzazione dell'utente.

# Domande frequenti

### Posso personalizzare il livello di zoom iniziale del PDF?
Sì, Aspose.PDF consente di impostare il livello di zoom quando il documento è aperto.

### Come posso bloccare le dimensioni della finestra di un PDF?
 Puoi impostare il`FitWindow` proprietà per impedire il ridimensionamento della finestra.

### Aspose.PDF supporta diverse modalità di lettura?
Sì, supporta diverse modalità, come schermo intero, miniature e allegati.

### È possibile nascondere le barre di scorrimento nel visualizzatore PDF?
 Assolutamente, puoi nascondere le barre di scorrimento impostando`HideWindowUI` proprietà a`true`.

### Posso centrare la finestra del documento quando è aperta?
 Sì, puoi controllarlo impostando`CenterWindow` proprietà.