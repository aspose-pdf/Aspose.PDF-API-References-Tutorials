---
title: सभी अनुलग्नक पीडीएफ फाइल में प्राप्त करें
linktitle: सभी अनुलग्नक पीडीएफ फाइल में प्राप्त करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: जानें कि .NET के लिए Aspose.PDF के साथ सभी अनुलग्नकों को PDF फ़ाइल में कैसे प्राप्त करें। आसान संचालन के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 40
url: /hi/net/programming-with-attachments/get-all-the-attachments/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फ़ाइल में सभी अनुलग्नक प्राप्त करने के लिए चरण दर चरण निम्नलिखित C# स्रोत कोड के बारे में बताएंगे।

सुनिश्चित करें कि आपने Aspose.PDF लाइब्रेरी स्थापित कर ली है और शुरू करने से पहले अपना विकास वातावरण स्थापित कर लिया है। C# प्रोग्रामिंग का बुनियादी ज्ञान भी हो।

### चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए स्रोत कोड में, आपको उस निर्देशिका को निर्दिष्ट करना होगा जहां पीडीएफ फ़ाइल स्थित है जिससे आप अनुलग्नक प्राप्त करना चाहते हैं। "डेटाडिर" वेरिएबल को वांछित निर्देशिका में बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### चरण 2: मौजूदा पीडीएफ दस्तावेज़ खोलें

हम निर्दिष्ट पथ का उपयोग करके मौजूदा पीडीएफ दस्तावेज़ खोलते हैं।

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### चरण 3: अनुलग्नक संग्रह प्राप्त करना

हमें दस्तावेज़ से अनुलग्नकों का संग्रह मिलता है।

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### चरण 4: अनुलग्नक पुनर्प्राप्त करना

हम सभी अनुलग्नकों को प्राप्त करने और उनकी जानकारी प्रदर्शित करने के लिए संग्रह का अध्ययन करते हैं। हम अनुलग्नकों को अलग-अलग फ़ाइलों में भी सहेजते हैं।

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// जांचें कि क्या ऑब्जेक्ट पैरामीटर में अतिरिक्त जानकारी है
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// अनुलग्नक पुनः प्राप्त करें और एक फ़ाइल में सहेजें
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### .NET के लिए Aspose.PDF का उपयोग करके सभी अनुलग्नक प्राप्त करने के लिए नमूना स्रोत कोड 

