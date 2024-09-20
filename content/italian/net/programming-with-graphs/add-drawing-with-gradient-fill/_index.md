---
title: Aggiungi disegno con riempimento sfumato
linktitle: Aggiungi disegno con riempimento sfumato
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come aggiungere splendidi disegni sfumati nei PDF utilizzando Aspose.PDF per .NET con questa guida dettagliata, perfetta per migliorare gli elementi visivi dei documenti.
type: docs
weight: 20
url: /it/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
## Introduzione

Creare documenti visivamente accattivanti è essenziale nel mondo digitale odierno. Una tecnica sorprendente per migliorare i tuoi documenti PDF è quella di aggiungere disegni con riempimenti sfumati. Se stai cercando di migliorare le tue capacità di progettazione di documenti, sei nel posto giusto! In questa guida, ti guiderò attraverso il processo di utilizzo di Aspose.PDF per .NET per aggiungere uno straordinario disegno con riempimento sfumato al tuo PDF.

## Prerequisiti

Prima di addentrarci nei dettagli, ecco alcune cose che devi mettere in atto:

1.  Aspose.PDF per la libreria .NET: assicurati di avere installata la libreria Aspose.PDF. Puoi ottenerla da[collegamento per il download](https://releases.aspose.com/pdf/net/).
2. Ambiente di sviluppo: predisponi un ambiente di sviluppo .NET, come Visual Studio, in cui puoi scrivere ed eseguire il codice.
3. Nozioni di base di C#: la familiarità con la programmazione in C# renderà più semplice seguire il corso.

Una volta soddisfatti i prerequisiti di cui sopra, passiamo all'implementazione!

## Importa pacchetti

Per prima cosa, devi importare i pacchetti richiesti nel tuo progetto. Ecco come fare:

- Apri il tuo progetto C# in Visual Studio.
- Aggiungi un riferimento alla libreria Aspose.PDF. Puoi farlo tramite NuGet Package Manager:
  
```csharp
using Aspose.Pdf.Drawing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ora scomponiamo il processo in passaggi più semplici. 

## Passaggio 1: impostare la directory dei documenti

Per iniziare, dovrai impostare un percorso per i tuoi documenti. Questo ti aiuterà a organizzare dove salvare i file PDF creati.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Sostituisci con il percorso della tua directory
```
 Questa riga di codice stabilisce una variabile`dataDir` , che conterrà il percorso alla directory in cui verrà salvato il PDF di output. Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory.

## Passaggio 2: creare un nuovo documento PDF

Ora creiamo un nuovo documento PDF utilizzando la libreria Aspose.PDF.

```csharp
Document doc = new Document();
```
 Qui, istanziamo un`Document` oggetto. Questo oggetto rappresenta il tuo documento PDF e fungerà da contenitore per tutti gli elementi che intendi aggiungere.

## Passaggio 3: aggiungere una pagina al documento

Ora che il nostro documento è pronto, è il momento di aggiungervi una pagina.

```csharp
Page page = doc.Pages.Add();
```
Questa riga aggiunge una nuova pagina al tuo documento. Fornisce spazio per tutta la grafica e il testo che desideri includere.

## Passaggio 4: creare un oggetto grafico

Per disegnare le forme, dobbiamo prima creare un'area grafica sulla pagina.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300.0, 300.0);
page.Paragraphs.Add(graph);
```
In questo caso, creiamo un oggetto grafico con larghezza e altezza di 300 unità. Aggiungendolo ai paragrafi della pagina, poniamo le basi per i nostri disegni.

## Passaggio 5: definire una forma rettangolare

Ora definiremo una forma rettangolare che vogliamo riempire con un colore sfumato.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```
Qui, creiamo un rettangolo che inizia alle coordinate (0,0) e si estende per 300 unità in larghezza e altezza. Questo rettangolo viene poi aggiunto al nostro oggetto grafico.

## Passaggio 6: applicare il riempimento sfumato al rettangolo

Ora arriva la parte divertente! Applicheremo un riempimento sfumato al nostro rettangolo.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
    PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
    {
        Start = new Point(0, 0),
        End = new Point(300, 300)
    }
};
```
 In questo blocco di codice, stiamo specificando il colore di riempimento del rettangolo come un gradiente dal rosso al blu.`GradientAxialShading`La classe consente la definizione di un riempimento sfumato, in cui è possibile specificare i punti di inizio e fine per creare una transizione graduale tra i colori.

## Passaggio 7: Salvare il documento PDF

Infine, dobbiamo salvare il nostro documento nella directory definita.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```
 Questo comando salva il tuo PDF con un nome specifico nel file precedentemente definito`dataDir`Il risultato è un PDF splendidamente realizzato, caratterizzato da un rettangolo riempito con un gradiente.

## Conclusione

Ed ecco fatto! Hai appena imparato come aggiungere un disegno con riempimento sfumato al tuo documento PDF usando Aspose.PDF per .NET. Non è incredibile come poche righe di codice possano trasformare un semplice PDF in qualcosa di visivamente sorprendente? Che tu stia creando report, fatture o qualsiasi altro documento, l'uso della grafica può migliorare notevolmente l'esperienza del lettore.

## Domande frequenti

### Che cos'è Aspose.PDF per .NET?
Aspose.PDF per .NET è una potente libreria che consente agli sviluppatori di creare e manipolare documenti PDF a livello di programmazione.

### Posso usare Aspose.PDF gratuitamente?
 Puoi iniziare con un[prova gratuita](https://releases.aspose.com/) per esplorarne le funzionalità, ma potrebbero esserci delle limitazioni d'uso.

### Dove posso trovare ulteriore documentazione?
La documentazione dettagliata è disponibile su[Pagina di riferimento PDF di Aspose](https://reference.aspose.com/pdf/net/).

### Come posso acquistare Aspose.PDF?
 Puoi acquistare la libreria Aspose.PDF tramite il loro[link di acquisto](https://purchase.aspose.com/buy).

### Cosa succede se ho bisogno di aiuto nell'uso di Aspose.PDF?
 Se riscontri problemi, puoi cercare aiuto su[Forum di supporto Aspose](https://forum.aspose.com/c/pdf/10).