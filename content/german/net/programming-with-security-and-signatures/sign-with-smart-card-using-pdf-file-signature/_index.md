---
title: Mit Smartcard unter Verwendung der PDF-Dateisignatur signieren
linktitle: Mit Smartcard unter Verwendung der PDF-Dateisignatur signieren
second_title: Aspose.PDF für .NET API-Referenz
description: Signieren Sie Ihre PDF-Dateien sicher mit einer Smartcard mit Aspose.PDF für .NET.
type: docs
weight: 110
url: /de/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
Die digitale Signatur mit einer Smartcard ist eine sichere Methode zum Signieren von PDF-Dateien. Mit Aspose.PDF für .NET können Sie eine PDF-Datei ganz einfach mit einer Smartcard signieren, indem Sie den folgenden Quellcode befolgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier sind die erforderlichen Importanweisungen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Schritt 2: Pfad zum Dokumentenordner festlegen

 In diesem Schritt müssen Sie den Pfad zum Ordner angeben, der die zu signierende PDF-Datei enthält. Ersetzen Sie`"YOUR DOCUMENTS DIRECTORY"` ersetzen Sie den folgenden Code durch den tatsächlichen Pfad zu Ihrem Dokumentordner:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 3: Laden Sie das PDF-Dokument

Nun laden wir das zu signierende PDF-Dokument mit folgendem Code:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Schritt 4: Mit der Chipkarte signieren

 In diesem Schritt führen wir die Signatur mit der Chipkarte durch. Dabei wird`PdfFileSignature` Klasse aus dem`Facades`Bibliothek. Wir wählen das Smartcard-Zertifikat aus dem Windows-Zertifikatspeicher aus und geben die erforderlichen Signaturinformationen an. Hier ist der entsprechende Code:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Wählen Sie das Zertifikat im Store aus
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## Schritt 5: Signatur überprüfen

 Abschließend überprüfen wir die Signatur der signierten PDF-Datei mit dem`PdfFileSignature` Klasse. Wir holen uns die Signaturnamen und prüfen sie einzeln. Wenn eine Signatur die Überprüfung nicht besteht, wird eine Exception ausgelöst. Hier ist der entsprechende Code:

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

### Beispiel-Quellcode zum Signieren mit Smartcard unter Verwendung der PDF-Dateisignatur unter Verwendung von Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Signieren mit Zertifikatauswahl im Windows-Zertifikatspeicher
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Wählen Sie das Zertifikat manuell im Store aus
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

## Abschluss

Herzlichen Glückwunsch! Sie verfügen nun über eine Schritt-für-Schritt-Anleitung zum Signieren einer PDF-Datei mit einer Smartcard unter Verwendung von Aspose.PDF für .NET. Mit diesem Code können Sie Ihren PDF-Dokumenten sichere digitale Signaturen hinzufügen.

Weitere Informationen zu erweiterten Funktionen für digitale Signaturen und Zertifikatsverwaltung finden Sie in der offiziellen Aspose.PDF-Dokumentation.

### Häufig gestellte Fragen

#### F: Warum sollte ich PDF-Dateien mit einer Smartcard signieren?

A: Das Signieren von PDF-Dateien mit einer Smartcard erhöht die Sicherheit, indem die Authentizität und Integrität des Dokuments sichergestellt wird. Smartcardbasierte Signaturen bieten ein höheres Maß an Vertrauen und Compliance.

#### F: Wie funktioniert die digitale Signatur auf Smartcard-Basis?

A: Bei der Smartcard-basierten digitalen Signatur wird ein auf einer Smartcard gespeicherter kryptografischer Schlüssel verwendet, um eine eindeutige digitale Signatur zu erstellen. Diese Signatur wird an die PDF-Datei angehängt, sodass die Empfänger die Herkunft und Integrität des Dokuments überprüfen können.

#### F: Welche Rolle spielt Aspose.PDF für .NET bei der Smartcard-basierten Signierung?

A: Aspose.PDF für .NET bietet einen umfassenden Satz an Tools und Bibliotheken, um die Smartcard-basierte digitale Signatur von PDF-Dateien zu erleichtern. Es vereinfacht den Prozess und gewährleistet eine sichere Signatur von Dokumenten.

#### F: Kann ich zum Signieren ein bestimmtes Smartcard-Zertifikat auswählen?

A: Ja, Sie können ein bestimmtes Smartcard-Zertifikat aus dem Windows-Zertifikatspeicher zum Signieren auswählen. Aspose.PDF für .NET ermöglicht Ihnen die nahtlose Integration der Zertifikatsauswahl in Ihre Anwendung.

#### F: Wie handhabt der bereitgestellte Quellcode die Smartcard-basierte Signatur?

A: Der Quellcode zeigt, wie man ein PDF-Dokument bindet, ein Smartcard-Zertifikat auswählt, Signaturinformationen angibt und eine digitale Signatur erstellt. Außerdem wird gezeigt, wie man die Gültigkeit der Signatur überprüft.

#### F: Kann ich mithilfe von Smartcards mehrere Signaturen in einer einzigen PDF-Datei anbringen?

A: Auf jeden Fall. Sie können einer einzelnen PDF-Datei mehrere Smartcard-basierte Signaturen hinzufügen. Jede Signatur ist einzigartig und trägt zur Gesamtsicherheit des Dokuments bei.

#### F: Was passiert, wenn eine Signatur während des Überprüfungsschritts die Überprüfung fehlschlägt?

A: Wenn die Überprüfung einer Signatur fehlschlägt, wird eine Ausnahme ausgelöst, die angibt, dass die Signatur ungültig ist. Dadurch wird sichergestellt, dass nur gültige und vertrauenswürdige Signaturen akzeptiert werden.

#### F: Ist die Smartcard-basierte Signatur mit allen Arten von PDF-Dokumenten kompatibel?

A: Ja, die Smartcard-basierte Signatur ist mit allen Arten von PDF-Dokumenten kompatibel. Sie können digitale Signaturen auf verschiedene Arten von PDF-Dateien anwenden, darunter Formulare, Berichte und mehr.

#### F: Wie kann ich mehr über erweiterte digitale Signaturen und Zertifikatsverwaltung erfahren?

A: Sehen Sie sich die offizielle Aspose.PDF-Dokumentation an, um detaillierte Einblicke in erweiterte Funktionen für digitale Signaturen, Zertifikatsverwaltung und Best Practices zur Gewährleistung der Dokumentensicherheit zu erhalten.

#### F: Wo finde ich weitere Hilfe oder Unterstützung bei der Implementierung einer Smartcard-basierten Signatur?

A: Weitere Anleitungen und Unterstützung erhalten Sie in den Aspose.PDF-Community-Foren oder in der Dokumentation mit umfassenden Informationen zum Signieren mit Smartcards.