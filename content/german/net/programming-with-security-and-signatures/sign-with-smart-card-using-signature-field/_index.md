---
title: Mit Smartcard unterschreiben und dabei das Signaturfeld verwenden
linktitle: Mit Smartcard unterschreiben und dabei das Signaturfeld verwenden
second_title: Aspose.PDF für .NET API-Referenz
description: Signieren Sie Ihre PDF-Dateien sicher mit einer Smartcard mit Aspose.PDF für .NET.
type: docs
weight: 120
url: /de/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Die digitale Signatur mit einer Smartcard ist eine sichere Methode zum Signieren von PDF-Dateien. Mit Aspose.PDF für .NET können Sie eine PDF-Datei ganz einfach mithilfe eines Signaturfelds und einer Smartcard signieren, indem Sie den folgenden Quellcode befolgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier sind die erforderlichen Importanweisungen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Schritt 2: Pfad zum Dokumentenordner festlegen

 In diesem Schritt müssen Sie den Pfad zum Ordner angeben, der die zu signierende PDF-Datei enthält. Ersetzen Sie`"YOUR DOCUMENTS DIRECTORY"` ersetzen Sie den folgenden Code durch den tatsächlichen Pfad zu Ihrem Dokumentordner:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 3: PDF-Dokument kopieren und öffnen

Nun kopieren und öffnen wir das zu signierende PDF-Dokument mit dem folgenden Code:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Erstellen eines Signaturfelds
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Wählen Sie das Zertifikat im Store aus
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Erstellen Sie eine externe Signatur mit den erforderlichen Informationen
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

 Abschließend überprüfen wir die Signatur der signierten PDF-Datei mit dem`PdfFileSignature` Klasse. Wir holen uns die Signaturnamen und prüfen sie einzeln. Wenn eine Signatur die Überprüfung nicht besteht, wird eine Exception ausgelöst. Hier ist der entsprechende Code:

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

### Beispielquellcode zum Unterschreiben mit Smartcard unter Verwendung des Signaturfelds unter Verwendung von Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Signieren mit Zertifikatauswahl im Windows-Zertifikatspeicher
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

Herzlichen Glückwunsch! Sie haben jetzt eine Schritt-für-Schritt-Anleitung zum Signieren einer PDF-Datei mit einer Smartcard unter Verwendung eines Signaturfelds mit Aspose.PDF für .NET. Mit diesem Code können Sie Ihren PDF-Dokumenten sichere digitale Signaturen hinzufügen.

Weitere Informationen zu erweiterten Funktionen für digitale Signaturen und Zertifikatsverwaltung finden Sie in der offiziellen Aspose.PDF-Dokumentation.

### Häufig gestellte Fragen

#### F: Welchen Vorteil bietet die Verwendung eines Signaturfelds zum digitalen Signieren mit einer Smartcard?

A: Durch die Verwendung eines Signaturfelds für die digitale Signatur mit einer Smartcard wird ein spezieller Bereich innerhalb der PDF-Datei bereitgestellt, in dem die Signatur angewendet wird. Dies verbessert die Dokumentübersichtlichkeit und stellt die Authentizität der Signatur sicher.

#### F: Wie erleichtert die Aspose.PDF-Bibliothek für .NET die digitale Signatur auf Smartcard-Basis mit einem Signaturfeld?

A: Aspose.PDF für .NET vereinfacht das Erstellen eines Signaturfelds, das Auswählen eines Smartcard-Zertifikats und das Anwenden einer digitalen Signatur auf einen bestimmten Bereich innerhalb des PDF-Dokuments.

#### F: Warum ist die Auswahl eines bestimmten Zertifikats für die Smartcard-basierte Signatur wichtig?

A: Durch die Auswahl eines bestimmten Zertifikats können Sie den Unterzeichner eindeutig identifizieren und die Integrität der Signatur sicherstellen. Dies trägt dazu bei, Vertrauen aufzubauen und die Einhaltung digitaler Signaturstandards zu gewährleisten.

#### F: Wie handhabt der bereitgestellte Quellcode den Smartcard-basierten Signaturprozess mit einem Signaturfeld?

A: Der Quellcode zeigt, wie man ein Signaturfeld erstellt, ein Smartcard-Zertifikat auswählt und eine digitale Signatur mit spezifischen Signaturinformationen anwendet. Außerdem wird gezeigt, wie die Gültigkeit der Signatur überprüft wird.

#### F: Kann ich das Erscheinungsbild des Signaturfelds anpassen?

A: Ja, Sie können das Erscheinungsbild des Signaturfelds, beispielsweise seine Größe, Position und visuelle Darstellung, anpassen, um es an das Layout Ihres Dokuments anzupassen.

#### F: Was passiert, wenn eine Signatur im Überprüfungsschritt nicht überprüft wird?

A: Wenn die Überprüfung einer Signatur fehlschlägt, wird eine Ausnahme ausgelöst, die angibt, dass die Signatur ungültig ist. Dadurch wird sichergestellt, dass nur gültige und vertrauenswürdige Signaturen akzeptiert werden.

#### F: Kann ich einem einzelnen PDF-Dokument mehrere Signaturfelder und Smartcard-basierte Signaturen hinzufügen?

A: Auf jeden Fall. Sie können mehrere Signaturfelder und Smartcard-basierte Signaturen auf verschiedene Bereiche desselben PDF-Dokuments anwenden und so mehrere Sicherheitsebenen bereitstellen.

#### F: Wie verbessert die Verwendung eines Signaturfelds den gesamten Dokumentsignaturprozess?

A: Die Verwendung eines Signaturfelds vereinfacht den Dokumentsignaturvorgang, da es den Unterzeichner anleitet, seine Unterschrift in einem dafür vorgesehenen Bereich zu platzieren. Dadurch wird der Signaturvorgang übersichtlicher und benutzerfreundlicher.

#### F: Gibt es Einschränkungen bei der Verwendung von Signaturfeldern bei der Smartcard-basierten Signatur?

A: Es gibt keine grundsätzlichen Einschränkungen bei der Verwendung von Signaturfeldern bei der Smartcard-basierten Signatur. Es ist jedoch wichtig sicherzustellen, dass die gewählte Position des Signaturfelds wichtige Dokumentinhalte nicht verdeckt.

#### F: Wo finde ich weitere Hilfe oder Unterstützung bei der Implementierung einer Smartcard-basierten Signatur mit einem Signaturfeld?

A: Weitere Anleitungen und Unterstützung erhalten Sie in der offiziellen Aspose.PDF-Dokumentation und in den Community-Foren, die wertvolle Einblicke und Lösungen zur Implementierung sicherer digitaler Signaturen bieten.