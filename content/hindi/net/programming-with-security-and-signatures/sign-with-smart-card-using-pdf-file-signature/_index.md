---
title: स्मार्ट कार्ड से पीडीएफ फाइल हस्ताक्षर का उपयोग करके हस्ताक्षर करें
linktitle: स्मार्ट कार्ड से पीडीएफ फाइल हस्ताक्षर का उपयोग करके हस्ताक्षर करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके स्मार्ट कार्ड से अपनी PDF फ़ाइलों पर सुरक्षित रूप से हस्ताक्षर करें।
type: docs
weight: 110
url: /hi/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
स्मार्ट कार्ड के साथ डिजिटल हस्ताक्षर PDF फ़ाइलों पर हस्ताक्षर करने का एक सुरक्षित तरीका है। .NET के लिए Aspose.PDF के साथ, आप निम्न स्रोत कोड का पालन करके स्मार्ट कार्ड का उपयोग करके आसानी से PDF फ़ाइल पर हस्ताक्षर कर सकते हैं:

## चरण 1: आवश्यक लाइब्रेरीज़ आयात करें

आरंभ करने से पहले, आपको अपने C# प्रोजेक्ट के लिए आवश्यक लाइब्रेरीज़ आयात करनी होंगी। यहाँ आवश्यक आयात निर्देश दिए गए हैं:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## चरण 2: दस्तावेज़ फ़ोल्डर का पथ सेट करें

 इस चरण में, आपको उस फ़ोल्डर का पथ निर्दिष्ट करना होगा जिसमें वह PDF फ़ाइल है जिस पर आप हस्ताक्षर करना चाहते हैं।`"YOUR DOCUMENTS DIRECTORY"` अपने दस्तावेज़ फ़ोल्डर के वास्तविक पथ के साथ निम्नलिखित कोड में:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 3: पीडीएफ दस्तावेज़ लोड करें

अब हम निम्नलिखित कोड का उपयोग करके हस्ताक्षरित करने हेतु PDF दस्तावेज़ लोड करेंगे:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## चरण 4: स्मार्ट कार्ड से हस्ताक्षर करें

 इस चरण में, हम स्मार्ट कार्ड का उपयोग करके हस्ताक्षर करेंगे।`PdfFileSignature` कक्षा से`Facades`लाइब्रेरी। हम विंडोज सर्टिफिकेट स्टोर से स्मार्ट कार्ड सर्टिफिकेट चुनते हैं और आवश्यक हस्ताक्षर जानकारी निर्दिष्ट करते हैं। यहाँ संबंधित कोड है:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // स्टोर में प्रमाणपत्र का चयन करें
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## चरण 5: हस्ताक्षर सत्यापित करें

 अंत में, हम हस्ताक्षरित पीडीएफ फाइल के हस्ताक्षर को सत्यापित करते हैं`PdfFileSignature` क्लास। हम हस्ताक्षरों के नाम प्राप्त करते हैं और उन्हें एक-एक करके जाँचते हैं। यदि कोई हस्ताक्षर सत्यापन में विफल रहता है, तो एक अपवाद फेंका जाता है। यहाँ संगत कोड है:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

### .NET के लिए Aspose.PDF का उपयोग करके स्मार्ट कार्ड का उपयोग करके पीडीएफ फ़ाइल हस्ताक्षर के साथ हस्ताक्षर के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// विंडोज़ प्रमाणपत्र स्टोर में प्रमाणपत्र चयन के साथ हस्ताक्षर करें
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// स्टोर में मैन्युअल रूप से प्रमाणपत्र चुनें
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

बधाई हो! अब आपके पास .NET के लिए Aspose.PDF का उपयोग करके स्मार्ट कार्ड से PDF फ़ाइल पर हस्ताक्षर करने के लिए चरण-दर-चरण मार्गदर्शिका है। आप अपने PDF दस्तावेज़ों में सुरक्षित डिजिटल हस्ताक्षर जोड़ने के लिए इस कोड का उपयोग कर सकते हैं।

उन्नत डिजिटल हस्ताक्षर और प्रमाणपत्र प्रबंधन सुविधाओं के बारे में अधिक जानकारी के लिए आधिकारिक Aspose.PDF दस्तावेज़ अवश्य देखें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मुझे स्मार्ट कार्ड से पीडीएफ फाइलों पर हस्ताक्षर करने पर विचार क्यों करना चाहिए?

उत्तर: स्मार्ट कार्ड से पीडीएफ फाइलों पर हस्ताक्षर करने से दस्तावेज़ की प्रामाणिकता और अखंडता सुनिश्चित करके सुरक्षा बढ़ जाती है। स्मार्ट कार्ड-आधारित हस्ताक्षर उच्च स्तर का विश्वास और अनुपालन प्रदान करते हैं।

#### प्रश्न: स्मार्ट कार्ड-आधारित डिजिटल हस्ताक्षर कैसे काम करता है?

