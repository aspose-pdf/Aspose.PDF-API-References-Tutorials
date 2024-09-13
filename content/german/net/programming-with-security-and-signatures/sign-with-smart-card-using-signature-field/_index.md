---
title: Mit Smartcard unterschreiben und dabei das Signaturfeld verwenden
linktitle: Mit Smartcard unterschreiben und dabei das Signaturfeld verwenden
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET PDFs mithilfe einer Smartcard sicher signieren. Folgen Sie unserer Schritt-für-Schritt-Anleitung für eine einfache Implementierung.
type: docs
weight: 120
url: /de/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
## Einführung

In der heutigen digitalen Welt ist die Sicherung von Dokumenten wichtiger denn je. Egal, ob Sie Entwickler, Geschäftsinhaber oder einfach jemand sind, der mit vertraulichen Informationen umgeht: Wenn Sie wissen, wie Sie PDFs elektronisch signieren, können Sie Zeit sparen und sicherstellen, dass Ihre Dokumente authentifiziert sind. In dieser Anleitung führen wir Sie durch den Prozess der Signierung einer PDF-Datei mithilfe einer Smartcard und eines Signaturfelds mit Aspose.PDF für .NET. 

## Voraussetzungen

Bevor wir uns in die Einzelheiten des Signiervorgangs stürzen, stellen wir sicher, dass Sie alles haben, was Sie für den Start benötigen. Hier ist eine Checkliste der Voraussetzungen:

