---
title: Imposta didascalia pulsante di scelta
linktitle: Imposta didascalia pulsante di scelta
second_title: Riferimento API Aspose.PDF per .NET
description: Scopri come utilizzare Aspose.PDF per .NET per impostare la didascalia per un pulsante di scelta in un modulo PDF.
type: docs
weight: 280
url: /it/net/programming-with-forms/set-radio-button-caption/
---
In questa guida, spiegheremo passo dopo passo come usare la libreria Aspose.PDF per .NET per definire la didascalia di un pulsante di scelta in un modulo PDF. Ti mostreremo come accedere al campo del pulsante di scelta, creare una nuova opzione del pulsante di scelta e personalizzare la didascalia del pulsante.

## Fase 1: Configurazione della directory dei documenti

 Il primo passo è configurare la directory dei documenti in cui si trova il modulo PDF su cui si desidera lavorare. È possibile utilizzare`dataDir` variabile per specificare il percorso della directory.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Assicurati di sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 2: caricamento del modulo PDF di origine

 In questo passaggio, caricheremo il modulo PDF di origine utilizzando`Aspose.Pdf.Facades.Form` classe di Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Assicurarsi che il file PDF contenente il modulo sia presente nella directory dei documenti specificata.

## Passaggio 3: modifica della didascalia del pulsante di scelta

Faremo un ciclo tra i nomi dei campi del modulo e cercheremo i campi dei pulsanti di scelta. Se viene trovato un campo corrispondente, creeremo una nuova opzione del pulsante di scelta con una didascalia personalizzata e la aggiungeremo al campo esistente.

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
// Specificare la modalità di interruzione di parola
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Aggiungere il nuovo TextFragment al paragrafo
par.AppendLine(updatedFragment);
// Aggiungere il TextParagraph utilizzando TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Personalizza il pulsante di scelta della didascalia e altre impostazioni in base alle tue esigenze.

## Passaggio 4: salvataggio del PDF risultante

 Ora che abbiamo finito di modificare la didascalia del pulsante di scelta, possiamo salvare il PDF risultante utilizzando`Save` metodo del`Document` classe.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Assicuratevi di specificare il percorso completo e il nome file del PDF risultante.

### Esempio di codice sorgente per Imposta didascalia del pulsante di scelta utilizzando Aspose.PDF per .NET 
```csharp
// Percorso verso la directory dei documenti.
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
		// Crea oggetto TextParagraph
		TextParagraph par = new TextParagraph();
		// Imposta la posizione del paragrafo
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Specificare la modalità di interruzione di parola
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Aggiungi un nuovo TextFragment al paragrafo
		par.AppendLine(updatedFragment);
		// Aggiungere il TextParagraph utilizzando TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Conclusione

In questa guida, abbiamo imparato come usare la libreria Aspose.PDF per .NET per impostare la didascalia per un pulsante di scelta in un modulo PDF. Seguendo i passaggi descritti, puoi personalizzare le opzioni del pulsante di scelta e modificare la didascalia in base alle tue esigenze. Sentiti libero di esplorare ulteriormente le funzionalità di Aspose.PDF per .NET per espandere le possibilità di manipolazione dei file PDF.

### Domande frequenti

#### D: Posso usare Aspose.PDF per .NET per impostare didascalie per i pulsanti di scelta in un modulo PDF?

R: Sì, puoi usare Aspose.PDF per .NET per impostare le didascalie per i pulsanti di scelta in un modulo PDF. Il codice sorgente di esempio fornito dimostra come accedere al campo del pulsante di scelta, creare una nuova opzione del pulsante di scelta con una didascalia personalizzata e aggiornare il campo esistente.

#### D: Come posso personalizzare l'aspetto della didascalia del pulsante di scelta, ad esempio la dimensione e il colore del carattere?

 A: È possibile personalizzare l'aspetto della didascalia del pulsante di scelta modificando le proprietà del`TextFragment` utilizzato per la didascalia. Ad esempio, puoi impostare il font, la dimensione del font, il colore, l'interlinea e altre opzioni di formattazione del testo.

#### D: È possibile aggiungere più opzioni di pulsanti di scelta con didascalie diverse a un singolo gruppo di pulsanti di scelta?

R: Sì, puoi aggiungere più opzioni di pulsanti di scelta con didascalie diverse a un singolo gruppo di pulsanti di scelta. Ogni opzione rappresenterà una scelta diversa e gli utenti possono selezionare solo un'opzione dal gruppo.

#### D: Posso usare Aspose.PDF per .NET per modificare altri campi modulo in un documento PDF?

R: Sì, Aspose.PDF per .NET fornisce un set completo di funzionalità per manipolare vari campi modulo in un documento PDF, come campi di testo, caselle di controllo, elenchi a discesa e altro. Puoi usare la libreria per impostare valori, modificare l'aspetto e aggiungere interattività ai campi modulo.

#### D: Aspose.PDF per .NET supporta l'utilizzo di file PDF generati da altre fonti, come documenti scansionati?

R: Sì, Aspose.PDF per .NET supporta l'utilizzo di PDF generati da varie fonti, inclusi documenti scansionati. La libreria fornisce funzionalità OCR (Optical Character Recognition) per estrarre testo da PDF scansionati e manipolare il contenuto a livello di programmazione.