---
title: डिजिटल रूप से साइन इन करें PDF फ़ाइल
linktitle: डिजिटल रूप से साइन इन करें PDF फ़ाइल
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ PDF फ़ाइल में डिजिटल रूप से हस्ताक्षर करना सीखें।
type: docs
weight: 40
url: /hi/net/programming-with-security-and-signatures/digitally-sign/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल में डिजिटल रूप से हस्ताक्षर करने की प्रक्रिया से अवगत कराएँगे। डिजिटल हस्ताक्षर एक अद्वितीय इलेक्ट्रॉनिक फ़िंगरप्रिंट जोड़कर दस्तावेज़ की प्रामाणिकता और अखंडता की गारंटी देता है।

## चरण 1: पूर्वापेक्षाएँ

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान
- अपनी मशीन पर Visual Studio स्थापित करना
- .NET के लिए Aspose.PDF लाइब्रेरी स्थापित

## चरण 2: पर्यावरण सेटअप

आरंभ करने के लिए, अपना विकास वातावरण स्थापित करने हेतु इन चरणों का पालन करें:

1. Visual Studio खोलें और एक नया C# प्रोजेक्ट बनाएं।
2. आवश्यक नामस्थानों को अपनी कोड फ़ाइल में आयात करें:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## चरण 3: डिजिटल हस्ताक्षर

पहला कदम पीडीएफ फाइल पर डिजिटल हस्ताक्षर करना है। दिया गया कोड दिखाता है कि .NET के लिए Aspose.PDF के साथ डिजिटल हस्ताक्षर कैसे बनाएं।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

यह कोड एक पीडीएफ फाइल को लोड करता है, एक निर्दिष्ट स्वरूप के साथ एक डिजिटल हस्ताक्षर बनाता है, फिर जोड़े गए हस्ताक्षर के साथ पीडीएफ फाइल को सेव कर देता है।

## चरण 4: हस्ताक्षर सत्यापन

