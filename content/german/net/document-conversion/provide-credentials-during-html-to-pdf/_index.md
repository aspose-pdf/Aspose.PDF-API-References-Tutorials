---
title: Geben Sie beim Konvertieren von HTML in PDF Ihre Anmeldeinformationen ein
linktitle: Geben Sie beim Konvertieren von HTML in PDF Ihre Anmeldeinformationen ein
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET HTML in PDF konvertieren. Perfekt für Entwickler, die die Dokumenterstellung optimieren möchten.
type: docs
weight: 240
url: /de/net/document-conversion/provide-credentials-during-html-to-pdf/
---
## Einführung

In der Welt der Softwareentwicklung ist die Konvertierung von HTML in PDF eine gängige Anforderung. Egal, ob Sie Berichte, Rechnungen oder andere Dokumente erstellen, eine zuverlässige Bibliothek für diese Aufgabe kann Ihnen viel Zeit und Mühe sparen. Hier kommt Aspose.PDF für .NET ins Spiel, eine leistungsstarke Bibliothek, mit der Entwickler PDF-Dokumente problemlos erstellen, bearbeiten und konvertieren können. In diesem Tutorial führen wir Sie durch den Prozess der Verwendung von Aspose.PDF zum Konvertieren von HTML in PDF und stellen Ihnen gleichzeitig Anmeldeinformationen für den sicheren Zugriff zur Verfügung. Also, schnappen Sie sich Ihren Programmierhut und legen Sie los!

## Voraussetzungen

Bevor wir beginnen, müssen Sie einige Dinge vorbereitet haben:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Dies wird unsere Entwicklungsumgebung sein.
2.  Aspose.PDF für .NET: Sie können die Bibliothek herunterladen von der[Webseite](https://releases.aspose.com/pdf/net/) . Wenn Sie es erst einmal ausprobieren möchten, können Sie auch eine[Kostenlose Testversion](https://releases.aspose.com/).
3. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, verstehen Sie die Beispiele besser.
4. Internetzugang: Da wir HTML-Inhalte von einer URL abrufen, stellen Sie sicher, dass Sie über eine aktive Internetverbindung verfügen.

## Pakete importieren

Um mit Aspose.PDF zu beginnen, müssen Sie die erforderlichen Pakete in Ihr Projekt importieren. So können Sie das tun:

1. Öffnen Sie Ihr Visual Studio-Projekt.
2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt und wählen Sie „NuGet-Pakete verwalten“ aus.
3. Suchen Sie nach „Aspose.PDF“ und installieren Sie die neueste Version.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Net;
```
Nachdem wir nun alles eingerichtet haben, unterteilen wir den Prozess der Konvertierung von HTML in PDF mit Anmeldeinformationen in überschaubare Schritte.

## Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein

Bevor wir HTML in PDF konvertieren können, müssen wir angeben, wo unser Ausgabe-PDF gespeichert wird. Dies geschieht durch die Definition eines Pfads zum Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem Sie Ihre PDF-Datei speichern möchten. Dies kann ein Ordner auf Ihrem Desktop oder ein beliebiger anderer Speicherort auf Ihrem System sein.

## Schritt 2: Erstellen einer Web-Anforderung

 Als nächstes müssen wir eine Anfrage erstellen, um den HTML-Inhalt von einer bestimmten URL abzurufen. Hier verwenden wir die`WebRequest` Klasse.

```csharp
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
```

Hier erstellen wir eine Anfrage an die URL, die das HTML enthält, das wir konvertieren möchten. Stellen Sie sicher, dass Sie die URL durch die URL ersetzen, die Sie verwenden möchten.

## Schritt 3: Anmeldeinformationen festlegen (falls erforderlich)

Wenn der Server Anmeldeinformationen für den Zugriff auf den Inhalt benötigt, müssen wir diese festlegen. Dies geschieht mithilfe des`CredentialCache.DefaultCredentials`.

```csharp
request.Credentials = CredentialCache.DefaultCredentials;
```

 Diese Zeile stellt sicher, dass die Anfrage die Standardanmeldeinformationen des aktuellen Benutzers verwendet. Wenn Sie spezielle Anmeldeinformationen angeben müssen, können Sie eine neue`NetworkCredential` Objekt.

## Schritt 4: Erhalten Sie die Antwort

Nachdem wir unsere Anfrage nun eingerichtet haben, ist es Zeit, die Antwort vom Server zu erhalten.

```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```

Diese Zeile sendet die Anfrage und wartet auf die Antwort des Servers. Wenn alles gut geht, erhalten wir den HTML-Inhalt, den wir brauchen.

## Schritt 5: Lesen Sie den Antwort-Stream

 Sobald wir die Antwort haben, müssen wir den vom Server zurückgegebenen Inhalt lesen. Dies geschieht mithilfe eines`StreamReader`.

```csharp
Stream dataStream = response.GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader.Close();
dataStream.Close();
response.Close();
```

 Hier lesen wir den gesamten Inhalt des Antwortstroms in eine Zeichenfolgevariable namens`responseFromServer`. Vergessen Sie nicht, den Reader und den Stream zu schließen, um Ressourcen freizugeben.

## Schritt 6: HTML in PDF konvertieren

Jetzt kommt der spannende Teil! Wir konvertieren den HTML-Inhalt mit Aspose.PDF in ein PDF-Dokument.

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

Document pdfDocument = new Document(stream, options);
```

In diesem Schritt erstellen wir eine`MemoryStream` aus dem HTML-Inhalt und Einrichten`HtmlLoadOptions`. Dadurch können wir die Basis-URL für alle externen Ressourcen (wie Bilder oder Stylesheets) angeben, auf die das HTML verweisen könnte.

## Schritt 7: Speichern Sie das PDF-Dokument

Schließlich müssen wir das generierte PDF-Dokument im angegebenen Verzeichnis speichern.

```csharp
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Diese Zeile speichert die PDF-Datei unter dem Namen`ProvideCredentialsDuringHTMLToPDF_out.pdf` in dem Verzeichnis, das wir zuvor angegeben haben.

## Abschluss

Und da haben Sie es! Sie haben HTML erfolgreich mit Aspose.PDF für .NET in PDF konvertiert und dabei Anmeldeinformationen für den sicheren Zugriff bereitgestellt. Diese leistungsstarke Bibliothek erleichtert die Handhabung von PDF-Dokumenten und mit nur wenigen Codezeilen können Sie aus HTML-Inhalten professionell aussehende PDFs erstellen. 

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine Bibliothek, mit der Entwickler PDF-Dokumente in .NET-Anwendungen erstellen, bearbeiten und konvertieren können.

### Wie installiere ich Aspose.PDF?
 Sie können Aspose.PDF über den NuGet Package Manager in Visual Studio installieren oder von der[Webseite](https://releases.aspose.com/pdf/net/).

### Kann ich Aspose.PDF kostenlos nutzen?
Ja, Aspose bietet eine kostenlose Testversion an, mit der Sie die Bibliothek vor dem Kauf testen können.

### Welche Dokumenttypen kann ich mit Aspose.PDF erstellen?
Mit Aspose.PDF können Sie eine breite Palette von Dokumenten erstellen, darunter Berichte, Rechnungen und Formulare.

### Wo finde ich Unterstützung für Aspose.PDF?
 Sie finden Unterstützung und können Fragen stellen auf der[Aspose-Supportforum](https://forum.aspose.com/c/pdf/10).