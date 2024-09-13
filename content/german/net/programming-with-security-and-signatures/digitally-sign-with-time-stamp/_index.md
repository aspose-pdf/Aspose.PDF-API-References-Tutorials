---
title: PDF-Datei digital mit Zeitstempel signieren
linktitle: PDF-Datei digital mit Zeitstempel signieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine PDF-Datei mit einem Zeitstempel digital signieren. Diese Schritt-für-Schritt-Anleitung behandelt Voraussetzungen, Zertifikatseinrichtung, Zeitstempel und mehr.
type: docs
weight: 50
url: /de/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
## Einführung

Mussten Sie schon einmal eine PDF-Datei digital signieren und einen Zeitstempel für zusätzliche Sicherheit hinzufügen? Egal, ob Sie an juristischen Dokumenten, Verträgen oder anderen Dokumenten arbeiten, die eine sichere Authentifizierung erfordern, eine digitale Signatur mit Zeitstempel verleiht zusätzliche Glaubwürdigkeit. In diesem Tutorial erklären wir Ihnen, wie Sie mit Aspose.PDF für .NET Ihren PDF-Dokumenten eine digitale Signatur zusammen mit einem Zeitstempel hinzufügen können. Keine Sorge, wir gehen Schritt für Schritt vor!

## Voraussetzungen

Bevor wir uns in den Code vertiefen, müssen Sie einige Dinge einrichten, um mitmachen zu können. Hier ist eine kurze Checkliste der Voraussetzungen, um Ihnen den Einstieg zu erleichtern:

