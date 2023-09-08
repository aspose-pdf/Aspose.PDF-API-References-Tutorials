---
title: Allineamento del testo per il contenuto della casella mobile nel file PDF
linktitle: Allineamento del testo per il contenuto della casella mobile nel file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Scopri come allineare il testo all'interno di caselle mobili nel file PDF utilizzando Aspose.PDF per .NET.
type: docs
weight: 520
url: /it/net/programming-with-text/text-alignment-for-floating-box-contents/
---
Questo tutorial spiega come allineare il testo all'interno di caselle mobili nel file PDF utilizzando Aspose.PDF per .NET. Il codice sorgente C# fornito illustra il processo passo dopo passo.

## Prerequisiti

Prima di procedere con il tutorial, assicurati di avere quanto segue:

- Conoscenza base del linguaggio di programmazione C#.
- Aspose.PDF per la libreria .NET installata. Puoi ottenerlo dal sito Web Aspose o utilizzare NuGet per installarlo nel tuo progetto.

## Passaggio 1: impostare il progetto

Inizia creando un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET.

## Passaggio 2: importa gli spazi dei nomi necessari

Aggiungi le seguenti direttive using all'inizio del file C# per importare gli spazi dei nomi richiesti:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Passaggio 3: impostare il percorso della directory dei documenti

 Imposta il percorso della directory dei documenti utilizzando il file`dataDir` variabile:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 4: crea un nuovo documento

 Creane uno nuovo`Document` oggetto:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## Passaggio 5: crea caselle mobili con frammenti di testo

 Crea multipli`FloatingBox` oggetti con diversi allineamenti verticali e allineamenti orizzontali:

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);

Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);

Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

 Modifica il testo e lo stile del file`TextFragment` oggetti come desiderato.

## Passaggio 6: salva il documento PDF

Salvare il documento PDF modificato:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 Assicurati di sostituire`"FloatingBox_alignment_review_out.pdf"` con il nome del file di output desiderato.

### Codice sorgente di esempio per l'allineamento del testo per il contenuto della casella mobile utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

## Conclusione

Congratulazioni! Hai imparato con successo come allineare il testo all'interno di caselle mobili in un documento PDF utilizzando Aspose.PDF per .NET. Questo tutorial ha fornito una guida passo passo, dall'impostazione del progetto al salvataggio del documento modificato. Ora puoi incorporare questo codice nei tuoi progetti C# per personalizzare l'allineamento del testo all'interno delle caselle mobili nei file PDF.

### Domande frequenti

#### D: Qual è lo scopo del tutorial "Allineamento del testo per i contenuti delle caselle mobili nel file PDF"?

R: Il tutorial "Allineamento del testo per i contenuti delle caselle mobili nel file PDF" mira a guidare gli utenti su come allineare il testo all'interno delle caselle mobili in un documento PDF utilizzando Aspose.PDF per .NET. L'esercitazione fornisce istruzioni dettagliate ed esempi di codice C# per dimostrare il processo.

#### D: In che modo questo tutorial aiuta ad allineare il testo all'interno delle caselle mobili?

R: Questo tutorial aiuta gli utenti a capire come utilizzare Aspose.PDF per .NET per allineare il testo all'interno di caselle mobili in un documento PDF. Seguendo i passaggi forniti e gli esempi di codice, gli utenti possono personalizzare l'allineamento verticale e orizzontale del testo all'interno delle caselle mobili.

#### D: Quali prerequisiti sono richiesti per seguire questo tutorial?

R: Prima di iniziare il tutorial, dovresti avere una conoscenza di base del linguaggio di programmazione C#. Inoltre, è necessario che sia installata la libreria Aspose.PDF per .NET. È possibile ottenerlo dal sito Web Aspose o installarlo nel progetto utilizzando NuGet.

#### D: Come posso impostare il mio progetto per seguire questo tutorial?

R: Per iniziare, crea un nuovo progetto C# nel tuo ambiente di sviluppo integrato (IDE) preferito e aggiungi un riferimento alla libreria Aspose.PDF per .NET. Ciò consente di sfruttare le funzionalità della libreria per lavorare con documenti PDF e allineare il testo all'interno di caselle mobili.

#### D: Posso utilizzare questo tutorial per allineare il testo all'interno di qualsiasi tipo di casella mobile?

R: Sì, questo tutorial fornisce istruzioni su come allineare il testo all'interno di caselle mobili in un documento PDF utilizzando Aspose.PDF per .NET. È possibile utilizzare gli esempi di codice forniti per personalizzare l'allineamento verticale e orizzontale del testo all'interno delle caselle mobili.

#### D: Come posso specificare l'allineamento del testo all'interno di una casella mobile?

 R: Il tutorial mostra come creare`FloatingBox`oggetti e impostare il loro`VerticalAlignment` E`HorizontalAlignment` proprietà per controllare l'allineamento del testo contenuto. È possibile modificare queste proprietà in base alle proprie esigenze.

#### D: Come posso personalizzare l'aspetto delle caselle mobili?

 R: Puoi personalizzare l'aspetto delle caselle mobili modificando proprietà come il bordo, le dimensioni e il contenuto del testo. L'esercitazione fornisce esempi di codice che dimostrano come creare e definire lo stile del file`FloatingBox` oggetti.

#### D: Posso aggiungere più caselle mobili con allineamenti diversi nello stesso documento PDF?

 R: Sì, il tutorial illustra come crearne multipli`FloatingBox` oggetti con allineamenti verticali e orizzontali diversi e aggiungerli allo stesso documento PDF. Ciò consente di vedere gli effetti di vari allineamenti all'interno dello stesso documento.

#### D: Come posso salvare il documento PDF modificato?

 R: Per salvare il documento PDF modificato, puoi utilizzare il file`Save` metodo del`Document` oggetto. L'esercitazione fornisce esempi di codice che dimostrano come salvare il documento PDF risultante.