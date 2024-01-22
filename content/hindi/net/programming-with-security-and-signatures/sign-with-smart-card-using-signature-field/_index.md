---
title: हस्ताक्षर फ़ील्ड का उपयोग करके स्मार्ट कार्ड से हस्ताक्षर करें
linktitle: हस्ताक्षर फ़ील्ड का उपयोग करके स्मार्ट कार्ड से हस्ताक्षर करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके स्मार्ट कार्ड से अपनी पीडीएफ फाइलों पर सुरक्षित रूप से हस्ताक्षर करें।
type: docs
weight: 120
url: /hi/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
स्मार्ट कार्ड से डिजिटल हस्ताक्षर पीडीएफ फाइलों पर हस्ताक्षर करने का एक सुरक्षित तरीका है। .NET के लिए Aspose.PDF के साथ, आप निम्नलिखित स्रोत कोड का पालन करके हस्ताक्षर फ़ील्ड और स्मार्ट कार्ड का उपयोग करके आसानी से एक पीडीएफ फ़ाइल पर हस्ताक्षर कर सकते हैं:

## चरण 1: आवश्यक पुस्तकालय आयात करें

शुरू करने से पहले, आपको अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरी आयात करनी होगी। यहां आवश्यक आयात निर्देश दिए गए हैं:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## चरण 2: दस्तावेज़ फ़ोल्डर में पथ सेट करें

 इस चरण में, आपको उस पीडीएफ फ़ाइल वाले फ़ोल्डर का पथ निर्दिष्ट करना होगा जिस पर आप हस्ताक्षर करना चाहते हैं। प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"`आपके दस्तावेज़ फ़ोल्डर के वास्तविक पथ के साथ निम्नलिखित कोड में:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 3: पीडीएफ दस्तावेज़ को कॉपी करें और खोलें

अब हम निम्नलिखित कोड का उपयोग करके हस्ताक्षरित होने के लिए पीडीएफ दस्तावेज़ को कॉपी और खोलेंगे:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // एक हस्ताक्षर फ़ील्ड बनाएँ
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // स्टोर में प्रमाणपत्र का चयन करें
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // आवश्यक जानकारी के साथ एक बाहरी हस्ताक्षर बनाएं
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## चरण 4: हस्ताक्षर सत्यापित करें

 अंत में, हम का उपयोग करके हस्ताक्षरित पीडीएफ फाइल के हस्ताक्षर को सत्यापित करते हैं`PdfFileSignature` कक्षा। हम हस्ताक्षरित नाम प्राप्त करते हैं और उन्हें एक-एक करके जांचते हैं। यदि कोई हस्ताक्षर सत्यापन में विफल रहता है, तो एक अपवाद फेंक दिया जाता है। यहाँ संबंधित कोड है:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### .NET के लिए Aspose.PDF का उपयोग करके सिग्नेचर फ़ील्ड का उपयोग करके साइन विद स्मार्ट कार्ड के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// विंडोज़ प्रमाणपत्र स्टोर में प्रमाणपत्र चयन के साथ हस्ताक्षर करें
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// स्टोर में प्रमाणपत्र को मैन्युअल रूप से चुना गया
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
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

## निष्कर्ष

बधाई हो! अब आपके पास .NET के लिए Aspose.PDF के साथ एक हस्ताक्षर फ़ील्ड का उपयोग करके स्मार्ट कार्ड के साथ एक पीडीएफ फ़ाइल पर हस्ताक्षर करने के लिए चरण-दर-चरण मार्गदर्शिका है। आप अपने पीडीएफ दस्तावेज़ों में सुरक्षित डिजिटल हस्ताक्षर जोड़ने के लिए इस कोड का उपयोग कर सकते हैं।

उन्नत डिजिटल हस्ताक्षर और प्रमाणपत्र प्रबंधन सुविधाओं पर अधिक जानकारी के लिए आधिकारिक Aspose.PDF दस्तावेज़ को अवश्य देखें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: स्मार्ट कार्ड के साथ डिजिटल हस्ताक्षर के लिए हस्ताक्षर फ़ील्ड का उपयोग करने का क्या लाभ है?

उ: स्मार्ट कार्ड के साथ डिजिटल हस्ताक्षर के लिए हस्ताक्षर फ़ील्ड का उपयोग करना पीडीएफ के भीतर एक निर्दिष्ट क्षेत्र प्रदान करता है जहां हस्ताक्षर लागू किया जाता है। यह दस्तावेज़ की स्पष्टता बढ़ाता है और हस्ताक्षर की प्रामाणिकता सुनिश्चित करता है।

#### प्रश्न: .NET लाइब्रेरी के लिए Aspose.PDF हस्ताक्षर फ़ील्ड के साथ स्मार्ट कार्ड-आधारित डिजिटल हस्ताक्षर की सुविधा कैसे प्रदान करता है?

