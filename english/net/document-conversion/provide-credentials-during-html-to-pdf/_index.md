---
title: Provide Credentials During HTML to PDF
linktitle: Provide Credentials During HTML to PDF
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 240
url: /pdf/net/document-conversion/provide-credentials-during-html-to-pdf/
---



```csharp

            try
            {
                
                // The path to the documents directory.
                string dataDir = "YOUR DOCUMENT DIRECTORY";

                // Create a request for the URL.
                WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
                // If required by the server, set the credentials.
                request.Credentials = CredentialCache.DefaultCredentials;
                // Get the response.
                HttpWebResponse response = (HttpWebResponse)request.GetResponse();

                // Get the stream containing content returned by the server.
                Stream dataStream = response.GetResponseStream();
                // Open the stream using a StreamReader for easy access.
                StreamReader reader = new StreamReader(dataStream);
                // Read the content.
                string responseFromServer = reader.ReadToEnd();
                reader.Close();
                dataStream.Close();
                response.Close();

                MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

                HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
                options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

                // Load HTML file
                Document pdfDocument = new Document(stream, options);
                // Save resultant file
                pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
                
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        
```

