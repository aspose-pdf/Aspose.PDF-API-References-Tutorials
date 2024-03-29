---
title: Geben Sie Anmeldeinformationen während der HTML-zu-PDF-Umwandlung an
linktitle: Geben Sie Anmeldeinformationen während der HTML-zu-PDF-Umwandlung an
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren von HTML in PDF durch Bereitstellung von Anmeldeinformationen mit Aspose.PDF für .NET.
type: docs
weight: 240
url: /de/net/document-conversion/provide-credentials-during-html-to-pdf/
---
In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung einer HTML-Datei in PDF und geben dabei Anmeldeinformationen an, wenn Sie mit Aspose.PDF für .NET auf eine sichere URL zugreifen. Wenn Sie die folgenden Schritte ausführen, können Sie HTML-Inhalte mit den entsprechenden Anmeldeinformationen in PDF konvertieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: Sichere HTML-Inhalte abrufen
In diesem Schritt rufen wir mit den entsprechenden Anmeldeinformationen sicheren HTML-Inhalt von einer URL ab. Verwenden Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie eine Anfrage für die URL.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Legen Sie bei Bedarf für den Server Anmeldeinformationen fest.
request.Credentials = CredentialCache.DefaultCredentials;
// Holen Sie sich die Antwort.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Rufen Sie den Stream ab, der den vom Server zurückgegebenen Inhalt enthält.
Stream dataStream = response. GetResponseStream();
// Öffnen Sie den Stream mit einem StreamReader, um den Zugriff zu erleichtern.
StreamReader reader = new StreamReader(dataStream);
// Lesen Sie den Inhalt.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Unbedingt austauschen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem Sie die resultierende PDF-Datei speichern möchten.

## Schritt 2: Konvertieren Sie HTML in PDF, indem Sie Anmeldeinformationen angeben
Jetzt laden wir den abgerufenen HTML-Inhalt und konvertieren ihn unter Angabe der entsprechenden Anmeldeinformationen in das PDF-Format. Verwenden Sie den folgenden Code:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Laden Sie die HTML-Datei
Document pdfDocument = new Document(stream, options);
```

## Schritt 3: Speichern der resultierenden PDF-Datei
Abschließend speichern wir die resultierende PDF-Datei. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie die resultierende PDF-Datei
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Der obige Code speichert die resultierende PDF-Datei unter dem Dateinamen`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Beispielquellcode für die Bereitstellung von Anmeldeinformationen bei der Umwandlung von HTML in PDF mit Aspose.PDF für .NET

```csharp
try
{
	
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Erstellen Sie eine Anfrage für die URL.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Wenn der Server dies erfordert, legen Sie die Anmeldeinformationen fest.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Holen Sie sich die Antwort.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Rufen Sie den Stream ab, der den vom Server zurückgegebenen Inhalt enthält.
	Stream dataStream = response.GetResponseStream();
	// Öffnen Sie den Stream mit einem StreamReader, um den Zugriff zu erleichtern.
	StreamReader reader = new StreamReader(dataStream);
	// Lesen Sie den Inhalt.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// HTML-Datei laden
	Document pdfDocument = new Document(stream, options);
	// Speichern Sie die resultierende Datei
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess der Konvertierung einer HTML-Datei in PDF behandelt und dabei Anmeldeinformationen bereitgestellt, wenn mit Aspose.PDF für .NET auf eine sichere URL zugegriffen wird. Wenn Sie die oben beschriebenen Anweisungen befolgen, können Sie HTML-Inhalte erfolgreich in PDF konvertieren und dabei die richtigen Anmeldeinformationen angeben.

### FAQs

#### F: Was ist Aspose.PDF für .NET?

A: Aspose.PDF für .NET ist eine robuste Bibliothek, die Entwicklern die Arbeit mit PDF-Dokumenten in C#-Anwendungen ermöglicht. Es bietet eine breite Palette an Funktionen, einschließlich der Konvertierung von HTML in PDF.

#### F: Wie kann ich sichere HTML-Inhalte von einer URL abrufen?

 A: Um sichere HTML-Inhalte von einer URL abzurufen, können Sie die verwenden`WebRequest` Klasse in C#. Stellen Sie sicher, dass Sie die entsprechenden Anmeldeinformationen mithilfe von festlegen`Credentials` Eigentum.

#### F: Was sind die Voraussetzungen für dieses Tutorial?

A: Bevor Sie mit dem Tutorial fortfahren, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

#### F: Wie geht Aspose.PDF für .NET mit externen Ressourcen um, während es HTML in PDF konvertiert?

 A: Aspose.PDF für .NET bietet das`HtmlLoadOptions`Klasse zur Handhabung externer Ressourcen während der HTML-zu-PDF-Konvertierung. Sie können die Anmeldeinformationen für externe Ressourcen mithilfe von festlegen`ExternalResourcesCredentials` Eigentum.

#### F: Kann ich den Dateinamen für die resultierende PDF-Datei anpassen?

 A: Ja, Sie können den Dateinamen für die resultierende PDF-Datei anpassen, indem Sie den Code ändern, der das PDF-Dokument speichert. Ändern Sie einfach den gewünschten Dateinamen im`pdfDocument.Save()` Methode.