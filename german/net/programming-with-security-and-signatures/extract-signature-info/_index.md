---
title: Signaturinformationen extrahieren
linktitle: Signaturinformationen extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Extrahieren von Signaturinformationen mit Aspose.PDF für .NET.
type: docs
weight: 80
url: /de/net/programming-with-security-and-signatures/extract-signature-info/
---

Das Extrahieren von Signaturinformationen aus einem PDF-Dokument kann in verschiedenen Szenarien sehr nützlich sein. Unabhängig davon, ob Sie die Authentizität eines signierten Dokuments überprüfen oder das für die Signatur verwendete Zertifikat analysieren müssen, bietet die Bibliothek Aspose.PDF für .NET eine praktische Lösung. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess der Extraktion von Signaturinformationen mithilfe des bereitgestellten C#-Quellcodes.

## Anforderungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Grundkenntnisse der Programmiersprache C#.
2. Aspose.PDF für .NET-Bibliothek auf Ihrem System installiert.
3. Ein gültiges PDF-Dokument mit einem oder mehreren Signaturfeldern.

Kommen wir nun zu den Implementierungsdetails.

## Schritt 1: Importieren der erforderlichen Bibliotheken

 Um zu beginnen, müssen Sie die erforderlichen Bibliotheken in Ihr C#-Projekt importieren. In diesem Fall müssen wir die importieren`Aspose.Pdf` Und`System.IO` Namensräume. Dies können Sie erreichen, indem Sie den folgenden Code am Anfang Ihrer C#-Datei hinzufügen:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Schritt 2: Festlegen des Dokumentpfads

 Als Nächstes müssen Sie den Pfad zu dem PDF-Dokument festlegen, aus dem Sie die Signaturinformationen extrahieren möchten. Ersetzen`"YOUR DOCUMENTS DIRECTORY"` im folgenden Codeausschnitt mit dem tatsächlichen Pfad zu Ihrem Dokument:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Schritt 3: Signaturinformationen extrahieren

Kommen wir nun zum Hauptteil des Codes, in dem wir die Signaturinformationen aus dem PDF-Dokument extrahieren. Wir durchlaufen jedes Feld im Formular des Dokuments und prüfen, ob es sich um ein Signaturfeld handelt. Wenn ein Signaturfeld gefunden wird, fahren wir mit der Extraktion des Zertifikats fort. Fügen Sie den folgenden Codeausschnitt hinzu:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Extrahieren Sie das Zertifikat
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## Schritt 4: Extrahieren des Zertifikats

In diesem Schritt extrahieren wir das Zertifikat aus dem Signaturfeld und speichern es als Datei. Das extrahierte Zertifikat kann weiter analysiert oder zu Validierungszwecken verwendet werden. Der folgende Codeausschnitt veranschaulicht den Extraktions- und Speichervorgang:

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## Schritt 5

: Speichern des Zertifikats

Abschließend speichern wir das extrahierte Zertifikat als Datei. In diesem Beispiel wird das Zertifikat unter dem Namen „input.cer“ im angegebenen Verzeichnis gespeichert. Sie können den Code an Ihre Anforderungen anpassen. Hier ist der Codeausschnitt zum Speichern des Zertifikats:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

Das ist es! Sie haben die Signaturinformationen mit Aspose.PDF für .NET erfolgreich extrahiert. Sie können diesen Code gerne in Ihre eigenen Anwendungen integrieren oder ihn entsprechend Ihren Bedürfnissen modifizieren.

### Beispielquellcode zum Extrahieren von Signaturinformationen mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss

In diesem Tutorial haben wir eine Schritt-für-Schritt-Anleitung zum Extrahieren von Signaturinformationen aus einem PDF-Dokument mithilfe der Aspose.PDF für .NET-Bibliothek besprochen. Wir haben den Prozess des Importierens der erforderlichen Bibliotheken, des Festlegens des Dokumentpfads, des Extrahierens von Signaturinformationen, des Extrahierens des Zertifikats und des Speicherns in einer Datei behandelt. Wenn Sie diese Schritte befolgen, können Sie Signaturdetails einfach abrufen und bei Bedarf damit arbeiten.