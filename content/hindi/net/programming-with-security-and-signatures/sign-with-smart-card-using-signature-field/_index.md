---
title: हस्ताक्षर फ़ील्ड का उपयोग करके स्मार्ट कार्ड से हस्ताक्षर करें
linktitle: हस्ताक्षर फ़ील्ड का उपयोग करके स्मार्ट कार्ड से हस्ताक्षर करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके स्मार्ट कार्ड से अपनी PDF फ़ाइलों पर सुरक्षित रूप से हस्ताक्षर करें।
type: docs
weight: 120
url: /hi/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
स्मार्ट कार्ड के साथ डिजिटल हस्ताक्षर PDF फ़ाइलों पर हस्ताक्षर करने का एक सुरक्षित तरीका है। .NET के लिए Aspose.PDF के साथ, आप निम्न स्रोत कोड का पालन करके हस्ताक्षर फ़ील्ड और स्मार्ट कार्ड का उपयोग करके आसानी से PDF फ़ाइल पर हस्ताक्षर कर सकते हैं:

## चरण 1: आवश्यक लाइब्रेरीज़ आयात करें

आरंभ करने से पहले, आपको अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरीज़ आयात करनी होंगी। यहाँ आवश्यक आयात निर्देश दिए गए हैं:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## चरण 2: दस्तावेज़ फ़ोल्डर का पथ सेट करें

 इस चरण में, आपको उस फ़ोल्डर का पथ निर्दिष्ट करना होगा जिसमें वह PDF फ़ाइल है जिस पर आप हस्ताक्षर करना चाहते हैं।`"YOUR DOCUMENTS DIRECTORY"` अपने दस्तावेज़ फ़ोल्डर के वास्तविक पथ के साथ निम्नलिखित कोड में:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 3: PDF दस्तावेज़ को कॉपी करें और खोलें

अब हम निम्नलिखित कोड का उपयोग करके हस्ताक्षरित किए जाने वाले पीडीएफ दस्तावेज़ को कॉपी करके खोलेंगे:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // हस्ताक्षर फ़ील्ड बनाएँ
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

 अंत में, हम हस्ताक्षरित पीडीएफ फाइल के हस्ताक्षर को सत्यापित करते हैं`PdfFileSignature` क्लास। हम हस्ताक्षरों के नाम प्राप्त करते हैं और उन्हें एक-एक करके जाँचते हैं। यदि कोई हस्ताक्षर सत्यापन में विफल रहता है, तो एक अपवाद फेंका जाता है। यहाँ संगत कोड है:

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

### .NET के लिए Aspose.PDF का उपयोग करके हस्ताक्षर फ़ील्ड का उपयोग करके स्मार्ट कार्ड के साथ हस्ताक्षर करने के लिए नमूना स्रोत कोड 
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
		// स्टोर में मैन्युअल रूप से प्रमाणपत्र चुनें
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

बधाई हो! अब आपके पास .NET के लिए Aspose.PDF के साथ हस्ताक्षर फ़ील्ड का उपयोग करके स्मार्ट कार्ड के साथ PDF फ़ाइल पर हस्ताक्षर करने के लिए चरण-दर-चरण मार्गदर्शिका है। आप अपने PDF दस्तावेज़ों में सुरक्षित डिजिटल हस्ताक्षर जोड़ने के लिए इस कोड का उपयोग कर सकते हैं।

उन्नत डिजिटल हस्ताक्षर और प्रमाणपत्र प्रबंधन सुविधाओं के बारे में अधिक जानकारी के लिए आधिकारिक Aspose.PDF दस्तावेज़ अवश्य देखें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: स्मार्ट कार्ड के साथ डिजिटल हस्ताक्षर के लिए हस्ताक्षर फ़ील्ड का उपयोग करने का क्या लाभ है?

उत्तर: स्मार्ट कार्ड के साथ डिजिटल हस्ताक्षर के लिए हस्ताक्षर फ़ील्ड का उपयोग करने से पीडीएफ के भीतर एक निर्दिष्ट क्षेत्र उपलब्ध होता है जहाँ हस्ताक्षर लागू किया जाता है। इससे दस्तावेज़ की स्पष्टता बढ़ती है और हस्ताक्षर की प्रामाणिकता सुनिश्चित होती है।

#### प्रश्न: .NET लाइब्रेरी के लिए Aspose.PDF हस्ताक्षर फ़ील्ड के साथ स्मार्ट कार्ड-आधारित डिजिटल हस्ताक्षर की सुविधा कैसे प्रदान करता है?

उत्तर: .NET के लिए Aspose.PDF हस्ताक्षर फ़ील्ड बनाने, स्मार्ट कार्ड प्रमाणपत्र का चयन करने और PDF दस्तावेज़ के भीतर एक विशिष्ट क्षेत्र में डिजिटल हस्ताक्षर लागू करने की प्रक्रिया को सरल बनाता है।

