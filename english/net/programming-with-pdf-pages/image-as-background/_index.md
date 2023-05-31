---
title: Image As Background
linktitle: Image As Background
second_title: Aspose.PDF for .NET API Reference
description: 
type: docs
weight: 110
url: /pdf/net/programming-with-pdf-pages/image-as-background/
---



```csharp

            
            // The path to the documents directory.
            string dataDir = RunExamples.GetDataDir_AsposePdf_Pages();

            // Create a new Document object
            Document doc = new Document();

            // Add a new page to document object
            Page page = doc.Pages.Add();

            // Create Background Artifact object
            BackgroundArtifact background = new BackgroundArtifact();

            // Specify the image for backgroundartifact object
            background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");

            // Add backgroundartifact to artifacts collection of page
            page.Artifacts.Add(background);

            dataDir = dataDir + "ImageAsBackground_out.pdf";
            // Save the document
            doc.Save(dataDir);
            
            System.Console.WriteLine("\nImage as page background added successfully.\nFile saved at " + dataDir);
        
```

