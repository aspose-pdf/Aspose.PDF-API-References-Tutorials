---
title: Add Attachment In PDF File
linktitle: Add Attachment In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add attachment in PDF file using Aspose.PDF for .NET. Step-by-step guide for easy handling.
type: docs
weight: 10
url: /fr/net/programming-with-attachments/add-attachment/
---
In this tutorial, we will walk you through the following C# source code step by step to add an attachment in PDF file using Aspose.PDF for .NET.

Make sure you have installed the Aspose.PDF library and set up your development environment before you begin. Also have basic knowledge of C# programming.

### Step 1: Document Directory Setup

In the provided source code, you need to specify the directory where the PDF file you want to add the attachment is located. Change the "dataDir" variable to the desired directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Step 2: Open the existing PDF document

We open the existing PDF document using the specified path.

```csharp
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
```

### Step 3: Setting up the new file to add as an attachment

We configure the new file that we want to add as an attachment. In this example, we add a text file with the name "test.txt" and a description "Example text file".

```csharp
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
```

### Step 4: Adding the attachment to the document's attachments collection

We add the attachment to the document's attachments collection.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Step 5: Saving the new output file

Finally, we save the resulting new PDF file with the name "AddAttachment_out.pdf" in the specified directory.

```csharp
pdfDocument.Save(dataDir + "AddAttachment_out.pdf");
```

### Sample source code for Add Attachment using Aspose.PDF for .NET
 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
// Setup new file to be added as attachment
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
// Add attachment to document's attachment collection
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "AddAttachment_out.pdf";
// Save new output
pdfDocument.Save(dataDir);
Console.WriteLine("\nSample text file attached successfully.\nFile saved at " + dataDir);

```

## Conclusion

In this tutorial, we explained how to add an attachment to a PDF file using Aspose.PDF for .NET. You can now use this knowledge to add additional files as attachments to your PDF documents.

### FAQ's for add attachment in PDF file

#### Q: Why would I need to add attachments to a PDF file?

A: Adding attachments to a PDF file allows you to include supplementary materials, such as supporting documents, images, or files, which can provide additional context or information to the PDF's content.

#### Q: How does Aspose.PDF for .NET simplify the process of adding attachments?

A: Aspose.PDF for .NET provides a streamlined API that allows you to easily add attachments to PDF files. The provided source code demonstrates step-by-step how to accomplish this task.

#### Q: What types of files can be attached to a PDF using Aspose.PDF for .NET?

A: Aspose.PDF for .NET supports attaching various types of files, including text files, images, documents, spreadsheets, and more, as long as they are accessible from your development environment.

#### Q: Is there a limit to the number of attachments that can be added to a PDF file?

A: There is no strict limit to the number of attachments that can be added, but it's important to consider the overall file size and potential impact on document performance.

#### Q: Can I customize the description of the attached files?

A: Yes, you can customize the description of each attached file. This description provides additional context for the attached file and helps users understand its purpose.

#### Q: Are there any file size considerations when adding attachments?

A: While attachments can increase the overall file size of the PDF, Aspose.PDF for .NET ensures efficient attachment handling to minimize any negative impact on document performance.

#### Q: Can attachments be added to specific pages within the PDF document?

A: Attachments are associated with the entire PDF document, rather than specific pages. They are accessible to users through the attachment panel in PDF viewers.

#### Q: How can I verify that the attachment was added successfully?

A: After following the provided source code, you can open the resulting PDF file to confirm that the attached file is accessible through the attachment panel.

#### Q: Can I remove or update attachments after they have been added?

A: Yes, you can modify or remove attachments from a PDF file using Aspose.PDF for .NET's API, giving you flexibility in managing attachments as needed.