---
title: पीडीएफ फाइल में व्यक्तिगत अनुलग्नक प्राप्त करें
linktitle: पीडीएफ फाइल में व्यक्तिगत अनुलग्नक प्राप्त करें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: जानें कि .NET के लिए Aspose.PDF के साथ PDF फ़ाइल में व्यक्तिगत अनुलग्नक कैसे प्राप्त करें।
type: docs
weight: 60
url: /hi/net/programming-with-attachments/get-individual-attachment/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ फ़ाइल का व्यक्तिगत अनुलग्नक प्राप्त करने के लिए चरण दर चरण निम्नलिखित C# स्रोत कोड के बारे में बताएंगे।

सुनिश्चित करें कि आपने Aspose.PDF लाइब्रेरी स्थापित कर ली है और शुरू करने से पहले अपना विकास वातावरण स्थापित कर लिया है। C# प्रोग्रामिंग का बुनियादी ज्ञान भी हो।

### चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए स्रोत कोड में, आपको उस निर्देशिका को निर्दिष्ट करना होगा जहां पीडीएफ फ़ाइल स्थित है जिससे आप व्यक्तिगत अनुलग्नक प्राप्त करना चाहते हैं। "डेटाडिर" वेरिएबल को वांछित निर्देशिका में बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### चरण 2: मौजूदा पीडीएफ दस्तावेज़ खोलें

हम निर्दिष्ट पथ का उपयोग करके मौजूदा पीडीएफ दस्तावेज़ खोलते हैं।

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
```

### चरण 3: एक विशिष्ट अनुलग्नक प्राप्त करना

हम दस्तावेज़ के अनुलग्नक संग्रह से एक विशिष्ट अनुलग्नक पुनर्प्राप्त करते हैं। इस उदाहरण में, हमें इंडेक्स 1 का उपयोग करके पहला अटैचमेंट मिलता है।

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### चरण 4: फ़ाइल गुण प्राप्त करें

हम नाम, विवरण, एमआईएमई प्रकार, नियंत्रण हैश, निर्माण तिथि, संशोधित तिथि और आकार जैसे अनुलग्नक गुण प्रदर्शित करते हैं।

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// जांचें कि क्या ऑब्जेक्ट पैरामीटर में अतिरिक्त जानकारी है
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### चरण 5: अनुलग्नक पुनर्प्राप्त करें और फ़ाइल में सहेजें

हम अनुलग्नक की सामग्री को पुनः प्राप्त करते हैं और इसे एक टेक्स्ट फ़ाइल में सहेजते हैं। इस उदाहरण में, फ़ाइल "test_out.txt" नाम से सहेजी गई है।

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### .NET के लिए Aspose.PDF का उपयोग करके व्यक्तिगत अनुलग्नक प्राप्त करने के लिए नमूना स्रोत कोड 

```csharp

// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// दस्तावेज़ खोलें
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
// विशेष एम्बेडेड फ़ाइल प्राप्त करें
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// फ़ाइल गुण प्राप्त करें
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
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
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## निष्कर्ष

इस ट्यूटोरियल में, हमने समझाया कि .NET के लिए Aspose.PDF का उपयोग करके एक पीडीएफ फ़ाइल से व्यक्तिगत अनुलग्नक कैसे प्राप्त करें। अब आप इस ज्ञान का उपयोग अपनी पीडीएफ फाइलों से अनुलग्नकों को निकालने और सहेजने के लिए कर सकते हैं।

### पीडीएफ फ़ाइल में व्यक्तिगत अनुलग्नक प्राप्त करने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: पीडीएफ दस्तावेज़ से व्यक्तिगत अनुलग्नक प्राप्त करने का उद्देश्य क्या है?

उ: एक व्यक्तिगत अनुलग्नक प्राप्त करने से आप पीडीएफ के भीतर एक विशिष्ट एम्बेडेड फ़ाइल को निकालने और सहेजने की अनुमति देते हैं, जो आगे के विश्लेषण या हेरफेर के लिए उपयोगी हो सकता है।

#### प्रश्न: मैं अपने पीडीएफ-संबंधित कार्यों में इस ट्यूटोरियल से कैसे लाभ उठा सकता हूं?

उ: यह ट्यूटोरियल .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ से एक विशेष अनुलग्नक को पुनर्प्राप्त करने और सहेजने के लिए चरण-दर-चरण निर्देश और सी # स्रोत कोड प्रदान करता है।

#### प्रश्न: इस ट्यूटोरियल का उपयोग करके मैं किन अनुलग्नक गुणों तक पहुंच सकता हूं?

ए: आप नाम, विवरण, एमआईएमई प्रकार, नियंत्रण हैश, निर्माण तिथि, संशोधन तिथि और विशिष्ट अनुलग्नक के आकार जैसे अनुलग्नक गुणों तक पहुंच सकते हैं।

#### प्रश्न: क्या मैं पहले अनुलग्नक के अलावा अन्य अनुलग्नक प्राप्त करने के लिए कोड को संशोधित कर सकता हूँ?

 ए: बिल्कुल, आप सूचकांक को समायोजित कर सकते हैं (उदाहरण के लिए,`pdfDocument.EmbeddedFiles[1]`) पीडीएफ के भीतर विभिन्न सूचकांकों पर अनुलग्नकों को पुनः प्राप्त करने के लिए।

#### प्रश्न: मैं पुनर्प्राप्त अनुलग्नक को किसी फ़ाइल में कैसे सहेजूँ?

उ: यह ट्यूटोरियल अनुलग्नक की सामग्री को पुनः प्राप्त करने और इसे एक निर्दिष्ट नाम के साथ एक टेक्स्ट फ़ाइल में सहेजने के लिए कोड प्रदान करता है।

#### प्रश्न: अनुलग्नक जानकारी में "चेक हैश" संपत्ति का क्या महत्व है?

उ: "चेक हैश" संपत्ति अनुलग्नक के नियंत्रण हैश मान का प्रतिनिधित्व करती है, जिसका उपयोग अनुलग्नक की अखंडता को सत्यापित करने के लिए किया जा सकता है।

#### प्रश्न: क्या मैं फ़ाइल प्रकार जैसे विशिष्ट मानदंडों के साथ अनुलग्नक निकालने के लिए इस ज्ञान का विस्तार कर सकता हूं?

उ: हाँ, आप फ़ाइल प्रकार या अन्य गुणों जैसे विशिष्ट मानदंडों के आधार पर अनुलग्नकों को फ़िल्टर करने के लिए कोड को बढ़ा सकते हैं।

#### प्रश्न: .NET के लिए Aspose.PDF व्यक्तिगत अनुलग्नकों को निकालने की प्रक्रिया को कैसे सरल बनाता है?

उ: .NET के लिए Aspose.PDF एक उपयोगकर्ता-अनुकूल एपीआई प्रदान करता है जो पीडीएफ दस्तावेजों के भीतर अनुलग्नकों के निष्कर्षण और हेरफेर की सुविधा प्रदान करता है।

#### प्रश्न: क्या यह ट्यूटोरियल पासवर्ड से सुरक्षित पीडीएफ फाइलों के लिए भी प्रासंगिक है?

उ: हां, आप .NET के लिए Aspose.PDF का उपयोग करके पासवर्ड-सुरक्षित पीडीएफ फाइलों से अलग-अलग अनुलग्नकों को पुनः प्राप्त करने के लिए समान तकनीकों को अपना सकते हैं।