डिजिटल हस्ताक्षर जोड़ने के बाद, आप जांच सकते हैं कि पीडीएफ फाइल में वैध हस्ताक्षर है या नहीं।

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // कुछ करो
                     }
                 }
             }
         }
     }
}
```

यह कोड पीडीएफ फाइल के प्रथम हस्ताक्षर को सत्यापित करता है तथा यदि हस्ताक्षर प्रमाणित है तथा उसमें विशिष्ट अनुमतियां हैं तो अतिरिक्त क्रियाएं करता है।

### .NET के लिए Aspose.PDF का उपयोग करके डिजिटल रूप से साइन करने के लिए नमूना स्रोत कोड 
```csharp
try
{
	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // PKCS7/PKCS7डिटैच्ड ऑब्जेक्ट का उपयोग करें
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// हस्ताक्षर का स्वरूप निर्धारित करें
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// तीन में से कोई भी हस्ताक्षर प्रकार बनाएँ
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// आउटपुट पीडीएफ फाइल सहेजें
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // कोई हस्ताक्षर?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // पहले वाले को सत्यापित करें
				{
					if (signature.IsCertified) // प्रमाणित?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // पहुँच की अनुमति प्राप्त करें
						{
							// कुछ करो
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

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल पर सफलतापूर्वक डिजिटल हस्ताक्षर किया है। इस ट्यूटोरियल में डिजिटल हस्ताक्षर जोड़ने से लेकर इसकी वैधता सत्यापित करने तक की चरण-दर-चरण प्रक्रिया को शामिल किया गया है। अब आप अपनी PDF फ़ाइलों को डिजिटल हस्ताक्षरों से सुरक्षित करने के लिए इस सुविधा का उपयोग कर सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: इस ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: यह ट्यूटोरियल आपको .NET के लिए Aspose.PDF का उपयोग करके PDF फ़ाइल पर डिजिटल हस्ताक्षर करने की प्रक्रिया के बारे में बताता है। डिजिटल हस्ताक्षर दस्तावेज़ की प्रामाणिकता और अखंडता सुनिश्चित करने के लिए एक इलेक्ट्रॉनिक फ़िंगरप्रिंट जोड़ते हैं।

#### प्रश्न: शुरू करने से पहले क्या पूर्व शर्तें आवश्यक हैं?

उत्तर: आरंभ करने से पहले, सुनिश्चित करें कि आपको C# प्रोग्रामिंग भाषा की बुनियादी समझ है, Visual Studio स्थापित है, तथा .NET के लिए Aspose.PDF लाइब्रेरी स्थापित है।

#### प्रश्न: मैं विकास परिवेश कैसे स्थापित करूं?

उत्तर: अपने विकास परिवेश को सेट करने के लिए दिए गए चरणों का पालन करें, जिसमें Visual Studio में एक नया C# प्रोजेक्ट बनाना और आवश्यक नामस्थानों को आयात करना शामिल है।

#### प्रश्न: मैं पीडीएफ फाइल में डिजिटल हस्ताक्षर कैसे जोड़ूं?

 उत्तर: दिया गया नमूना कोड यह दर्शाता है कि PDF फ़ाइल को कैसे लोड किया जाए, डिजिटल हस्ताक्षर कैसे बनाया जाए, उपस्थिति कैसे निर्दिष्ट की जाए, तथा हस्ताक्षरित PDF फ़ाइल को कैसे सहेजा जाए। डिजिटल हस्ताक्षर को उपयोग करके जोड़ा जाता है`Certify` की विधि`PdfFileSignature` वस्तु।

#### प्रश्न: मैं डिजिटल हस्ताक्षर की वैधता कैसे सत्यापित करूं?

उत्तर: डिजिटल हस्ताक्षर जोड़ने के बाद, आप हस्ताक्षर की वैधता को सत्यापित करने के लिए नमूना कोड का उपयोग कर सकते हैं। यह जाँचता है कि क्या हस्ताक्षर प्रमाणित है और क्या उसके पास विशिष्ट पहुँच अनुमतियाँ हैं।

####  प्रश्न: इसका क्या मतलब है?`PKCS7` object represent?

 उत्तर:`PKCS7` ऑब्जेक्ट का उपयोग डिजिटल हस्ताक्षरों के लिए क्रिप्टोग्राफ़िक कार्यक्षमता प्रदान करने के लिए किया जाता है। इसका उपयोग प्रदान किए गए नमूना कोड में डिजिटल हस्ताक्षर बनाने के लिए किया जाता है।

#### प्रश्न: क्या मैं डिजिटल हस्ताक्षर के स्वरूप को अनुकूलित कर सकता हूँ?

 उत्तर: हां, आप छवि के पथ को निर्दिष्ट करके डिजिटल हस्ताक्षर की उपस्थिति को अनुकूलित कर सकते हैं।`SignatureAppearance` की संपत्ति`PdfFileSignature` वस्तु।

#### प्रश्न: यदि हस्ताक्षर वैध न हों तो क्या होगा?

उत्तर: यदि हस्ताक्षर वैध नहीं है, तो सत्यापन प्रक्रिया विफल हो जाएगी, और सत्यापन कोड ब्लॉक के भीतर संबंधित क्रियाएं निष्पादित नहीं होंगी।

#### प्रश्न: मैं अपने डिजिटल हस्ताक्षरों की सुरक्षा कैसे सुनिश्चित कर सकता हूं?

उत्तर: डिजिटल हस्ताक्षर सुरक्षित होते हैं और प्रामाणिकता और अखंडता सुनिश्चित करने के लिए क्रिप्टोग्राफ़िक तकनीकों का उपयोग करते हैं। सुनिश्चित करें कि आप अपनी निजी कुंजी को सुरक्षित रखें और डिजिटल हस्ताक्षरों को संभालने के लिए सर्वोत्तम प्रथाओं का पालन करें।

#### प्रश्न: क्या मैं एक पीडीएफ में एकाधिक डिजिटल हस्ताक्षर जोड़ सकता हूँ?

 उत्तर: हां, आप पीडीएफ फाइल में एकाधिक डिजिटल हस्ताक्षर जोड़ सकते हैं।`PdfFileSignature` वस्तु का`Sign` या`Certify` प्रत्येक हस्ताक्षर का अपना स्वरूप और विन्यास होगा।