-  Aspose.PDF für .NET-Bibliothek: Sie müssen die Aspose.PDF für .NET-Bibliothek in Ihrem Projekt installiert haben. Sie können[Laden Sie hier die neueste Version herunter](https://releases.aspose.com/pdf/net/) oder fügen Sie es über NuGet zu Ihrem Projekt hinzu.
- Ein PDF-Dokument: Sie benötigen eine Beispiel-PDF-Datei zum Arbeiten. Stellen Sie sicher, dass sich im Verzeichnis Ihres Projekts eine Datei befindet, die Sie signieren möchten.
-  Digitales Zertifikat (PFX-Datei): Stellen Sie sicher, dass Sie über ein digitales Zertifikat verfügen (eine`.pfx` Datei), um das Dokument digital zu signieren.
- Zeitstempel-URL: Dies ist ein Online-Zeitstempeldienst, der verwendet wird, um der digitalen Signatur einen Zeitstempel anzuhängen. 
- Grundlegende C#-Kenntnisse: Sie müssen kein Experte sein, aber Kenntnisse der C#-Grundlagen helfen Ihnen, den Code zu verstehen und anzupassen.

Wenn Sie alle diese Kästchen angekreuzt haben, können Sie mit dem Codieren beginnen!

## Pakete importieren

Um zu beginnen, müssen Sie die folgenden Namespaces in Ihr C#-Projekt importieren. Dadurch wird sichergestellt, dass Sie Zugriff auf die relevanten Aspose.PDF-Klassen und -Funktionen haben.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Collections;
```

## Schritt 1: Laden Sie das PDF-Dokument

Als Erstes müssen wir das PDF-Dokument laden, das wir unterzeichnen möchten. So geht's:

```csharp
// Definieren Sie den Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das PDF-Dokument
Document document = new Document(dataDir + @"DigitallySign.pdf");
```

 Dieser Schritt ist ziemlich unkompliziert. Wir definieren lediglich den Pfad zu dem Dokument, das wir signieren möchten.`Document` Die Klasse von Aspose.PDF übernimmt das Laden der Datei.

## Schritt 2: Einrichten der digitalen Signatur

Als nächstes erstellen wir die digitale Signatur mit der PKCS7-Klasse und laden die PFX-Datei. Diese PFX-Datei enthält Ihr Zertifikat und Ihren privaten Schlüssel, die zum Signieren des Dokuments erforderlich sind.

```csharp
// Pfad zu Ihrer PFX-Datei
string pfxFile = "YOUR DOCUMENTS DIRECTORY\\certificate.pfx";

// Initialisieren Sie das Signaturobjekt
PdfFileSignature signature = new PdfFileSignature(document);

// Laden Sie die PFX-Datei mit einem Passwort
PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
```

 An diesem Punkt weisen Sie Aspose an, Ihr digitales Zertifikat zum Signieren des Dokuments zu verwenden. Das`PKCS7`Das Objekt übernimmt die gesamte kryptografische Arbeit für Sie, sodass Sie sich nicht um die kleinsten Details kümmern müssen.

## Schritt 3: Fügen Sie die Zeitstempeleinstellungen hinzu

Eine der wichtigsten Komponenten einer robusten digitalen Signatur ist der Zeitstempel. Dieser stellt sicher, dass die Signatur des Dokuments auch nach Ablauf des Zertifikats überprüft werden kann. Lassen Sie uns den Zeitstempel mithilfe einer Online-Zeitstempelstelle einrichten.

```csharp
// Zeitstempeleinstellungen definieren
TimestampSettings timestampSettings = new TimestampSettings("https://Ihre_Zeitstempel-URL", "Benutzer:Passwort");

// Zeitstempeleinstellungen zum PKCS7-Objekt hinzufügen
pkcs.TimestampSettings = timestampSettings;
```

Hier geben Sie die URL für den Zeitstempeldienst an, der Ihre Signatur automatisch mit Uhrzeit und Datum versieht. Dies kann mit oder ohne Authentifizierung erfolgen.

## Schritt 4: Definieren Sie den Ort und das Aussehen der Signatur

Jetzt legen wir fest, wo die Signatur im PDF angezeigt wird und welche Abmessungen sie haben soll. Sie können die Position des Signaturfelds auf der Seite sowie die Größe anpassen.

```csharp
//Definieren Sie das Aussehen und die Position der Signatur (Seite 1, mit angegebenem Rechteck).
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
```

Hier definieren wir ein Rechteck, das die Signatur bei den Koordinaten (100, 100) auf der ersten Seite der PDF-Datei positioniert, mit einer Breite von 200 und einer Höhe von 100. Sie können diese Werte an Ihr Design anpassen.

## Schritt 5: Unterschreiben Sie das PDF-Dokument

Wenn alles eingerichtet ist, ist es an der Zeit, die digitale Signatur auf das PDF anzuwenden. Dieser Schritt kombiniert Zertifikat, Zeitstempel und Positionierung in einem einfachen Befehl.

```csharp
// Unterschreiben Sie das Dokument auf der ersten Seite
signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
```

Folgendes ist passiert:
- 1: Dies gibt an, dass die Signatur auf der ersten Seite angewendet werden soll.
- „Unterschriftsgrund“: Hier können Sie angeben, warum Sie das Dokument unterschreiben.
- „Kontakt“: Geben Sie die Kontaktinformationen des Unterzeichners ein.
- „Standort“: Geben Sie den Standort des Unterzeichners an.
- true: Dieser Boolesche Wert gibt an, ob die Signatur im Dokument sichtbar ist.
- Rechteck: Das zuvor definierte Rechteck gibt die Größe und Position der Signatur an.
- pkcs: Das PKCS7-Objekt enthält die Einstellungen für das digitale Zertifikat und den Zeitstempel.

## Schritt 6: Speichern Sie das signierte PDF

Sobald das Dokument unterzeichnet ist, muss es nur noch gespeichert werden. Sie können einen neuen Dateinamen wählen, um sowohl das Original als auch die unterzeichnete Version beizubehalten.

```csharp
// Speichern Sie das signierte PDF-Dokument
signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
```

Ihr neu signiertes und mit Zeitstempel versehenes PDF ist jetzt im angegebenen Verzeichnis gespeichert!

## Abschluss

Und da haben Sie es! Sie haben erfolgreich eine PDF-Datei mit einem Zeitstempel digital signiert, indem Sie Aspose.PDF für .NET verwenden. Dieser Vorgang stellt die Authentizität und Integrität Ihrer Dokumente sicher und gibt sowohl Ihnen als auch dem Empfänger Sicherheit. Digitale Signaturen werden in der heutigen digitalen Welt immer wichtiger, daher ist die Beherrschung dieses Vorgangs definitiv eine lohnende Fähigkeit.

## Häufig gestellte Fragen

### Kann ich für das Zertifikat ein anderes Dateiformat verwenden?  
Ja, aber das Tutorial konzentriert sich auf die Verwendung einer PFX-Datei, dem gängigsten Format für digitale Zertifikate.

### Benötige ich eine Internetverbindung, um den Zeitstempel anzuwenden?  
Ja, da der Zeitstempel von einer Online-Zeitstempelstelle abgerufen wird, benötigen Sie Internetzugang.

### Kann ich mehrere Seiten in einer PDF signieren?  
 Absolut! Sie können die`signature.Sign()` Methode, um mehrere Seiten anzusprechen oder alle Seiten zu durchlaufen.

### Was passiert, wenn das Kennwort der PFX-Datei falsch ist?  
Bei einem falschen Kennwort erhalten Sie eine Ausnahme. Stellen Sie daher sicher, dass Sie das Kennwort richtig eingegeben haben.

### Kann ich die Signatur unsichtbar machen?  
 Ja, du kannst vorbeikommen`false` zur`Sign` Verwenden Sie den Sichtbarkeitsparameter der Methode, um die Signatur unsichtbar zu machen.