उ: .NET के लिए Aspose.PDF एक हस्ताक्षर फ़ील्ड बनाने, एक स्मार्ट कार्ड प्रमाणपत्र का चयन करने और पीडीएफ दस्तावेज़ के भीतर एक विशिष्ट क्षेत्र में डिजिटल हस्ताक्षर लागू करने की प्रक्रिया को सरल बनाता है।

#### प्रश्न: स्मार्ट कार्ड-आधारित हस्ताक्षर के लिए एक विशिष्ट प्रमाणपत्र का चयन करना क्यों महत्वपूर्ण है?

उ: एक विशिष्ट प्रमाणपत्र का चयन करने से आप हस्ताक्षरकर्ता को विशिष्ट रूप से पहचान सकते हैं और हस्ताक्षर की अखंडता सुनिश्चित कर सकते हैं। इससे डिजिटल हस्ताक्षर मानकों के साथ विश्वास और अनुपालन स्थापित करने में मदद मिलती है।

#### प्रश्न: प्रदान किया गया स्रोत कोड हस्ताक्षर फ़ील्ड के साथ स्मार्ट कार्ड-आधारित हस्ताक्षर प्रक्रिया को कैसे संभालता है?

ए: स्रोत कोड दर्शाता है कि हस्ताक्षर फ़ील्ड कैसे बनाएं, स्मार्ट कार्ड प्रमाणपत्र का चयन करें और विशिष्ट हस्ताक्षर जानकारी के साथ डिजिटल हस्ताक्षर कैसे लागू करें। यह यह भी दिखाता है कि हस्ताक्षर की वैधता को कैसे सत्यापित किया जाए।

#### प्रश्न: क्या मैं हस्ताक्षर फ़ील्ड के स्वरूप को अनुकूलित कर सकता हूँ?

उ: हाँ, आप अपने दस्तावेज़ के लेआउट के साथ संरेखित करने के लिए हस्ताक्षर फ़ील्ड की उपस्थिति, जैसे उसका आकार, स्थिति और दृश्य प्रतिनिधित्व को अनुकूलित कर सकते हैं।

#### प्रश्न: यदि सत्यापन चरण के दौरान हस्ताक्षर सत्यापन में विफल रहता है तो क्या होगा?

उ: यदि कोई हस्ताक्षर सत्यापन में विफल रहता है, तो एक अपवाद फेंक दिया जाता है, जो दर्शाता है कि हस्ताक्षर मान्य नहीं है। यह सुनिश्चित करता है कि केवल वैध और विश्वसनीय हस्ताक्षर ही स्वीकार किए जाएं।

#### प्रश्न: क्या मैं एक ही पीडीएफ दस्तावेज़ में एकाधिक हस्ताक्षर फ़ील्ड और स्मार्ट कार्ड-आधारित हस्ताक्षर लागू कर सकता हूँ?

उ: बिल्कुल, आप एक ही पीडीएफ दस्तावेज़ के विभिन्न क्षेत्रों में एकाधिक हस्ताक्षर फ़ील्ड और स्मार्ट कार्ड-आधारित हस्ताक्षर लागू कर सकते हैं, जिससे सुरक्षा की कई परतें उपलब्ध होती हैं।

#### प्रश्न: हस्ताक्षर फ़ील्ड का उपयोग समग्र दस्तावेज़ हस्ताक्षर प्रक्रिया को कैसे बढ़ाता है?

उ: हस्ताक्षर फ़ील्ड का उपयोग दस्तावेज़ पर हस्ताक्षर करने की प्रक्रिया को सुव्यवस्थित करता है, क्योंकि यह हस्ताक्षरकर्ता को एक निर्दिष्ट क्षेत्र में अपने हस्ताक्षर रखने के लिए मार्गदर्शन करता है, जिससे हस्ताक्षर प्रक्रिया अधिक व्यवस्थित और उपयोगकर्ता के अनुकूल हो जाती है।

#### प्रश्न: क्या स्मार्ट कार्ड-आधारित हस्ताक्षर के साथ हस्ताक्षर फ़ील्ड का उपयोग करने की कोई सीमाएँ हैं?

उत्तर: स्मार्ट कार्ड-आधारित हस्ताक्षर के साथ हस्ताक्षर फ़ील्ड का उपयोग करने की कोई अंतर्निहित सीमाएँ नहीं हैं। हालाँकि, यह सुनिश्चित करना महत्वपूर्ण है कि चयनित हस्ताक्षर फ़ील्ड स्थान महत्वपूर्ण दस्तावेज़ सामग्री को अस्पष्ट नहीं करता है।

#### प्रश्न: हस्ताक्षर फ़ील्ड के साथ स्मार्ट कार्ड-आधारित हस्ताक्षर लागू करने के लिए मुझे और सहायता या समर्थन कहां मिल सकता है?

उत्तर: अतिरिक्त मार्गदर्शन और समर्थन के लिए, आप आधिकारिक Aspose.PDF दस्तावेज़ और सामुदायिक मंचों का संदर्भ ले सकते हैं, जो सुरक्षित डिजिटल हस्ताक्षर लागू करने के लिए मूल्यवान अंतर्दृष्टि और समाधान प्रदान करते हैं।