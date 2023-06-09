---
title: Unterschreiben Sie mit einer Smartcard über das Signaturfeld
linktitle: Unterschreiben Sie mit einer Smartcard über das Signaturfeld
second_title: Aspose.PDF für .NET API-Referenz
description: Signieren Sie Ihre PDF-Dateien sicher mit einer Smartcard mit Aspose.PDF für .NET.
type: docs
weight: 120
url: /de/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---

Das digitale Signieren mit einer Smartcard ist eine sichere Möglichkeit, PDF-Dateien zu signieren. Mit Aspose.PDF für .NET können Sie eine PDF-Datei ganz einfach mithilfe eines Signaturfelds und einer Smartcard signieren, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier sind die notwendigen Importanweisungen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, die Sie signieren möchten. Ersetzen`"YOUR DOCUMENTS DIRECTORY"` Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 3: Kopieren und öffnen Sie das PDF-Dokument

Jetzt kopieren und öffnen wir das zu signierende PDF-Dokument mit dem folgenden Code:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Erstellen Sie ein Signaturfeld
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Wählen Sie das Zertifikat im Store aus
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Erstellen Sie eine externe Signatur mit den notwendigen Informationen
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## Schritt 4: Signatur überprüfen

 Abschließend überprüfen wir die Signatur der signierten PDF-Datei mithilfe von`PdfFileSignature` Klasse. Wir erhalten die Signaturnamen und prüfen sie einzeln. Wenn die Überprüfung einer Signatur fehlschlägt, wird eine Ausnahme ausgelöst. Hier ist der entsprechende Code:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

### Beispielquellcode für Sign With Smart Card Using Signature Field mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Signieren Sie mit der Zertifikatsauswahl im Windows-Zertifikatspeicher
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Wählen Sie das Zertifikat manuell im Store aus
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

## Abschluss

Herzlichen Glückwunsch! Sie haben jetzt eine Schritt-für-Schritt-Anleitung zum Signieren einer PDF-Datei mit einer Smartcard mithilfe eines Signaturfelds mit Aspose.PDF für .NET. Mit diesem Code können Sie Ihren PDF-Dokumenten sichere digitale Signaturen hinzufügen.

Weitere Informationen zu erweiterten digitalen Signatur- und Zertifikatsverwaltungsfunktionen finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.