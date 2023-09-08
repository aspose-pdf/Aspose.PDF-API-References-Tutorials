---
title: Digital mit Zeitstempel in einer PDF-Datei signieren
linktitle: Digital mit Zeitstempel in einer PDF-Datei signieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine digitale Signatur mit Zeitstempel in einer PDF-Datei durchführen.
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
		// Erstellen Sie einen der drei Signaturtypen
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Speichern Sie die ausgegebene PDF-Datei
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich eine digitale Signatur mit Zeitstempel für eine PDF-Datei durchgeführt. In diesem Tutorial wurde der Schritt-für-Schritt-Prozess vom Erstellen der Signatur bis zum Speichern der aktualisierten PDF-Datei behandelt. Mit dieser Funktion können Sie jetzt digitale Signaturen mit Zeitstempel zu Ihren PDF-Dateien hinzufügen.

### FAQs zum digitalen Signieren mit Zeitstempel in PDF-Dateien

#### F: Was ist der Zweck der digitalen Signatur mit Zeitstempel?

A: Beim digitalen Signieren mit Zeitstempel wird einer PDF-Datei ein elektronischer Fingerabdruck mit Zeitstempel hinzugefügt, wodurch die Authentizität und Integrität des Dokuments zu einem bestimmten Zeitpunkt sichergestellt wird.

#### F: Welche Voraussetzungen sind erforderlich, um mit diesem Tutorial zu beginnen?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie über grundlegende Kenntnisse der Programmiersprache C# verfügen, Visual Studio installiert haben und die Aspose.PDF-Bibliothek für .NET installiert ist.

#### F: Wie kann ich meine Entwicklungsumgebung einrichten?

A: Befolgen Sie die bereitgestellten Schritte, um Ihre Entwicklungsumgebung einzurichten, einschließlich der Erstellung eines neuen C#-Projekts in Visual Studio und des Imports der erforderlichen Namespaces.

#### F: Wie füge ich einer PDF-Datei eine digitale Signatur mit Zeitstempel hinzu?

A: Der bereitgestellte Beispielcode zeigt, wie Sie eine PDF-Datei laden, eine digitale Signatur mit einem Zeitstempel mithilfe einer PFX-Datei (privater Schlüssel) und angegebenen Zeitstempeleinstellungen erstellen, die Signatur zur PDF-Datei hinzufügen und die aktualisierte Datei speichern.

#### F: Was ist eine PFX-Datei und warum wird sie im Beispiel verwendet?

A: Eine PFX-Datei (Personal Exchange Format) enthält einen privaten Schlüssel und ein Zertifikat. Es wird hier verwendet, um kryptografische Funktionen für digitale Signaturen bereitzustellen. Stellen Sie sicher, dass Sie den Platzhalter durch Ihre PFX-Datei und Ihr Passwort ersetzen.

#### F: Was sind TimestampSettings?

A: TimestampSettings definiert die Einstellungen für den Zeitstempelserver, der zum Hinzufügen des elektronischen Zeitstempels zur Signatur verwendet wird. Es enthält die URL des Zeitstempelservers und optionale Benutzeranmeldeinformationen.

#### F: Kann ich einen anderen Zeitstempelserver als den im Beispiel verwenden?
 A: Ja, Sie können jeden kompatiblen Zeitstempelserver verwenden. Ersetzen Sie die URL und geben Sie bei Bedarf die entsprechenden Benutzeranmeldeinformationen ein`TimestampSettings` Objekt.

#### F: Was ist der Zweck der Angabe des Signaturrechtecks?

A: Das Signaturrechteck definiert die Position und Abmessungen des Erscheinungsbilds der digitalen Signatur auf der PDF-Seite. Passen Sie diese Werte an, um die Signatur wie gewünscht zu positionieren.

#### F: Was passiert, wenn der Zeitstempelserver während der Signierung nicht verfügbar ist?

A: Wenn der Zeitstempelserver während des Signierens nicht verfügbar ist, schlägt der Vorgang möglicherweise fehl oder dauert länger. Stellen Sie sicher, dass Ihr Zeitstempelserver zuverlässig und zugänglich ist.

#### F: Wie kann ich das Vorhandensein eines Zeitstempels im signierten PDF überprüfen?

 A: Sie können das signierte PDF mithilfe des bereitgestellten Beispielcodes untersuchen. Der`TimestampSettings` Die von Ihnen beim Signieren verwendete Datei sollte in den Signaturdetails verfügbar sein.

#### F: Sind digitale Signaturen mit Zeitstempel rechtsverbindlich?

A: Digitale Signaturen mit Zeitstempel haben in vielen Rechtsordnungen rechtlichen Wert und gelten oft als zuverlässiger als einfache digitale Signaturen. Für spezifische Vorschriften wenden Sie sich an Rechtsexperten in Ihrer Gerichtsbarkeit.

#### F: Kann ich einer PDF-Datei mehrere digitale Signaturen mit Zeitstempeln hinzufügen?

A: Ja, Sie können einer PDF-Datei mehrere digitale Signaturen mit Zeitstempel hinzufügen, indem Sie den Signaturerstellungsprozess mehrmals aufrufen. Jede Signatur verfügt über einen eigenen Zeitstempel.