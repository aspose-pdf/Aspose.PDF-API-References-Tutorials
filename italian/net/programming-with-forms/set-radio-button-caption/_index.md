---
title: Imposta la didascalia del pulsante di opzione
linktitle: Imposta la didascalia del pulsante di opzione
second_title: Aspose.PDF per riferimento API .NET
description: Scopri come utilizzare Aspose.PDF per .NET per impostare la didascalia per un pulsante di opzione in un modulo PDF.
type: docs
weight: 280
url: /it/net/programming-with-forms/set-radio-button-caption/
---
In questa guida, spiegheremo passo dopo passo come utilizzare la libreria Aspose.PDF per .NET per definire la didascalia di un pulsante di opzione in un modulo PDF. Ti mostreremo come accedere al campo del pulsante di opzione, creare una nuova opzione del pulsante di opzione e personalizzare la didascalia del pulsante.

## Passaggio 1: configurazione della directory dei documenti

 Il primo passaggio consiste nel configurare la directory dei documenti in cui si trova il modulo PDF su cui si desidera lavorare. Puoi usare il`dataDir` variabile per specificare il percorso della directory.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 2: caricamento del modulo PDF di origine

 In questo passaggio, caricheremo il modulo PDF di origine utilizzando il file`Aspose.Pdf.Facades.Form` classe di Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Assicurarsi che il file PDF contenente il modulo sia presente nella directory dei documenti specificata.

## Passaggio 3: modifica della didascalia del pulsante di opzione

Passeremo in rassegna i nomi dei campi del modulo e cercheremo i campi dei pulsanti di opzione. Se viene trovato un campo corrispondente, creeremo una nuova opzione del pulsante di opzione con una didascalia personalizzata e la aggiungeremo al campo esistente.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// Crea un oggetto TextParagraph
TextParagraph par = new TextParagraph();
// Imposta la posizione del paragrafo
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Specifica la modalità a capo automatico
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Aggiungi il nuovo TextFragment al paragrafo
par.AppendLine(updatedFragment);
// Aggiungi il TextParagraph usando TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Personalizza il pulsante di opzione della didascalia e altre impostazioni secondo necessità.

## Passaggio 4: salvare il PDF risultante

 Ora che abbiamo finito di modificare la didascalia del pulsante di opzione, possiamo salvare il PDF risultante utilizzando il file`Save` metodo del`Document` classe.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Assicurati di specificare il percorso completo e il nome del file per il PDF risultante.

### Esempio di codice sorgente per Set Radio Button Caption utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carica il modulo PDF di origine
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// Crea un oggetto TextParagraph
		TextParagraph par = new TextParagraph();
		// Imposta la posizione del paragrafo
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Specifica la modalità di a capo automatico
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Aggiungi un nuovo TextFragment al paragrafo
		par.AppendLine(updatedFragment);
		// Aggiungi il TextParagraph usando TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Conclusione

In questa guida, abbiamo imparato come utilizzare la libreria Aspose.PDF per .NET per impostare la didascalia per un pulsante di opzione in un modulo PDF. Seguendo i passaggi descritti, è possibile personalizzare le opzioni del pulsante di opzione e modificare la didascalia secondo necessità. Sentiti libero di esplorare ulteriormente le funzionalità di Aspose.PDF per .NET per espandere le possibilità di manipolazione dei file PDF.

### FAQ

#### D: Posso utilizzare Aspose.PDF per .NET per impostare didascalie per i pulsanti di opzione in un modulo PDF?

R: Sì, puoi utilizzare Aspose.PDF per .NET per impostare le didascalie per i pulsanti di opzione in un modulo PDF. Il codice sorgente di esempio fornito mostra come accedere al campo del pulsante di opzione, creare una nuova opzione del pulsante di opzione con una didascalia personalizzata e aggiornare il campo esistente.

#### D: Come posso personalizzare l'aspetto della didascalia del pulsante di opzione, ad esempio la dimensione del carattere e il colore?

 R: Puoi personalizzare l'aspetto della didascalia del pulsante di opzione regolando le proprietà del`TextFragment` utilizzato per la didascalia. Ad esempio, puoi impostare il carattere, la dimensione del carattere, il colore, l'interlinea e altre opzioni di formattazione del testo.

#### D: È possibile aggiungere più opzioni di pulsanti di opzione con didascalie diverse a un singolo gruppo di pulsanti di opzione?

R: Sì, puoi aggiungere più pulsanti di opzione con didascalie diverse a un singolo gruppo di pulsanti di opzione. Ogni opzione rappresenterà una scelta diversa e gli utenti possono selezionare solo un'opzione dal gruppo.

#### D: Posso utilizzare Aspose.PDF per .NET per modificare altri campi modulo in un documento PDF?

A: Sì, Aspose.PDF per .NET offre un set completo di funzionalità per manipolare vari campi modulo in un documento PDF, come campi di testo, caselle di controllo, elenchi a discesa e altro. È possibile utilizzare la libreria per impostare valori, modificare aspetti e aggiungere interattività ai campi modulo.

#### D: Aspose.PDF per .NET supporta il lavoro con PDF generati da altre fonti, come documenti scansionati?

R: Sì, Aspose.PDF per .NET supporta il lavoro con PDF generati da varie fonti, compresi i documenti scansionati. La libreria fornisce funzionalità OCR (Optical Character Recognition) per estrarre il testo dai PDF scansionati e manipolare il contenuto in modo programmatico.