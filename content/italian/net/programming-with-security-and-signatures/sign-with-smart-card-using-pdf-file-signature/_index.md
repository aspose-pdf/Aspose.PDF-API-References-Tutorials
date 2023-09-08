---
title: Firma con la smart card utilizzando la firma del file PDF
linktitle: Firma con la smart card utilizzando la firma del file PDF
second_title: Aspose.PDF per riferimento all'API .NET
description: Firma i tuoi file PDF in modo sicuro con una smart card utilizzando Aspose.PDF per .NET.
type: docs
weight: 110
url: /it/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
La firma digitale con una smart card è un modo sicuro per firmare file PDF. Con Aspose.PDF per .NET, puoi firmare facilmente un file PDF utilizzando una smart card seguendo il seguente codice sorgente:

## Passaggio 1: importa le librerie richieste

Prima di iniziare, devi importare le librerie necessarie per il tuo progetto C#. Ecco le direttive di importazione necessarie:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Passaggio 2: imposta il percorso della cartella dei documenti

 In questo passaggio, devi specificare il percorso della cartella contenente il file PDF che desideri firmare. Sostituire`"YOUR DOCUMENTS DIRECTORY"`nel seguente codice con il percorso effettivo della cartella dei documenti:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 3: carica il documento PDF

Ora caricheremo il documento PDF da firmare utilizzando il seguente codice:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Passaggio 4: eseguire la firma con la smart card

 In questo passaggio eseguiremo la firma con la smart card utilizzando il file`PdfFileSignature` classe da`Facades`biblioteca. Selezioniamo il certificato della smart card dall'archivio certificati di Windows e specifichiamo le informazioni di firma necessarie. Ecco il codice corrispondente:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Seleziona il certificato nel negozio
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## Passaggio 5: verifica la firma

 Infine, verifichiamo la firma del file PDF firmato utilizzando il file`PdfFileSignature` classe. Otteniamo i nomi delle firme e li controlliamo uno per uno. Se una firma non supera la verifica, viene generata un'eccezione. Ecco il codice corrispondente:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### Codice sorgente di esempio per Firma con smart card utilizzando la firma del file Pdf utilizzando Aspose.PDF per .NET 
```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Accedi con la selezione del certificato nell'archivio certificati di Windows
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Scegli manualmente il certificato nel negozio
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
	IList<string> sigNames = pdfSign.GetSignNames();
	for (int index = 0; index <= sigNames.Count - 1; index++)
	{
		if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
		{
			throw new ApplicationException("Not verified");
		}
	}
}
```

## Conclusione

Congratulazioni! Ora hai una guida passo passo per firmare un file PDF con una smart card utilizzando Aspose.PDF per .NET. Puoi utilizzare questo codice per aggiungere firme digitali sicure ai tuoi documenti PDF.

Assicurati di controllare la documentazione ufficiale Aspose.PDF per ulteriori informazioni sulla firma digitale avanzata e sulle funzionalità di gestione dei certificati.

### Domande frequenti

#### D: Perché dovrei prendere in considerazione la firma dei file PDF con una smart card?

R: La firma di file PDF con una smart card aumenta la sicurezza garantendo l'autenticità e l'integrità del documento. Le firme basate su smart card forniscono un livello più elevato di affidabilità e conformità.

#### D: Come funziona la firma digitale basata su smart card?

R: La firma digitale basata su smart card prevede l'utilizzo di una chiave crittografica archiviata su una smart card per creare una firma digitale univoca. Questa firma è allegata al file PDF, consentendo ai destinatari di verificare l'origine e l'integrità del documento.

#### D: Qual è il ruolo di Aspose.PDF per .NET nella firma basata su smart card?

R: Aspose.PDF per .NET fornisce un set completo di strumenti e librerie per facilitare la firma digitale dei file PDF basata su smart card. Semplifica il processo e garantisce la firma sicura dei documenti.

#### D: Posso scegliere un certificato smart card specifico per la firma?

R: Sì, puoi selezionare un certificato smart card specifico dall'archivio certificati di Windows per la firma. Aspose.PDF per .NET ti consente di integrare perfettamente la selezione del certificato nella tua applicazione.

#### D: In che modo il codice sorgente fornito gestisce la firma basata su smart card?

R: Il codice sorgente mostra come associare un documento PDF, selezionare un certificato di smart card, specificare le informazioni sulla firma e creare una firma digitale. Mostra anche come verificare la validità della firma.

#### D: Posso applicare più firme utilizzando le smart card in un singolo file PDF?

R: Assolutamente sì, puoi applicare più firme basate su smart card a un singolo file PDF. Ogni firma è unica e contribuisce alla sicurezza generale del documento.

#### D: Cosa succede se una firma non supera la verifica durante la fase di verifica?

R: Se una firma non supera la verifica, viene generata un'eccezione che indica che la firma non è valida. Ciò garantisce che vengano accettate solo firme valide e attendibili.

#### D: La firma basata su smart card è compatibile con tutti i tipi di documenti PDF?

R: Sì, la firma basata su smart card è compatibile con tutti i tipi di documenti PDF. Puoi applicare firme digitali a vari tipi di file PDF, inclusi moduli, report e altro.

#### D: Come posso ottenere ulteriori informazioni sulla firma digitale avanzata e sulla gestione dei certificati?

R: Esplora la documentazione ufficiale Aspose.PDF per approfondimenti dettagliati sulle funzionalità avanzate di firma digitale, sulla gestione dei certificati e sulle migliori pratiche per garantire la sicurezza dei documenti.

#### D: Dove posso trovare ulteriore assistenza o supporto per l'implementazione della firma basata su smart card?

R: Per ulteriore assistenza e supporto, contattare i forum della community Aspose.PDF o fare riferimento alla documentazione per informazioni complete sulla firma basata su smart card.