---
title: PDF-Datei digital mit Zeitstempel signieren
linktitle: PDF-Datei digital mit Zeitstempel signieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine digitale Signatur mit Zeitstempel in einer PDF-Datei erstellen.
type: docs
weight: 50
url: /de/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
In diesem Tutorial führen wir Sie durch den Prozess der digitalen Signatur einer PDF-Datei mit Zeitstempel mithilfe von Aspose.PDF für .NET. Die digitale Signatur mit Zeitstempel garantiert die Authentizität und Integrität des Dokuments, indem ein elektronischer Fingerabdruck mit Zeitstempel hinzugefügt wird.

## Schritt 1: Voraussetzungen

Stellen Sie zunächst sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Grundkenntnisse der Programmiersprache C#
- Installieren von Visual Studio auf Ihrem Computer
- Aspose.PDF-Bibliothek für .NET installiert

## Schritt 2: Umgebung einrichten

Führen Sie zunächst die folgenden Schritte aus, um Ihre Entwicklungsumgebung einzurichten:

1. Öffnen Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Importieren Sie die erforderlichen Namespaces in Ihre Codedatei:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## Schritt 3: Digitale Signatur mit Zeitstempel

Der erste Schritt besteht darin, die PDF-Datei digital mit Zeitstempel zu signieren. Der bereitgestellte Code zeigt, wie diese Signatur mit Aspose.PDF für .NET erreicht wird.

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

Dieser Code lädt eine PDF-Datei, erstellt eine digitale Signatur mit Zeitstempel unter Verwendung einer PFX-Datei (privater Schlüssel) und den angegebenen Zeitstempelparametern. Die Signatur wird dann der PDF-Datei hinzugefügt und mit dem Suffix "_aus".

### Beispiel-Quellcode für „Digitales Signieren mit Zeitstempel“ unter Verwendung von Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Benutzer/Passwort können weggelassen werden
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// Erstellen Sie einen der drei Signaturtypen
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Ausgabe-PDF-Datei speichern
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich eine digitale Signatur mit Zeitstempel auf einer PDF-Datei erstellt. Dieses Tutorial behandelte den schrittweisen Prozess vom Erstellen der Signatur bis zum Speichern der aktualisierten PDF-Datei. Sie können diese Funktion jetzt verwenden, um Ihren PDF-Dateien digitale Signaturen mit Zeitstempel hinzuzufügen.

### FAQs zum digitalen Signieren mit Zeitstempel in PDF-Dateien

#### F: Was ist der Zweck der digitalen Signatur mit einem Zeitstempel?

A: Durch die digitale Signatur mit Zeitstempel wird einer PDF-Datei ein elektronischer Fingerabdruck mit Zeitstempel hinzugefügt, der die Authentizität und Integrität des Dokuments zu einem bestimmten Zeitpunkt sicherstellt.

#### F: Welche Voraussetzungen sind erforderlich, um dieses Tutorial starten zu können?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie über grundlegende Kenntnisse der Programmiersprache C# verfügen, Visual Studio installiert haben und die Aspose.PDF-Bibliothek für .NET installiert haben.

#### F: Wie kann ich meine Entwicklungsumgebung einrichten?

A: Befolgen Sie die angegebenen Schritte, um Ihre Entwicklungsumgebung einzurichten, einschließlich der Erstellung eines neuen C#-Projekts in Visual Studio und des Importierens der erforderlichen Namespaces.

#### F: Wie füge ich einer PDF eine digitale Signatur mit Zeitstempel hinzu?

A: Der bereitgestellte Beispielcode zeigt, wie Sie eine PDF-Datei laden, mithilfe einer PFX-Datei (privater Schlüssel) und angegebenen Zeitstempeleinstellungen eine digitale Signatur mit Zeitstempel erstellen, die Signatur zur PDF-Datei hinzufügen und die aktualisierte Datei speichern.

#### F: Was ist eine PFX-Datei und warum wird sie im Beispiel verwendet?

A: Eine PFX-Datei (Personal Exchange Format) enthält einen privaten Schlüssel und ein Zertifikat. Sie wird hier verwendet, um kryptografische Funktionen für digitale Signaturen bereitzustellen. Stellen Sie sicher, dass Sie den Platzhalter durch Ihre PFX-Datei und Ihr Kennwort ersetzen.

#### F: Was sind TimestampSettings?

A: TimestampSettings definiert die Einstellungen für den Zeitstempelserver, der zum Hinzufügen des elektronischen Zeitstempels zur Signatur verwendet wird. Dazu gehören die URL des Zeitstempelservers und optionale Benutzeranmeldeinformationen.

#### F: Kann ich einen anderen Zeitstempelserver als den im Beispiel verwenden?
 A: Ja, Sie können jeden kompatiblen Zeitstempelserver verwenden. Ersetzen Sie die URL und geben Sie bei Bedarf die entsprechenden Benutzeranmeldeinformationen im`TimestampSettings` Objekt.

#### F: Was ist der Zweck der Angabe des Signaturrechtecks?

A: Das Signaturrechteck definiert die Position und Abmessungen der digitalen Signatur auf der PDF-Seite. Passen Sie diese Werte an, um die Signatur wie gewünscht zu positionieren.

#### F: Was passiert, wenn der Zeitstempelserver während der Signierung nicht verfügbar ist?

A: Wenn der Zeitstempelserver während der Signierung nicht verfügbar ist, kann der Vorgang fehlschlagen oder länger dauern. Stellen Sie sicher, dass Ihr Zeitstempelserver zuverlässig und zugänglich ist.

#### F: Wie kann ich das Vorhandensein eines Zeitstempels im signierten PDF überprüfen?

 A: Sie können das signierte PDF anhand des bereitgestellten Beispielcodes prüfen.`TimestampSettings` Die von Ihnen beim Signieren verwendeten Zeichen sollten in den Signaturdetails verfügbar sein.

#### F: Sind digitale Signaturen mit Zeitstempeln rechtlich bindend?

A: Digitale Signaturen mit Zeitstempeln haben in vielen Rechtsgebieten Rechtskraft und werden oft als zuverlässiger angesehen als einfache digitale Signaturen. Konsultieren Sie Rechtsexperten in Ihrem Rechtsgebiet, um spezifische Bestimmungen zu erfahren.

#### F: Kann ich einer PDF mehrere digitale Signaturen mit Zeitstempeln hinzufügen?

A: Ja, Sie können einer PDF-Datei mehrere digitale Signaturen mit Zeitstempeln hinzufügen, indem Sie den Signaturerstellungsprozess mehrmals aufrufen. Jede Signatur hat einen eigenen Zeitstempel.