1. Aspose.PDF für .NET: Stellen Sie sicher, dass die Aspose.PDF-Bibliothek in Ihrer .NET-Umgebung installiert ist. Sie können sie von der[Website](https://releases.aspose.com/pdf/net/).

2. Visual Studio: Sie benötigen eine IDE, um Ihren .NET-Code zu schreiben und auszuführen. Visual Studio Community Edition ist eine großartige kostenlose Option.

3. Eine Smartcard: Diese ist zum Signieren Ihrer PDF-Datei unbedingt erforderlich. Stellen Sie sicher, dass auf Ihrem Computer ein Smartcard-Lesegerät und die erforderlichen Zertifikate installiert sind.

4. Grundlegende C#-Kenntnisse: Wenn Sie mit der C#-Programmierung vertraut sind, können Sie die von uns verwendeten Codeausschnitte besser verstehen.

5. Beispiel-PDF-Dokument: Halten Sie ein Beispiel-PDF-Dokument zum Testen bereit. Sie können ein leeres PDF erstellen oder ein vorhandenes verwenden.

## Pakete importieren

Bevor wir mit dem Programmieren beginnen, importieren wir die erforderlichen Pakete. Sie müssen die folgenden Namespaces in Ihre C#-Datei aufnehmen:

```csharp
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Über diese Namespaces erhalten Sie Zugriff auf die Klassen und Methoden, die für die Arbeit mit PDFs und die Handhabung digitaler Signaturen erforderlich sind.

## Schritt-für-Schritt-Anleitung zum Signieren einer PDF-Datei mit einer Smartcard

Nachdem wir nun unsere Voraussetzungen geklärt haben, unterteilen wir den Signiervorgang in überschaubare Schritte. Wir gehen jeden Schritt im Detail durch, um sicherzustellen, dass Sie verstehen, was im Hintergrund passiert.

### Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein

Vorgehensweise: Definieren Sie den Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Erklärung: Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad, in dem sich Ihre PDF-Dateien befinden. Hier lesen wir das leere PDF und speichern das signierte Dokument.

### Schritt 2: Kopieren Sie das leere PDF

Was zu tun ist: Erstellen Sie eine Kopie Ihrer leeren PDF-Datei zum Arbeiten.

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
```

 Erklärung: Diese Zeile kopiert die`blank.pdf`Datei in eine neue Datei mit dem Namen`externalSignature1.pdf` . Der`true` Der Parameter ermöglicht das Überschreiben, wenn die Datei bereits vorhanden ist.

### Schritt 3: Öffnen Sie das PDF-Dokument

Vorgehensweise: Öffnen Sie die kopierte PDF-Datei zum Lesen und Schreiben.

```csharp
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
    using (Document doc = new Document(fs))
    {
        // Weitere Schritte folgen hier
    }
}
```

 Erklärung: Wir verwenden eine`FileStream` um unsere PDF-Datei zu öffnen.`Document` Klasse von Aspose.PDF ermöglicht uns, den PDF-Inhalt zu bearbeiten.

### Schritt 4: Erstellen Sie ein Signaturfeld

Vorgehensweise: Definieren Sie im PDF ein Signaturfeld, in dem die Signatur platziert wird.

```csharp
SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
```

 Erklärung: Hier erstellen wir eine`SignatureField` auf der zweiten Seite (Seitenindex beginnt bei 1) des PDFs. Die`Rectangle` definiert die Position und Größe des Signaturfeldes.

### Schritt 5: Zugriff auf den Smartcard-Zertifikatspeicher

Vorgehensweise: Öffnen Sie den Zertifikatspeicher, um Ihr Smartcard-Zertifikat auszuwählen.

```csharp
X509Store store = new X509Store(StoreLocation.CurrentUser);
store.Open(OpenFlags.ReadOnly);
```

Erklärung: Wir greifen auf den Zertifikatsspeicher des aktuellen Benutzers zu. Hier sind Ihre Smartcard-Zertifikate gespeichert.

### Schritt 6: Wählen Sie das Zertifikat aus

Vorgehensweise: Fordern Sie den Benutzer auf, ein Zertifikat aus dem Speicher auszuwählen.

```csharp
X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
```

Erklärung: Diese Zeile öffnet einen Dialog zur Auswahl eines Zertifikats. Sie können das Zertifikat auswählen, das Ihrer Smartcard zugeordnet ist.

### Schritt 7: Erstellen einer externen Signatur

 Vorgehensweise: Erstellen Sie eine Instanz von`ExternalSignature` unter Verwendung des ausgewählten Zertifikats.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
{
    Authority = "Me",
    Reason = "Reason",
    ContactInfo = "Contact"
};
```

 Erklärung: Wir initialisieren die`ExternalSignature` mit dem ausgewählten Zertifikat. Sie können auch die Autorität, den Grund für die Signatur und die Kontaktinformationen festlegen.

### Schritt 8: Signaturfeld zum Dokument hinzufügen

Vorgehensweise: Fügen Sie dem Dokument das Signaturfeld hinzu.

```csharp
field1.PartialName = "sig1";
doc.Form.Add(field1, 1);
```

Erklärung: Wir geben dem Signaturfeld einen Namen und fügen es auf der ersten Seite des Dokuments ein. Damit bereiten wir das PDF für die Unterschrift vor.

### Schritt 9: Unterschreiben Sie das Dokument

Vorgehensweise: Verwenden Sie die externe Signatur, um das PDF zu signieren.

```csharp
field1.Sign(externalSignature);
doc.Save();
```

Erklärung: Diese Zeile unterschreibt das Dokument mit der externen Signatur und speichert die Änderungen im PDF. Ihr Dokument ist nun unterschrieben!

### Schritt 10: Überprüfen der Signatur

Vorgehensweise: Überprüfen Sie, ob die Signatur gültig ist.

```csharp
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

Erklärung: Wir erstellen eine Instanz von`PdfFileSignature` um die Signaturen im Dokument zu überprüfen. Wenn die Signatur ungültig ist, wird eine Ausnahme ausgelöst.

## Abschluss

Herzlichen Glückwunsch! Sie haben gerade gelernt, wie Sie mit Aspose.PDF für .NET ein PDF-Dokument mithilfe einer Smartcard und eines Signaturfelds signieren. Dieser Vorgang sichert nicht nur Ihre Dokumente, sondern gewährleistet auch deren Authentizität und ist damit eine unverzichtbare Fähigkeit in der heutigen digitalen Landschaft. Egal, ob Sie Verträge, Rechnungen oder andere wichtige Dokumente unterzeichnen, das Wissen, wie Sie digitale Signaturen implementieren, kann Ihnen Zeit sparen und Ihnen ein beruhigendes Gefühl geben.

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler PDF-Dokumente in .NET-Anwendungen erstellen, bearbeiten und konvertieren können.

### Benötige ich zum Signieren von PDFs eine Smartcard?
Ja, zum sicheren Signieren von PDFs mit einem digitalen Zertifikat ist eine Smartcard erforderlich.

### Kann ich Aspose.PDF kostenlos nutzen?
 Aspose.PDF bietet eine kostenlose Testversion an, die Sie herunterladen können[Hier](https://releases.aspose.com/).

### Wie kann ich ein signiertes PDF verifizieren?
 Sie können die`PdfFileSignature` Klasse in Aspose.PDF, um die Signaturen in Ihrem PDF-Dokument zu überprüfen.

### Wo finde ich weitere Dokumentation zu Aspose.PDF?
 Sie können die[Aspose.PDF-Dokumentation](https://reference.aspose.com/pdf/net/) für weitere Einzelheiten und Beispiele.