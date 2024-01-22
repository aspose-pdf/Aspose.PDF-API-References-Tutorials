---
title: HTML से पीडीएफ के दौरान क्रेडेंशियल प्रदान करें
linktitle: HTML से पीडीएफ के दौरान क्रेडेंशियल प्रदान करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF के साथ क्रेडेंशियल प्रदान करके HTML को पीडीएफ में बदलने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 240
url: /hi/net/document-conversion/provide-credentials-during-html-to-pdf/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके एक सुरक्षित यूआरएल तक पहुंचने पर क्रेडेंशियल प्रदान करते हुए एक HTML फ़ाइल को पीडीएफ में परिवर्तित करने की प्रक्रिया के बारे में बताएंगे। नीचे दिए गए चरणों का पालन करके, आप उपयुक्त क्रेडेंशियल्स का उपयोग करके HTML सामग्री को पीडीएफ में परिवर्तित करने में सक्षम होंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आप निम्नलिखित शर्तें पूरी करते हैं:

- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- आपके सिस्टम पर .NET के लिए Aspose.PDF लाइब्रेरी स्थापित है।
- विजुअल स्टूडियो जैसा विकास वातावरण।

## चरण 1: सुरक्षित HTML सामग्री प्राप्त करें
इस चरण में, हम उपयुक्त क्रेडेंशियल्स का उपयोग करके एक यूआरएल से सुरक्षित HTML सामग्री लाएंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// यूआरएल के लिए एक अनुरोध बनाएं.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// यदि सर्वर के लिए आवश्यक हो, तो क्रेडेंशियल सेट करें।
request.Credentials = CredentialCache.DefaultCredentials;
// प्रतिक्रिया प्राप्त करें.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// सर्वर द्वारा लौटाई गई सामग्री वाली स्ट्रीम प्राप्त करें।
Stream dataStream = response. GetResponseStream();
// आसान पहुंच के लिए स्ट्रीमरीडर का उपयोग करके स्ट्रीम खोलें।
StreamReader reader = new StreamReader(dataStream);
// सामग्री पढ़ें.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 प्रतिस्थापित करना सुनिश्चित करें`"YOUR DOCUMENTS DIRECTORY"` वास्तविक निर्देशिका के साथ जहां आप परिणामी पीडीएफ फाइल को सहेजना चाहते हैं।

## चरण 2: क्रेडेंशियल प्रदान करके HTML को पीडीएफ में बदलें
अब हम पुनर्प्राप्त HTML सामग्री को लोड करेंगे और उचित क्रेडेंशियल प्रदान करते हुए इसे पीडीएफ प्रारूप में परिवर्तित करेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// HTML फ़ाइल लोड करें
Document pdfDocument = new Document(stream, options);
```

## चरण 3: परिणामी पीडीएफ फाइल को सहेजना
अंत में, हम परिणामी पीडीएफ फाइल को सहेज लेंगे। निम्नलिखित कोड का प्रयोग करें:

```csharp
// परिणामी पीडीएफ फाइल को सेव करें
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 उपरोक्त कोड परिणामी पीडीएफ फाइल को फ़ाइल नाम के साथ सहेजता है`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### .NET के लिए Aspose.PDF का उपयोग करके HTML से PDF के दौरान क्रेडेंशियल प्रदान करने के लिए उदाहरण स्रोत कोड

```csharp
try
{
	
	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// यूआरएल के लिए एक अनुरोध बनाएं.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// यदि सर्वर द्वारा आवश्यक हो, तो क्रेडेंशियल सेट करें।
	request.Credentials = CredentialCache.DefaultCredentials;
	// प्रतिक्रिया प्राप्त करें.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// सर्वर द्वारा लौटाई गई सामग्री युक्त स्ट्रीम प्राप्त करें।
	Stream dataStream = response.GetResponseStream();
	// आसान पहुंच के लिए स्ट्रीमरीडर का उपयोग करके स्ट्रीम खोलें।
	StreamReader reader = new StreamReader(dataStream);
	// सामग्री पढ़ें.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// HTML फ़ाइल लोड करें
	Document pdfDocument = new Document(stream, options);
	// परिणामी फ़ाइल सहेजें
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.PDF का उपयोग करके एक सुरक्षित यूआरएल तक पहुंचने पर क्रेडेंशियल प्रदान करते हुए एक HTML फ़ाइल को पीडीएफ में परिवर्तित करने की चरण-दर-चरण प्रक्रिया को कवर किया। ऊपर उल्लिखित निर्देशों का पालन करके, आप सही क्रेडेंशियल प्रदान करते हुए HTML सामग्री को पीडीएफ में सफलतापूर्वक परिवर्तित करने में सक्षम होंगे।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.PDF क्या है?

उत्तर: .NET के लिए Aspose.PDF एक मजबूत लाइब्रेरी है जो डेवलपर्स को C# अनुप्रयोगों में PDF दस्तावेज़ों के साथ काम करने का अधिकार देती है। यह HTML से पीडीएफ रूपांतरण सहित कार्यात्मकताओं की एक विस्तृत श्रृंखला प्रदान करता है।

#### प्रश्न: मैं किसी URL से सुरक्षित HTML सामग्री कैसे प्राप्त कर सकता हूं?

 उ: किसी URL से सुरक्षित HTML सामग्री लाने के लिए, आप इसका उपयोग कर सकते हैं`WebRequest` सी# में कक्षा। का उपयोग करके उचित क्रेडेंशियल सेट करना सुनिश्चित करें`Credentials` संपत्ति।

#### प्रश्न: इस ट्यूटोरियल के लिए आवश्यक शर्तें क्या हैं?

उ: ट्यूटोरियल के साथ आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- आपके सिस्टम पर .NET के लिए Aspose.PDF लाइब्रेरी स्थापित है।
- विजुअल स्टूडियो जैसा विकास वातावरण।

#### प्रश्न: HTML को PDF में परिवर्तित करते समय .NET के लिए Aspose.PDF बाहरी संसाधनों को कैसे संभालता है?

 उत्तर: .NET के लिए Aspose.PDF प्रदान करता है`HtmlLoadOptions`HTML से पीडीएफ रूपांतरण के दौरान बाहरी संसाधनों को संभालने के लिए क्लास। आप इसका उपयोग करके बाहरी संसाधन क्रेडेंशियल सेट कर सकते हैं`ExternalResourcesCredentials` संपत्ति।

#### प्रश्न: क्या मैं परिणामी पीडीएफ फ़ाइल के लिए फ़ाइल नाम को अनुकूलित कर सकता हूँ?

 उ: हाँ, आप पीडीएफ दस्तावेज़ को सहेजने वाले कोड को संशोधित करके परिणामी पीडीएफ फ़ाइल के लिए फ़ाइल नाम को अनुकूलित कर सकते हैं। बस वांछित फ़ाइल नाम बदलें`pdfDocument.Save()` तरीका।