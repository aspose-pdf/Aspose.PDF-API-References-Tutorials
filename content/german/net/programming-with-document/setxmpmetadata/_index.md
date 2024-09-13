---
title: XMPMetadata in PDF-Datei festlegen
linktitle: XMPMetadata in PDF-Datei festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET XMP-Metadaten in einer PDF-Datei festlegen. Diese Schritt-für-Schritt-Anleitung führt Sie durch den gesamten Prozess, vom Einrichten bis zum Speichern des Dokuments.
type: docs
weight: 330
url: /de/net/programming-with-document/setxmpmetadata/
---
## Einführung

Möchten Sie Ihren PDF-Dateien Metadaten hinzufügen? Vielleicht möchten Sie Informationen wie Erstellungsdatum, Spitzname oder benutzerdefinierte Eigenschaften hinzufügen. Dann sind Sie hier genau richtig! In diesem Tutorial erfahren Sie, wie Sie mit Aspose.PDF für .NET XMP-Metadaten in einer PDF-Datei festlegen. Wir führen Sie durch jeden Schritt des Prozesses und erklären ihn auf einfache und ansprechende Weise. Egal, ob Sie Anfänger oder erfahrener Entwickler sind, Sie werden diese Anleitung leicht befolgen können.

## Voraussetzungen

Bevor wir uns in den Code stürzen, müssen ein paar Dinge bereitstehen:

