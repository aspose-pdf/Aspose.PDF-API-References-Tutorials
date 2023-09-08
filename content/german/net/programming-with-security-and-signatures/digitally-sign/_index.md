---
title: PDF-Datei digital anmelden
linktitle: PDF-Datei digital anmelden
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie eine PDF-Datei mit Aspose.PDF für .NET digital signieren.
type: docs
weight: 40
url: /de/net/programming-with-security-and-signatures/digitally-sign/
---
In diesem Tutorial führen wir Sie durch den Prozess der digitalen Signatur in PDF-Dateien mit Aspose.PDF für .NET. Die digitale Signatur garantiert die Authentizität und Integrität des Dokuments, indem sie einen einzigartigen elektronischen Fingerabdruck hinzufügt.

## Schritt 1: Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#
- Installieren von Visual Studio auf Ihrem Computer
- Aspose.PDF-Bibliothek für .NET installiert

## Schritt 2: Umgebungseinrichtung

Führen Sie zunächst die folgenden Schritte aus, um Ihre Entwicklungsumgebung einzurichten:

1. Öffnen Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Importieren Sie die erforderlichen Namespaces in Ihre Codedatei:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## Schritt 3: Digitale Signatur

Der erste Schritt besteht darin, die PDF-Datei digital zu signieren. Der bereitgestellte Code zeigt, wie Sie mit Aspose.PDF für .NET eine digitale Signatur erstellen.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

Dieser Code lädt eine PDF-Datei, erstellt eine digitale Signatur mit einem bestimmten Erscheinungsbild und speichert dann die PDF-Datei mit der hinzugefügten Signatur.

## Schritt 4: Signaturüberprüfung

Nach dem Hinzufügen der digitalen Signatur können Sie prüfen, ob die PDF-Datei eine gültige Signatur enthält.

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // Etwas tun
                     }
                 }
             }
         }
     }
}
```

Dieser Code überprüft die erste Signatur der PDF-Datei und führt zusätzliche Aktionen aus, wenn die Signatur zertifiziert ist und über bestimmte Berechtigungen verfügt.

### Beispielquellcode für Digital Sign mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Verwenden Sie PKCS7/PKCS7Detached-Objekte
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Legen Sie das Erscheinungsbild der Signatur fest
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Erstellen Sie einen der drei Signaturtypen
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Speichern Sie die ausgegebene PDF-Datei
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // Irgendwelche Unterschriften?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // Zuerst überprüfen
				{
					if (signature.IsCertified) // Zertifiziert?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Holen Sie sich eine Zugangsberechtigung
						{
							// Etwas tun
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich eine digitale Signatur für eine PDF-Datei durchgeführt. Dieses Tutorial behandelt den schrittweisen Prozess vom Hinzufügen der digitalen Signatur bis zur Überprüfung ihrer Gültigkeit. Sie können diese Funktion jetzt nutzen, um Ihre PDF-Dateien mit digitalen Signaturen zu sichern.

### FAQs

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial führt Sie durch den Prozess der digitalen Signatur einer PDF-Datei mit Aspose.PDF für .NET. Digitale Signaturen fügen einen elektronischen Fingerabdruck hinzu, um die Authentizität und Integrität des Dokuments sicherzustellen.

#### F: Welche Voraussetzungen sind vor dem Start erforderlich?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie über grundlegende Kenntnisse der Programmiersprache C# verfügen, Visual Studio installiert haben und die Aspose.PDF-Bibliothek für .NET installiert ist.

#### F: Wie richte ich die Entwicklungsumgebung ein?

A: Befolgen Sie die bereitgestellten Schritte zum Einrichten Ihrer Entwicklungsumgebung, einschließlich der Erstellung eines neuen C#-Projekts in Visual Studio und des Imports der erforderlichen Namespaces.

#### F: Wie füge ich einer PDF-Datei eine digitale Signatur hinzu?

 A: Der bereitgestellte Beispielcode zeigt, wie Sie eine PDF-Datei laden, eine digitale Signatur erstellen, das Erscheinungsbild festlegen und die signierte PDF-Datei speichern. Die digitale Signatur wird mit hinzugefügt`Certify` Methode der`PdfFileSignature` Objekt.

#### F: Wie überprüfe ich die Gültigkeit einer digitalen Signatur?

A: Nachdem Sie die digitale Signatur hinzugefügt haben, können Sie den Beispielcode verwenden, um die Gültigkeit der Signatur zu überprüfen. Es prüft, ob die Signatur zertifiziert ist und über bestimmte Zugriffsberechtigungen verfügt.

####  F: Was bedeutet das`PKCS7` object represent?

 A: Die`PKCS7` Das Objekt wird verwendet, um die kryptografische Funktionalität für digitale Signaturen bereitzustellen. Es wird verwendet, um die digitale Signatur im bereitgestellten Beispielcode zu erstellen.

#### F: Kann ich das Erscheinungsbild der digitalen Signatur anpassen?

 A: Ja, Sie können das Erscheinungsbild der digitalen Signatur anpassen, indem Sie den Pfad zu einem Bild im angeben`SignatureAppearance` Eigentum der`PdfFileSignature` Objekt.

#### F: Was passiert, wenn die Signatur ungültig ist?

A: Wenn die Signatur ungültig ist, schlägt der Verifizierungsprozess fehl und die entsprechenden Aktionen innerhalb des Verifizierungscodeblocks werden nicht ausgeführt.

#### F: Wie kann ich die Sicherheit meiner digitalen Signaturen gewährleisten?

A: Digitale Signaturen sind von Natur aus sicher und nutzen kryptografische Techniken, um Authentizität und Integrität sicherzustellen. Stellen Sie sicher, dass Sie Ihren privaten Schlüssel sicher aufbewahren und befolgen Sie die Best Practices für den Umgang mit digitalen Signaturen.

#### F: Kann ich einer PDF-Datei mehrere digitale Signaturen hinzufügen?

 A: Ja, Sie können einer PDF-Datei mehrere digitale Signaturen hinzufügen`PdfFileSignature` Objekt`Sign` oder`Certify` Methoden. Jede Signatur hat ihr eigenes Aussehen und ihre eigene Konfiguration.