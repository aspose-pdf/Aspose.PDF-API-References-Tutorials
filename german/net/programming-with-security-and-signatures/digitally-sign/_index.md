---
title: Digital signieren
linktitle: Digital signieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie eine PDF-Datei mit Aspose.PDF für .NET digital signieren.
type: docs
weight: 40
url: /de/net/programming-with-security-and-signatures/digitally-sign/
---

In diesem Tutorial führen wir Sie durch den Prozess der digitalen Signatur einer PDF-Datei mit Aspose.PDF für .NET. Die digitale Signatur garantiert die Authentizität und Integrität des Dokuments, indem sie einen einzigartigen elektronischen Fingerabdruck hinzufügt.

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
			//Erstellen Sie einen der drei Signaturtypen
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