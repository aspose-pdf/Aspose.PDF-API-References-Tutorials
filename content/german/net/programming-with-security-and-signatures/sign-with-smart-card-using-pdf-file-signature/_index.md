---
title: Unterschreiben Sie mit einer Smartcard und einer PDF-Dateisignatur
linktitle: Unterschreiben Sie mit einer Smartcard und einer PDF-Dateisignatur
second_title: Aspose.PDF für .NET API-Referenz
description: Signieren Sie Ihre PDF-Dateien sicher mit einer Smartcard mit Aspose.PDF für .NET.
type: docs
weight: 110
url: /de/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
Das digitale Signieren mit einer Smartcard ist eine sichere Möglichkeit, PDF-Dateien zu signieren. Mit Aspose.PDF für .NET können Sie eine PDF-Datei ganz einfach mit einer Smartcard signieren, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier sind die notwendigen Importanweisungen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, die Sie signieren möchten. Ersetzen`"YOUR DOCUMENTS DIRECTORY"`Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 3: Laden Sie das PDF-Dokument

Jetzt laden wir das zu signierende PDF-Dokument mit dem folgenden Code:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Schritt 4: Führen Sie die Signatur mit der Smartcard durch

 In diesem Schritt führen wir die Signatur mit der Smartcard durch`PdfFileSignature` Klasse aus der`Facades`Bibliothek. Wir wählen das Smartcard-Zertifikat aus dem Windows-Zertifikatspeicher aus und geben die erforderlichen Signaturinformationen an. Hier ist der entsprechende Code:

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

 Abschließend überprüfen wir die Signatur der signierten PDF-Datei mithilfe von`PdfFileSignature` Klasse. Wir erhalten die Signaturnamen und prüfen sie einzeln. Wenn die Überprüfung einer Signatur fehlschlägt, wird eine Ausnahme ausgelöst. Hier ist der entsprechende Code:

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

### Beispielquellcode für das Signieren mit einer Smartcard mithilfe einer PDF-Dateisignatur mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Signieren Sie mit der Zertifikatsauswahl im Windows-Zertifikatspeicher
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

Herzlichen Glückwunsch! Sie haben jetzt eine Schritt-für-Schritt-Anleitung zum Signieren einer PDF-Datei mit einer Smartcard mit Aspose.PDF für .NET. Mit diesem Code können Sie Ihren PDF-Dokumenten sichere digitale Signaturen hinzufügen.

Weitere Informationen zu erweiterten digitalen Signatur- und Zertifikatsverwaltungsfunktionen finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.

### FAQs

#### F: Warum sollte ich das Signieren von PDF-Dateien mit einer Smartcard in Betracht ziehen?

A: Das Signieren von PDF-Dateien mit einer Smartcard erhöht die Sicherheit, indem es die Authentizität und Integrität des Dokuments gewährleistet. Smartcard-basierte Signaturen sorgen für ein höheres Maß an Vertrauen und Compliance.

#### F: Wie funktioniert das digitale Signieren auf Smartcard-Basis?

A: Beim Smartcard-basierten digitalen Signieren wird ein auf einer Smartcard gespeicherter kryptografischer Schlüssel verwendet, um eine eindeutige digitale Signatur zu erstellen. Diese Signatur wird an die PDF-Datei angehängt und ermöglicht es den Empfängern, die Herkunft und Integrität des Dokuments zu überprüfen.

#### F: Welche Rolle spielt Aspose.PDF für .NET beim Smartcard-basierten Signieren?

A: Aspose.PDF für .NET bietet einen umfassenden Satz an Tools und Bibliotheken, um das digitale Signieren von PDF-Dateien auf Smartcard-Basis zu ermöglichen. Es vereinfacht den Prozess und sorgt für sicheres Signieren von Dokumenten.

#### F: Kann ich ein bestimmtes Smartcard-Zertifikat zum Signieren auswählen?

A: Ja, Sie können zum Signieren ein bestimmtes Smartcard-Zertifikat aus dem Windows-Zertifikatspeicher auswählen. Mit Aspose.PDF für .NET können Sie die Zertifikatsauswahl nahtlos in Ihre Anwendung integrieren.

#### F: Wie geht der bereitgestellte Quellcode mit der Smartcard-basierten Signatur um?

A: Der Quellcode zeigt, wie man ein PDF-Dokument bindet, ein Smartcard-Zertifikat auswählt, Signaturinformationen angibt und eine digitale Signatur erstellt. Außerdem wird gezeigt, wie die Gültigkeit der Signatur überprüft wird.

#### F: Kann ich mit Smartcards mehrere Signaturen in einer einzigen PDF-Datei anwenden?

A: Auf jeden Fall können Sie mehrere Smartcard-basierte Signaturen auf eine einzelne PDF-Datei anwenden. Jede Signatur ist einzigartig und trägt zur Gesamtsicherheit des Dokuments bei.

#### F: Was passiert, wenn die Überprüfung einer Signatur während des Überprüfungsschritts fehlschlägt?

A: Wenn die Überprüfung einer Signatur fehlschlägt, wird eine Ausnahme ausgelöst, die darauf hinweist, dass die Signatur ungültig ist. Dadurch wird sichergestellt, dass nur gültige und vertrauenswürdige Signaturen akzeptiert werden.

#### F: Ist das Smartcard-basierte Signieren mit allen Arten von PDF-Dokumenten kompatibel?

A: Ja, das Smartcard-basierte Signieren ist mit allen Arten von PDF-Dokumenten kompatibel. Sie können digitale Signaturen auf verschiedene Arten von PDF-Dateien anwenden, darunter Formulare, Berichte und mehr.

#### F: Wie kann ich mehr über die erweiterte Verwaltung digitaler Signaturen und Zertifikate erfahren?

A: Entdecken Sie die offizielle Aspose.PDF-Dokumentation, um detaillierte Einblicke in erweiterte Funktionen für digitale Signaturen, Zertifikatsverwaltung und Best Practices zur Gewährleistung der Dokumentensicherheit zu erhalten.

#### F: Wo finde ich weitere Hilfe oder Unterstützung für die Implementierung der Smartcard-basierten Signatur?

A: Für weitere Anleitung und Unterstützung wenden Sie sich an die Aspose.PDF-Community-Foren oder lesen Sie die Dokumentation für umfassende Informationen zum Smartcard-basierten Signieren.