उत्तर: स्मार्ट कार्ड-आधारित डिजिटल हस्ताक्षर में एक अद्वितीय डिजिटल हस्ताक्षर बनाने के लिए स्मार्ट कार्ड पर संग्रहीत क्रिप्टोग्राफ़िक कुंजी का उपयोग करना शामिल है। यह हस्ताक्षर पीडीएफ फ़ाइल से जुड़ा होता है, जिससे प्राप्तकर्ता दस्तावेज़ की उत्पत्ति और अखंडता को सत्यापित कर सकते हैं।

#### प्रश्न: स्मार्ट कार्ड-आधारित हस्ताक्षर में .NET के लिए Aspose.PDF की क्या भूमिका है?

उत्तर: .NET के लिए Aspose.PDF PDF फ़ाइलों के स्मार्ट कार्ड-आधारित डिजिटल हस्ताक्षर को सुविधाजनक बनाने के लिए उपकरणों और पुस्तकालयों का एक व्यापक सेट प्रदान करता है। यह प्रक्रिया को सरल बनाता है और सुरक्षित दस्तावेज़ हस्ताक्षर सुनिश्चित करता है।

#### प्रश्न: क्या मैं हस्ताक्षर करने के लिए कोई विशिष्ट स्मार्ट कार्ड प्रमाणपत्र चुन सकता हूँ?

उत्तर: हाँ, आप हस्ताक्षर करने के लिए Windows प्रमाणपत्र स्टोर से एक विशिष्ट स्मार्ट कार्ड प्रमाणपत्र चुन सकते हैं। .NET के लिए Aspose.PDF आपको अपने एप्लिकेशन में प्रमाणपत्र चयन को सहजता से एकीकृत करने की अनुमति देता है।

#### प्रश्न: प्रदान किया गया स्रोत कोड स्मार्ट कार्ड-आधारित हस्ताक्षर को कैसे संभालता है?

उत्तर: स्रोत कोड यह दर्शाता है कि PDF दस्तावेज़ को कैसे बाँधा जाए, स्मार्ट कार्ड प्रमाणपत्र का चयन कैसे किया जाए, हस्ताक्षर जानकारी निर्दिष्ट की जाए और डिजिटल हस्ताक्षर कैसे बनाया जाए। यह यह भी दर्शाता है कि हस्ताक्षर की वैधता को कैसे सत्यापित किया जाए।

#### प्रश्न: क्या मैं एक ही पीडीएफ फाइल में स्मार्ट कार्ड का उपयोग करके एकाधिक हस्ताक्षर कर सकता हूं?

उत्तर: बिल्कुल, आप एक ही PDF फ़ाइल पर कई स्मार्ट कार्ड-आधारित हस्ताक्षर लागू कर सकते हैं। प्रत्येक हस्ताक्षर अद्वितीय है और दस्तावेज़ की समग्र सुरक्षा में योगदान देता है।

#### प्रश्न: यदि सत्यापन चरण के दौरान हस्ताक्षर सत्यापन में विफल हो जाए तो क्या होगा?

उत्तर: यदि कोई हस्ताक्षर सत्यापन में विफल रहता है, तो एक अपवाद फेंका जाता है, जो दर्शाता है कि हस्ताक्षर मान्य नहीं है। यह सुनिश्चित करता है कि केवल मान्य और विश्वसनीय हस्ताक्षर ही स्वीकार किए जाते हैं।

#### प्रश्न: क्या स्मार्ट कार्ड-आधारित हस्ताक्षर सभी प्रकार के PDF दस्तावेज़ों के साथ संगत है?

उत्तर: हां, स्मार्ट कार्ड-आधारित हस्ताक्षर सभी प्रकार के पीडीएफ दस्तावेजों के साथ संगत है। आप विभिन्न प्रकार की पीडीएफ फाइलों पर डिजिटल हस्ताक्षर लागू कर सकते हैं, जिसमें फॉर्म, रिपोर्ट और बहुत कुछ शामिल हैं।

#### प्रश्न: मैं उन्नत डिजिटल हस्ताक्षर और प्रमाणपत्र प्रबंधन के बारे में अधिक जानकारी कैसे प्राप्त कर सकता हूँ?

उत्तर: उन्नत डिजिटल हस्ताक्षर सुविधाओं, प्रमाणपत्र प्रबंधन और दस्तावेज़ सुरक्षा सुनिश्चित करने के सर्वोत्तम तरीकों के बारे में विस्तृत जानकारी के लिए आधिकारिक Aspose.PDF दस्तावेज़ देखें।

#### प्रश्न: स्मार्ट कार्ड-आधारित हस्ताक्षर को लागू करने के लिए मुझे आगे सहायता या समर्थन कहां मिल सकता है?

उत्तर: अतिरिक्त मार्गदर्शन और सहायता के लिए, Aspose.PDF सामुदायिक मंचों पर पहुंचें या स्मार्ट कार्ड-आधारित हस्ताक्षर पर व्यापक जानकारी के लिए दस्तावेज़ देखें।