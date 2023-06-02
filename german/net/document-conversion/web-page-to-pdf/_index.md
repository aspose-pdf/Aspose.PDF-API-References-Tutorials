---
title: Webseite in PDF
linktitle: Webseite in PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren einer Webseite in PDF mit Aspose.PDF für .NET.
type: docs
weight: 320
url: /de/net/document-conversion/web-page-to-pdf/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch die Konvertierung einer Webseite in PDF mithilfe der Bibliothek Aspose.PDF für .NET. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren. Am Ende dieses Tutorials werden Sie Webseiten mühelos in PDF-Dokumente konvertieren können.

## Einführung
Das Konvertieren von Webseiten in das PDF-Format ist in vielen Anwendungen eine häufige Anforderung. Durch die Konvertierung von Webinhalten in PDF können Sie das Layout, die Formatierung und die Bilder der ursprünglichen Webseite problemlos beibehalten. Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, mit der Sie diese Konvertierung effizient und genau durchführen können.

## Anforderungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Visual Studio ist auf Ihrem Computer installiert
- Aspose.PDF für .NET-Bibliothek (Sie können sie von der offiziellen Aspose-Website herunterladen)
- Grundkenntnisse der C#-Programmierung


## Schritt 1: Definieren Sie das Dokumentenverzeichnis
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad, in dem Sie die generierte PDF-Datei speichern möchten.

## Schritt 2: Erstellen Sie eine Webanfrage
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
Erstellen Sie ein Webanforderungsobjekt und geben Sie die URL der Webseite an, die Sie konvertieren möchten. Sie können die URL durch eine beliebige Webseite ersetzen.

## Schritt 3: Holen Sie sich die Web-Antwort
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
Senden Sie die Webanfrage und rufen Sie die Antwort vom Server ab.

## Schritt 4: Lesen Sie den Webinhalt
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
 Lesen Sie den Inhalt der Webseite mit a`StreamReader` und speichern Sie es in der`responseFromServer` Variable.

## Schritt 5: HTML in PDF konvertieren
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
 Ein ... kreieren`MemoryStream` Objekt zum Laden des Webseiteninhalts. Erstellen Sie dann eine Instanz von`HtmlLoadOptions` und übergeben Sie die Basis-URL der Webseite. Als nächstes erstellen Sie eine`Document` Objekt mithilfe des geladenen Streams und der HTML-Ladeoptionen. Stellen Sie die ein`IsLandscape` Eigentum zu`true` wenn Sie möchten, dass das PDF im Querformat vorliegt. Speichern Sie abschließend das PDF-Dokument im angegebenen Verzeichnis

.

## Schritt 6: Ausnahmen behandeln
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
Erfassen Sie alle Ausnahmen, die während des Konvertierungsprozesses auftreten können, und zeigen Sie die Fehlermeldung an.

### Beispielquellcode für die Umwandlung einer Webseite in PDF mit Aspose.Words für .NET

```csharp
try
{
	
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Erstellen Sie eine Anfrage für die URL.
	WebRequest request = WebRequest.Create("https:// En.wikipedia.org/wiki/Main_Page");
	// Wenn der Server dies erfordert, legen Sie die Anmeldeinformationen fest.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Zeitüberschreitung in Millisekunden, bevor die Anforderung abläuft
	// Request.Timeout = 100;

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
	HtmlLoadOptions options = new HtmlLoadOptions("https:// En.wikipedia.org/wiki/");


	// HTML-Datei laden
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	// Speichern Sie die Ausgabe im PDF-Format
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man eine Webseite mithilfe der Bibliothek Aspose.PDF für .NET in PDF konvertiert. Wir sind die Schritt-für-Schritt-Anleitung durchgegangen, in der der bereitgestellte C#-Quellcode erläutert wird. Wenn Sie diese Anweisungen befolgen, können Sie die Funktionalität zur Konvertierung von Webseiten in PDF ganz einfach in Ihre eigenen .NET-Anwendungen integrieren.