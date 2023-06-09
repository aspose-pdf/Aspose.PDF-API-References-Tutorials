---
title: Digital mit Zeitstempel signieren
linktitle: Digital mit Zeitstempel signieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine digitale Signatur mit Zeitstempel für eine PDF-Datei durchführen.
type: docs
weight: 50
url: /de/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---

In diesem Tutorial führen wir Sie durch den Prozess der digitalen Signatur einer PDF-Datei mit Zeitstempel mithilfe von Aspose.PDF für .NET. Die digitale Signatur mit Zeitstempel garantiert die Authentizität und Integrität des Dokuments, indem sie einen elektronischen Fingerabdruck mit Zeitstempel hinzufügt.

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
```

## Schritt 3: Digitale Signatur mit Zeitstempel

Der erste Schritt besteht darin, die digitale Signatur mit Zeitstempel auf der PDF-Datei durchzuführen. Der bereitgestellte Code zeigt, wie diese Signatur mit Aspose.PDF für .NET erreicht wird.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

Dieser Code lädt eine PDF-Datei und erstellt mithilfe einer PFX-Datei (privater Schlüssel) und den angegebenen Zeitstempelparametern eine digitale Signatur mit Zeitstempel. Die Signatur wird dann zur PDF-Datei hinzugefügt und mit dem Suffix „_aus".

### Beispielquellcode für die digitale Signatur mit Zeitstempel mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Benutzer/Passwort kann weggelassen werden
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		//Erstellen Sie einen der drei Signaturtypen
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Speichern Sie die ausgegebene PDF-Datei
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich eine digitale Signatur mit Zeitstempel für eine PDF-Datei durchgeführt. In diesem Tutorial wurde der Schritt-für-Schritt-Prozess vom Erstellen der Signatur bis zum Speichern der aktualisierten PDF-Datei behandelt. Mit dieser Funktion können Sie jetzt digitale Signaturen mit Zeitstempel zu Ihren PDF-Dateien hinzufügen.