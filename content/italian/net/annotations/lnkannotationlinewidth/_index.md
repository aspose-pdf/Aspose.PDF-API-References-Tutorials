---
title: Larghezza della linea di annotazione lnk
linktitle: Larghezza della linea di annotazione lnk
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come impostare la larghezza della linea di annotazione a penna in un PDF usando Aspose.PDF per .NET. Questo tutorial dettagliato ti guida attraverso ogni passaggio, assicurando un output di alta qualità.
type: docs
weight: 110
url: /it/net/annotations/lnkannotationlinewidth/
---
## Introduzione

Quando si lavora con documenti PDF, aggiungere annotazioni può essere un modo potente per evidenziare informazioni o aggiungere elementi interattivi ai file. Una di queste annotazioni è Ink Annotation, che consente di disegnare linee libere sul PDF. Ma cosa succede se è necessario personalizzare l'aspetto di queste linee, in particolare la larghezza della linea? In questo tutorial, ti guideremo attraverso il processo di impostazione della larghezza della linea di annotazione a inchiostro utilizzando Aspose.PDF per .NET.

## Prerequisiti

Prima di immergerci nel codice, assicuriamoci di aver impostato tutto per seguire questo tutorial senza problemi:

1.  Aspose.PDF per .NET: assicurati di avere installata la libreria Aspose.PDF per .NET. Puoi scaricarla da[pagina di download](https://releases.aspose.com/pdf/net/) oppure installarlo tramite NuGet Package Manager in Visual Studio.
2. Ambiente di sviluppo: questo tutorial presuppone che tu stia lavorando in un ambiente di sviluppo .NET come Visual Studio.
3. Conoscenza di base di C#: una conoscenza di base di C# ti aiuterà a seguire i passaggi della codifica.
4. Documento PDF: per questo tutorial puoi utilizzare un documento PDF esistente oppure crearne uno nuovo.

## Importazione degli spazi dei nomi necessari

Prima di iniziare a scrivere il codice, assicurati di importare gli spazi dei nomi necessari nel tuo progetto:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

Questi namespace forniscono le classi e i metodi necessari per manipolare i documenti PDF, lavorare con le annotazioni e gestire gli elementi grafici.

Ora che abbiamo definito i prerequisiti, scomponiamo il processo di impostazione della larghezza della linea di annotazione a penna in passaggi chiari e gestibili.

## Passaggio 1: inizializzare il documento PDF

Per prima cosa, dobbiamo creare o aprire un documento PDF. Per questo tutorial, creeremo un nuovo documento PDF da zero.

```csharp
// Inizializzare il documento PDF
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Specifica la directory dei tuoi documenti
Document doc = new Document();
doc.Pages.Add(); // Aggiungere una pagina vuota al documento
```

 Qui, stiamo inizializzando un nuovo`Document` oggetto, che rappresenta il nostro file PDF. Aggiungiamo quindi una pagina vuota a questo documento per lavorare.

## Passaggio 2: creare l'annotazione a inchiostro

Successivamente, creeremo l'annotazione a inchiostro vera e propria. Ciò implica la definizione dei punti che compongono i tratti a inchiostro.

```csharp
// Crea l'annotazione a inchiostro
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

 In questo passaggio definiamo il`LineInfo` oggetto, che contiene le coordinate dei tratti di inchiostro, la loro visibilità, colore e larghezza iniziale della linea.`VerticeCoordinate` array contiene le coordinate X e Y di ciascun punto del tratto.

## Passaggio 3: convertire le coordinate in punti

Ora dobbiamo convertire queste coordinate in punti che possano essere utilizzati dall'annotazione a inchiostro.

```csharp
// Convertire le coordinate in punti
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

 Questo ciclo elabora la matrice di coordinate, convertendo ogni coppia di coordinate in un`Point` oggetto, che viene poi aggiunto al nostro`inkList`.

## Passaggio 4: aggiungere l'annotazione a inchiostro alla pagina PDF

Una volta pronti i punti, possiamo creare l'annotazione a inchiostro e aggiungerla alla pagina PDF.

```csharp
// Aggiungere l'annotazione a inchiostro alla pagina PDF
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

 In questo passaggio, inizializziamo un`InkAnnotation`object, specificando la pagina, un rettangolo di delimitazione e il nostro elenco di punti. Impostiamo anche l'oggetto, il titolo e il colore dell'annotazione.

## Passaggio 5: personalizzare il bordo dell'annotazione

Per personalizzare ulteriormente l'aspetto della nostra annotazione, modificheremo le proprietà del bordo.

```csharp
// Personalizza il bordo dell'annotazione
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

 Qui creiamo un`Border` oggetto per la nostra annotazione, impostandone larghezza, effetto, schema di tratteggio e stile. Questo passaggio assicura che l'annotazione risalti visivamente sulla pagina PDF.

## Passaggio 6: Salvare il documento PDF

Infine, dopo aver apportato tutte le modifiche necessarie, è il momento di salvare il documento.

```csharp
// Salva il documento PDF
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

 Questo codice salva il documento PDF modificato con l'annotazione a inchiostro nella directory specificata.`Console.WriteLine` L'istruzione conferma l'esecuzione corretta del codice.

## Conclusione

Congratulazioni! Hai creato e personalizzato con successo un'annotazione a inchiostro in un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha coperto l'intero processo, dall'inizializzazione del documento al salvataggio del file finale. Con questa conoscenza, puoi esplorare ulteriormente le vaste capacità di Aspose.PDF per .NET e applicare tecniche simili ad altri tipi di annotazioni o manipolazioni PDF.

## Domande frequenti

### Posso usare colori diversi per le diverse parti dell'annotazione a inchiostro?  
 Sì, puoi crearne più di uno`InkAnnotation` oggetti con colori diversi e aggiungerli alla stessa pagina o a pagine diverse del PDF.

### Come posso modificare dinamicamente la larghezza della linea?  
 Puoi regolare il`LineWidth` proprietà del`LineInfo` oggetto prima di convertire le coordinate in punti.

### È possibile rendere trasparente l'annotazione a inchiostro?  
 Sì, puoi modificare il`Opacity` proprietà del`InkAnnotation` oggetto per renderlo trasparente.

### Posso aggiungere più annotazioni a penna sulla stessa pagina?  
Assolutamente! Puoi aggiungere tutte le annotazioni a inchiostro che vuoi a una singola pagina ripetendo il procedimento.

### Come faccio a rimuovere un'annotazione a mano da un PDF?  
 È possibile rimuovere un'annotazione utilizzando`doc.Pages[1].Annotations.Delete(a1)` metodo, dove`a1` è il tuo oggetto di annotazione.