#### प्रश्न: स्मार्ट कार्ड-आधारित हस्ताक्षर के लिए विशिष्ट प्रमाणपत्र का चयन क्यों महत्वपूर्ण है?

उत्तर: किसी विशिष्ट प्रमाणपत्र का चयन करने से आप हस्ताक्षरकर्ता की विशिष्ट पहचान कर सकते हैं और हस्ताक्षर की अखंडता सुनिश्चित कर सकते हैं। इससे डिजिटल हस्ताक्षर मानकों के साथ विश्वास और अनुपालन स्थापित करने में मदद मिलती है।

#### प्रश्न: प्रदान किया गया स्रोत कोड हस्ताक्षर फ़ील्ड के साथ स्मार्ट कार्ड-आधारित हस्ताक्षर प्रक्रिया को कैसे संभालता है?

उत्तर: स्रोत कोड दर्शाता है कि हस्ताक्षर फ़ील्ड कैसे बनाएँ, स्मार्ट कार्ड प्रमाणपत्र कैसे चुनें, और विशिष्ट हस्ताक्षर जानकारी के साथ डिजिटल हस्ताक्षर कैसे लागू करें। यह यह भी दिखाता है कि हस्ताक्षर की वैधता को कैसे सत्यापित किया जाए।

#### प्रश्न: क्या मैं हस्ताक्षर फ़ील्ड के स्वरूप को अनुकूलित कर सकता हूँ?

उत्तर: हां, आप अपने दस्तावेज़ के लेआउट के साथ संरेखित करने के लिए हस्ताक्षर फ़ील्ड की उपस्थिति, जैसे इसका आकार, स्थिति और दृश्य प्रतिनिधित्व, को अनुकूलित कर सकते हैं।

#### प्रश्न: यदि सत्यापन चरण के दौरान हस्ताक्षर सत्यापन में विफल हो जाता है तो क्या होगा?

उत्तर: यदि कोई हस्ताक्षर सत्यापन में विफल रहता है, तो एक अपवाद फेंका जाता है, जो दर्शाता है कि हस्ताक्षर मान्य नहीं है। यह सुनिश्चित करता है कि केवल मान्य और विश्वसनीय हस्ताक्षर ही स्वीकार किए जाते हैं।

#### प्रश्न: क्या मैं एक ही PDF दस्तावेज़ पर एकाधिक हस्ताक्षर फ़ील्ड और स्मार्ट कार्ड-आधारित हस्ताक्षर लागू कर सकता हूँ?

उत्तर: बिल्कुल, आप एक ही पीडीएफ दस्तावेज़ के विभिन्न क्षेत्रों में एकाधिक हस्ताक्षर फ़ील्ड और स्मार्ट कार्ड-आधारित हस्ताक्षर लागू कर सकते हैं, जिससे सुरक्षा की कई परतें मिलती हैं।

#### प्रश्न: हस्ताक्षर फ़ील्ड का उपयोग करने से समग्र दस्तावेज़ हस्ताक्षर प्रक्रिया कैसे बेहतर होती है?

उत्तर: हस्ताक्षर क्षेत्र का उपयोग करने से दस्तावेज़ पर हस्ताक्षर करने की प्रक्रिया सरल हो जाती है, क्योंकि यह हस्ताक्षरकर्ता को निर्दिष्ट क्षेत्र में अपना हस्ताक्षर करने के लिए मार्गदर्शन प्रदान करता है, जिससे हस्ताक्षर प्रक्रिया अधिक व्यवस्थित और उपयोगकर्ता-अनुकूल हो जाती है।

#### प्रश्न: क्या स्मार्ट कार्ड-आधारित हस्ताक्षर के साथ हस्ताक्षर फ़ील्ड का उपयोग करने में कोई सीमाएँ हैं?

उत्तर: स्मार्ट कार्ड-आधारित हस्ताक्षर के साथ हस्ताक्षर फ़ील्ड का उपयोग करने में कोई अंतर्निहित सीमाएँ नहीं हैं। हालाँकि, यह सुनिश्चित करना महत्वपूर्ण है कि चुना गया हस्ताक्षर फ़ील्ड स्थान महत्वपूर्ण दस्तावेज़ सामग्री को अस्पष्ट न करे।

#### प्रश्न: हस्ताक्षर फ़ील्ड के साथ स्मार्ट कार्ड-आधारित हस्ताक्षर को कार्यान्वित करने के लिए मुझे आगे सहायता या समर्थन कहां मिल सकता है?

उत्तर: अतिरिक्त मार्गदर्शन और सहायता के लिए, आप आधिकारिक Aspose.PDF दस्तावेज़ और सामुदायिक फ़ोरम देख सकते हैं, जो सुरक्षित डिजिटल हस्ताक्षरों को लागू करने के लिए बहुमूल्य जानकारी और समाधान प्रदान करते हैं।