1.  Aspose.PDF für .NET-Bibliothek: Wenn Sie dies noch nicht getan haben, laden Sie die neueste Version von Aspose.PDF für .NET herunter von[Hier](https://releases.aspose.com/pdf/net/).
2. Entwicklungsumgebung: Sie benötigen Visual Studio oder eine andere .NET-Entwicklungsumgebung, um den Code zu schreiben und auszuführen.
3. Grundkenntnisse in C#: Keine Sorge, wir halten die Dinge einfach, aber ein grundlegendes Verständnis von C# ist hilfreich.

Sie benötigen außerdem ein PDF-Dokument zum Arbeiten. Wenn Sie keins haben, können Sie ein Beispiel-PDF erstellen oder eines aus dem Internet herunterladen.

## Pakete importieren

Bevor wir mit dem Schreiben des Codes beginnen, müssen Sie die erforderlichen Pakete in Ihr Projekt importieren.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

Kommen wir nun zum Kern des Tutorials: Festlegen von XMP-Metadaten in einer PDF-Datei mithilfe von Aspose.PDF für .NET. Wir werden dies in mehrere Schritte aufteilen, damit es leicht nachvollziehbar ist.

## Schritt 1: Einrichten des Verzeichnispfads

 Als erstes müssen Sie das Verzeichnis angeben, in dem Ihre PDF-Datei gespeichert ist. Wenn sich Ihr Dokument woanders befindet, ändern Sie einfach die`dataDir` Variable, um auf den richtigen Ort zu verweisen.

Stellen Sie sich diesen Schritt so vor, als ob Sie Ihrem Code die Heimatadresse geben, unter der er Ihre PDF-Datei finden kann. Ohne diese Adresse wüsste er nicht, wo er suchen soll.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Hier teilen Sie dem Programm mit, wo sich Ihre Datei befindet. Dies ist wichtig, denn wenn Sie nicht den richtigen Pfad angeben, kann das Programm Ihre PDF-Datei nicht öffnen.

## Schritt 2: Öffnen Sie das PDF-Dokument

 Nachdem wir nun das Verzeichnis festgelegt haben, besteht der nächste Schritt darin, Ihr PDF-Dokument mit dem`Document` Klasse von Aspose.PDF.

Stellen Sie sich vor, Sie öffnen ein gedrucktes Buch. Dieser Schritt ist das digitale Äquivalent zum Öffnen der PDF-Datei, damit Sie mit den Änderungen beginnen können.

```csharp
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

 Diese Codezeile lädt die PDF-Datei in das`pdfDocument` Objekt. Stellen Sie sicher, dass der Dateiname mit dem in Ihrem Verzeichnis übereinstimmt, sonst gibt das Programm einen Fehler aus.

## Schritt 3: XMP-Metadateneigenschaften festlegen

Und jetzt geschieht die Magie! Nachdem wir das PDF-Dokument geladen haben, können wir die Metadateneigenschaften wie das Erstellungsdatum, einen Spitznamen oder jede beliebige benutzerdefinierte Eigenschaft festlegen.

Betrachten Sie diesen Schritt als das Ausfüllen des Abschnitts „Über mich“ Ihres Profils. Dort fügen Sie das Erstellungsdatum, einen Spitznamen oder andere Details hinzu, die in die PDF-Datei eingebettet werden sollen.

```csharp
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

Lassen Sie es uns aufschlüsseln:
- CreateDate: Diese Eigenschaft speichert das Erstellungsdatum der PDF-Datei. Wir setzen es auf das aktuelle Datum und die aktuelle Uhrzeit.
- Spitzname: Genau wie bei einem persönlichen Spitznamen können Sie einen Spitznamen für das Dokument festlegen.
- CustomProperty: Hier können Sie alle benutzerdefinierten Informationen hinzufügen, die für Ihr Dokument relevant sind.

## Schritt 4: Speichern Sie das aktualisierte PDF-Dokument

 Nach dem Festlegen der XMP-Metadaten ist es an der Zeit, das aktualisierte PDF-Dokument zu speichern. Wir ändern die`dataDir` Pfad, um sicherzustellen, dass die neue Datei unter einem anderen Namen gespeichert wird.

Stellen Sie sich vor, Sie haben eine wichtige Notiz in Ihr Notizbuch geschrieben. Jetzt müssen Sie es wieder ins Regal legen, aber dieses Mal mit zusätzlichen Details. Dieser Schritt speichert Ihr neues „Notizbuch“ mit den Metadaten.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
pdfDocument.Save(dataDir);
```

 Diese Codezeile speichert das aktualisierte PDF unter dem Namen`SetXMPMetadata_out.pdf`. Sie können den Dateinamen bei Bedarf ändern.

## Schritt 5: Eine Erfolgsmeldung anzeigen

Um zu bestätigen, dass alles reibungslos gelaufen ist, geben wir eine Meldung an die Konsole aus. Dieser Schritt ist optional, aber es ist immer schön, eine Bestätigung zu erhalten, oder?

```csharp
Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);
```

Diese Zeile gibt eine Meldung in der Konsole aus, die Sie darüber informiert, dass die Metadaten erfolgreich hinzugefügt wurden und die Datei am angegebenen Speicherort gespeichert ist.

## Abschluss

Und da haben Sie es! In nur wenigen einfachen Schritten haben wir gelernt, wie Sie mit Aspose.PDF für .NET XMP-Metadaten in einer PDF-Datei festlegen. Dies ist eine großartige Möglichkeit, Ihren PDF-Dateien zusätzliche Informationen hinzuzufügen, sei es das Erstellungsdatum, eine benutzerdefinierte Eigenschaft oder andere Metadaten, die für Ihr Dokument wichtig sind.


## Häufig gestellte Fragen

### Was sind XMP-Metadaten in einer PDF-Datei?  
XMP-Metadaten beziehen sich auf die eingebetteten Daten in einer PDF-Datei, die verschiedene Eigenschaften des Dokuments beschreiben, wie etwa das Erstellungsdatum, den Autor und benutzerdefinierte Eigenschaften.

### Kann ich meiner PDF mehrere benutzerdefinierte Eigenschaften hinzufügen?  
 Ja, Sie können beliebig viele benutzerdefinierte Eigenschaften hinzufügen, indem Sie`Metadata`Objekt, indem Sie einfach neuen Schlüsseln Werte zuweisen.

### Benötige ich eine Lizenz, um Aspose.PDF für .NET zu verwenden?  
 Ja, Aspose.PDF für .NET erfordert eine Lizenz, aber Sie können es auch mit einem[Kostenlose Testversion](https://releases.aspose.com/).

### Was passiert, wenn der Dateipfad falsch ist?  
Wenn der Dateipfad falsch ist, gibt das Programm einen Fehler aus, der besagt, dass die Datei nicht gefunden werden konnte. Stellen Sie sicher, dass Dateiname und Pfad korrekt sind.

### Kann ich die Metadaten einer verschlüsselten PDF-Datei ändern?  
Wenn die PDF-Datei verschlüsselt ist, müssen Sie sie zuerst entschlüsseln, bevor Sie die Metadaten ändern.