```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// एम्बेडेड फ़ाइलें संग्रह प्राप्त करें
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// एम्बेडेड फ़ाइलों की गिनती प्राप्त करें
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// सभी अनुलग्नक प्राप्त करने के लिए संग्रह के माध्यम से लूप करें
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
	Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
	//जांचें कि क्या पैरामीटर ऑब्जेक्ट में पैरामीटर हैं
	if (fileSpecification.Params != null)
	{
		Console.WriteLine("CheckSum: {0}",
		fileSpecification.Params.CheckSum);
		Console.WriteLine("Creation Date: {0}",
		fileSpecification.Params.CreationDate);
		Console.WriteLine("Modification Date: {0}",
		fileSpecification.Params.ModDate);
		Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
	}
	// अनुलग्नक प्राप्त करें और फ़ाइल या स्ट्रीम में लिखें
	byte[] fileContent = new byte[fileSpecification.Contents.Length];
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## निष्कर्ष

इस ट्यूटोरियल में, हमने बताया कि .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ फाइल से सभी अटैचमेंट कैसे प्राप्त करें। अब आप इस ज्ञान का उपयोग अपनी पीडीएफ फाइलों से अनुलग्नकों को निकालने और उनमें हेरफेर करने के लिए कर सकते हैं।

## सभी अनुलग्नकों को पीडीएफ फाइल में प्राप्त करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मुझे पीडीएफ दस्तावेज़ से सभी अनुलग्नकों को पुनः प्राप्त करने की आवश्यकता क्यों होगी?

उ: अनुलग्नकों को पुनः प्राप्त करने से आप पीडीएफ के भीतर एम्बेडेड अतिरिक्त फ़ाइलों तक पहुंच और हेरफेर कर सकते हैं, जो संग्रह करने, साझा करने या आगे की प्रक्रिया के लिए उपयोगी हो सकते हैं।

#### प्रश्न: पीडीएफ दस्तावेज़ में किस प्रकार की फ़ाइलें संलग्न की जा सकती हैं?

उ: पीडीएफ दस्तावेज़ों में संलग्न फ़ाइलों की एक विस्तृत श्रृंखला हो सकती है, जिनमें चित्र, दस्तावेज़, स्प्रेडशीट, ऑडियो फ़ाइलें और बहुत कुछ शामिल हैं।

#### प्रश्न: यह ट्यूटोरियल मुझे .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ से अटैचमेंट पुनर्प्राप्त करने में कैसे मदद करता है?

उ: यह ट्यूटोरियल पीडीएफ दस्तावेज़ के भीतर सभी अनुलग्नकों तक पहुंचने और पुनर्प्राप्त करने के लिए चरण-दर-चरण निर्देश और सी # स्रोत कोड प्रदान करता है।

#### प्रश्न: क्या मैं इस ट्यूटोरियल का उपयोग करके सभी अनुलग्नकों के बजाय विशिष्ट अनुलग्नकों को पुनः प्राप्त कर सकता हूँ?

उ: हाँ, आप अपनी आवश्यकताओं के आधार पर चुनिंदा अनुलग्नकों को पुनः प्राप्त करने के लिए दिए गए कोड को संशोधित कर सकते हैं।

#### प्रश्न: इस ट्यूटोरियल का उपयोग करके मैं प्रत्येक अनुलग्नक के बारे में क्या जानकारी प्राप्त कर सकता हूं?

उ: यह ट्यूटोरियल दर्शाता है कि अनुलग्नक का नाम, विवरण, एमआईएमई प्रकार, निर्माण तिथि, संशोधन तिथि और आकार जैसे विवरण कैसे प्राप्त करें और प्रदर्शित करें।

#### प्रश्न: इस ट्यूटोरियल का उपयोग करके पुनर्प्राप्त अनुलग्नकों को कैसे सहेजा जाता है?

उ: ट्यूटोरियल प्रत्येक पुनर्प्राप्त अनुलग्नक को निर्दिष्ट निर्देशिका में एक अलग फ़ाइल के रूप में सहेजने में आपका मार्गदर्शन करता है।

#### प्रश्न: क्या मैं इस ज्ञान का उपयोग पासवर्ड से सुरक्षित पीडीएफ फाइलों से अटैचमेंट निकालने के लिए कर सकता हूं?

उ: हां, आप .NET के लिए Aspose.PDF का उपयोग करके पासवर्ड-सुरक्षित पीडीएफ फाइलों से अनुलग्नक पुनर्प्राप्त करने के लिए समान सिद्धांत लागू कर सकते हैं।

#### प्रश्न: .NET के लिए Aspose.PDF अटैचमेंट पुनर्प्राप्ति की सुविधा कैसे प्रदान करता है?

उ: .NET के लिए Aspose.PDF एक सहज एपीआई प्रदान करता है जो आपको पीडीएफ दस्तावेज़ों में अनुलग्नकों तक आसानी से पहुंचने और हेरफेर करने की अनुमति देता है।

#### प्रश्न: क्या ऐसे विशिष्ट परिदृश्य हैं जहां अनुलग्नकों को पुनः प्राप्त करने की अनुशंसा की जाती है?

उ: अनुलग्नकों को पुनर्प्राप्त करना तब उपयोगी होता है जब आपको पीडीएफ में एम्बेडेड फ़ाइलों तक पहुंचने की आवश्यकता होती है, जैसे कि छवियां, ऑडियो फ़ाइलें, या अतिरिक्त दस्तावेज़ निकालना।