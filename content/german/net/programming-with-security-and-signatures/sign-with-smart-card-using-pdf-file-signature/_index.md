---
title: Mit Smartcard unter Verwendung der PDF-Dateisignatur signieren
linktitle: Mit Smartcard unter Verwendung der PDF-Dateisignatur signieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie PDF-Dateien mit einer Smartcard mit Aspose.PDF für .NET signieren. Folgen Sie dieser Schritt-für-Schritt-Anleitung für sichere digitale Signaturen.
type: docs
weight: 110
url: /de/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
## Einführung

Im digitalen Zeitalter ist die Sicherung von Dokumenten wichtiger denn je. Ob es sich um einen Vertrag, eine Vereinbarung oder vertrauliche Informationen handelt, es ist von größter Bedeutung, sicherzustellen, dass das Dokument authentisch ist und nicht manipuliert wurde. Hier kommen digitale Signaturen ins Spiel! Heute werden wir uns damit befassen, wie man eine PDF-Datei mit einer Smartcard mit Aspose.PDF für .NET signiert. Mit dieser leistungsstarken Bibliothek können Entwickler PDF-Dokumente effizient bearbeiten und erstellen, einschließlich des Hinzufügens sicherer digitaler Signaturen. Also, schnappen Sie sich Ihre Smartcard und legen Sie los!

## Voraussetzungen

Bevor wir uns mit den Einzelheiten des Signierens einer PDF-Datei befassen, stellen wir sicher, dass Sie alles haben, was Sie brauchen. Hier ist eine Checkliste, die Ihnen bei der Vorbereitung hilft:

1.  Aspose.PDF für .NET: Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert haben. Sie können sie von der[Website](https://releases.aspose.com/pdf/net/).
2. Visual Studio: Eine Entwicklungsumgebung, in der Sie Ihren .NET-Code schreiben und ausführen können.
3. Smartcard: Sie benötigen eine Smartcard mit einem gültigen digitalen Zertifikat.
4. Grundlegende Kenntnisse in C#: Kenntnisse in der C#-Programmierung sind von Vorteil, da wir Codeausschnitte in dieser Sprache schreiben werden.
5. PDF-Dokument: Eine Beispiel-PDF-Datei (wie`blank.pdf`), um unseren Signaturprozess zu testen.

Wenn diese Voraussetzungen erfüllt sind, können Sie mit dem Code loslegen!

## Pakete importieren

Als Erstes importieren wir die erforderlichen Pakete. Sie müssen in Ihrem Projekt Verweise auf die Aspose.PDF-Bibliothek hinzufügen. So können Sie das tun:

1. Öffnen Sie Visual Studio.
2. Erstellen Sie ein neues Projekt oder öffnen Sie ein vorhandenes.
3.  Klicken Sie mit der rechten Maustaste auf Ihr Projekt im Solution Explorer und wählen Sie`Manage NuGet Packages`.
4.  Suchen nach`Aspose.PDF` und installieren Sie die neueste Version.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nachdem wir nun die erforderlichen Pakete importiert haben, wollen wir den Code Schritt für Schritt aufschlüsseln.

## Schritt 1: Richten Sie Ihr Dokument ein

Der erste Schritt in unserem Prozess besteht darin, das PDF-Dokument einzurichten, das wir unterzeichnen möchten. So können Sie das tun:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
```
 In diesem Snippet definieren wir den Pfad zu unserem Dokumentenverzeichnis und erstellen eine Instanz des`Document` Klasse mit einer Beispiel-PDF-Datei namens`blank.pdf` . Achten Sie darauf, zu ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad, in dem sich Ihr PDF befindet.

## Schritt 2: PdfFileSignature initialisieren

 Als nächstes initialisieren wir die`PdfFileSignature` Klasse, die für die Abwicklung des Signaturvorgangs zuständig ist.

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
    pdfSign.BindPdf(doc);
```
Hier erstellen wir eine Instanz von`PdfFileSignature`und binden Sie es an unser PDF-Dokument. Dadurch wird das Dokument für die Unterzeichnung vorbereitet.

## Schritt 3: Zugriff auf das Smartcard-Zertifikat

Jetzt kommt der entscheidende Teil – der Zugriff auf das digitale Zertifikat, das auf Ihrer Chipkarte gespeichert ist. So können wir es machen:

### Öffnen Sie den Zertifikatspeicher

```csharp
System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
```
Wir öffnen den Zertifikatsspeicher im Profil des aktuellen Benutzers. Dadurch können wir auf die auf Ihrem Computer installierten Zertifikate zugreifen, einschließlich der Zertifikate auf Ihrer Smartcard.

### Wählen Sie das Zertifikat

```csharp
System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel =
    System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(
        store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
```
Dieser Code fordert den Benutzer auf, ein Zertifikat aus der Sammlung auszuwählen. Die Benutzeroberfläche zeigt alle verfügbaren Zertifikate an, sodass Sie das Zertifikat auswählen können, das Ihrer Smartcard zugeordnet ist.

## Schritt 4: Erstellen der externen Signatur

Nachdem Sie Ihr Zertifikat ausgewählt haben, besteht der nächste Schritt darin, eine externe Signatur mit dem ausgewählten Zertifikat zu erstellen.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
```
Hier erstellen wir eine Instanz von`ExternalSignature` mit dem ausgewählten Zertifikat. Dieses Objekt wird zum Signieren des PDF-Dokuments verwendet.

## Schritt 5: Festlegen des Signatur-Erscheinungsbilds

Legen wir nun das Erscheinungsbild unserer Signatur fest. Hier können Sie anpassen, wie Ihre Signatur im Dokument aussieht.

```csharp
pdfSign.SignatureAppearance = dataDir + "demo.png";
```
 In diesem Snippet geben wir das Erscheinungsbild der Signatur an, indem wir den Pfad zu einer Bilddatei (z. B. einem Logo oder einer Signaturgrafik) angeben. Achten Sie darauf, Folgendes zu ersetzen:`"demo.png"` mit dem tatsächlichen Bild, das Sie verwenden möchten.

## Schritt 6: Unterschreiben Sie das PDF

Nachdem alles eingerichtet ist, ist es Zeit, das PDF-Dokument zu unterzeichnen!

```csharp
pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
pdfSign.Save(dataDir + "externalSignature2.pdf");
```
In diesem Schritt rufen wir die`Sign` Methode auf unserer`pdfSign` Objekt. Die Bedeutung der einzelnen Parameter lautet:
- `1`: Die Seitenzahl, auf der die Signatur erscheint.
- `"Reason"`: Der Grund für die Unterzeichnung des Dokuments.
- `"Contact"`: Kontaktinformationen für den Unterzeichner.
- `"Location"`: Der Standort des Unterzeichners.
- `true`: Gibt an, ob eine sichtbare Signatur erstellt werden soll.
- `new System.Drawing.Rectangle(100, 100, 200, 200)`: Die Position und Größe der Signatur im PDF.
- `externalSignature`: Das Signaturobjekt, das wir zuvor erstellt haben.

 Abschließend speichern wir das unterschriebene Dokument als`externalSignature2.pdf`.

## Schritt 7: Überprüfen der Signatur

Nach der Unterzeichnung des Dokuments muss unbedingt überprüft werden, ob die Unterschrift gültig ist. So geht's:

### Verifizierungsprozess initialisieren

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
```
 Wir erstellen eine neue Instanz von`PdfFileSignature` für das signierte Dokument. Anschließend rufen wir die Namen aller im Dokument vorhandenen Signaturen ab.

### Gültigkeit der Signatur prüfen

```csharp
for (int index = 0; index <= sigNames.Count - 1; index++)
{
    if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
    {
        throw new ApplicationException("Not verified");
    }
}
```
Wir durchlaufen jeden Signaturnamen und überprüfen seine Gültigkeit. Wenn die Überprüfung einer Signatur fehlschlägt, wird eine Ausnahme ausgelöst, die angibt, dass die Signatur nicht gültig ist.

## Abschluss

Und da haben Sie es! Sie haben erfolgreich ein PDF-Dokument mit einer Smartcard mit Aspose.PDF für .NET signiert. Dieser Vorgang sichert nicht nur Ihr Dokument, sondern fügt auch eine Authentizitätsebene hinzu, die in der heutigen digitalen Welt von entscheidender Bedeutung ist. Egal, ob Sie mit Verträgen, Rechtsdokumenten oder vertraulichen Informationen arbeiten, das Wissen, wie man digitale Signaturen implementiert, ist eine wertvolle Fähigkeit. 

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente innerhalb von .NET-Anwendungen zu erstellen, zu bearbeiten und zu konvertieren.

### Benötige ich zum Signieren von PDFs eine Smartcard?
Obwohl eine Smartcard nicht zwingend erforderlich ist, wird sie für sichere digitale Signaturen dringend empfohlen, da sie eine zusätzliche Sicherheitsebene bietet.

### Kann ich zum Unterschreiben eine beliebige PDF-Datei verwenden?
Ja, Sie können jede beliebige PDF-Datei verwenden. Stellen Sie jedoch sicher, dass sie nicht kennwortgeschützt ist. Wenn dies der Fall ist, müssen Sie die Datei zuerst entsperren.

### Was ist, wenn ich kein digitales Zertifikat habe?
Sie können ein digitales Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle (CA) erhalten oder zu Testzwecken ein selbstsigniertes Zertifikat verwenden.

### Gibt es eine Testversion von Aspose.PDF?
 Ja, Sie können eine kostenlose Testversion herunterladen von der[Aspose-Website](https://releases.aspose.com/).