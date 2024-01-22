---
title: पीडीएफ फाइल में एसवीजी ऑब्जेक्ट जोड़ें
linktitle: पीडीएफ फाइल में एसवीजी ऑब्जेक्ट जोड़ें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके आसानी से PDF फ़ाइल में SVG ऑब्जेक्ट जोड़ें।
type: docs
weight: 30
url: /hi/net/programming-with-tables/add-svg-object/
---
इस ट्यूटोरियल में, हम सीखेंगे कि .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करके पीडीएफ फाइल में एक एसवीजी ऑब्जेक्ट कैसे जोड़ें। एसवीजी (स्केलेबल वेक्टर ग्राफिक्स) वेक्टर ग्राफिक्स के लिए एक लोकप्रिय प्रारूप है जिसे गुणवत्ता खोए बिना आसानी से स्केल किया जा सकता है। Aspose.PDF के साथ, आप प्रोग्रामेटिक रूप से अपने PDF दस्तावेज़ों में SVG ऑब्जेक्ट जोड़ सकते हैं।

## आवश्यकताएं

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- विजुअल स्टूडियो स्थापित
- .NET लाइब्रेरी के लिए Aspose.PDF स्थापित

## चरण 1: पर्यावरण स्थापित करें

सबसे पहले, आइए विज़ुअल स्टूडियो में एक नया C# प्रोजेक्ट बनाकर पर्यावरण स्थापित करें। विज़ुअल स्टूडियो खोलें और इन चरणों का पालन करें:

1. नया प्रोजेक्ट बनाने के लिए "फ़ाइल" > "नया" > "प्रोजेक्ट" पर क्लिक करें।
2. अपने सेटअप के आधार पर, "कंसोल ऐप (.NET फ्रेमवर्क)" या "कंसोल ऐप (.NET कोर)" टेम्पलेट चुनें।
3. अपने प्रोजेक्ट के लिए उपयुक्त नाम और स्थान चुनें, फिर "बनाएं" पर क्लिक करें।

## चरण 2: दस्तावेज़ और छवि ऑब्जेक्ट बनाएँ

इस चरण में, हम अपने पीडीएफ दस्तावेज़ और एसवीजी छवि के लिए आवश्यक ऑब्जेक्ट बनाएंगे। अपने प्रोजेक्ट की C# फ़ाइल खोलें और निम्नलिखित कोड जोड़ें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// त्वरित दस्तावेज़ ऑब्जेक्ट
Document doc = new Document();
// एक छवि उदाहरण बनाएँ
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## चरण 3: छवि गुण सेट करें

इसके बाद, हम अपनी एसवीजी छवि के लिए गुण सेट करेंगे। हम फ़ाइल प्रकार को एसवीजी, एसवीजी फ़ाइल का पथ और छवि के आयाम निर्दिष्ट करेंगे। पिछले चरण के बाद निम्नलिखित कोड जोड़ें:

```csharp
// छवि प्रकार को एसवीजी के रूप में सेट करें
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// स्रोत फ़ाइल के लिए पथ
img.File = dataDir + "SVGToPDF.svg";
// छवि उदाहरण के लिए चौड़ाई निर्धारित करें
img. FixWidth = 50;
// छवि उदाहरण के लिए ऊँचाई निर्धारित करें
img.FixHeight = 50;
```

## चरण 4: तालिका बनाएं और कॉन्फ़िगर करें

अब, एक टेबल ऑब्जेक्ट बनाएं और कॉलम की चौड़ाई सेट करें। हम दो स्तंभों वाली एक तालिका बनाएंगे, प्रत्येक की चौड़ाई 100 इकाई होगी। निम्नलिखित कोड जोड़ें:

```csharp
// इंस्टेंस तालिका बनाएं
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// तालिका कक्षों के लिए चौड़ाई निर्धारित करें
table. ColumnWidths = "100 100";
```

## चरण 5: तालिका में कक्ष जोड़ें

इस चरण में, हम तालिका में एक पंक्ति और कक्ष जोड़ेंगे। प्रत्येक पंक्ति तालिका में एक क्षैतिज पंक्ति का प्रतिनिधित्व करती है, और कोशिकाओं को पंक्तियों में जोड़ा जाता है। निम्नलिखित कोड जोड़ें:

```csharp
//पंक्ति ऑब्जेक्ट बनाएं और इसे तालिका उदाहरण में जोड़ें
Aspose.Pdf.Row row = table.Rows.Add();
// सेल ऑब्जेक्ट बनाएं और इसे पंक्ति उदाहरण में जोड़ें
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## चरण 6: सेल में टेक्स्ट और छवि जोड़ें

इसके बाद, आइए तालिका की कोशिकाओं में टेक्स्ट और एसवीजी छवि जोड़ें। हम पहले सेल में "पहला सेल" टेक्स्ट और दूसरे सेल में एसवीजी छवि जोड़ देंगे। निम्नलिखित कोड जोड़ें:

```csharp
// सेल ऑब्जेक्ट के पैराग्राफ संग्रह में टेक्स्टफ्रैगमेंट जोड़ें
cell.Paragraphs.Add(new TextFragment("First cell"));
// पंक्ति ऑब्जेक्ट में एक और सेल जोड़ें
cell = row. Cells. Add();
// हाल ही में जोड़े गए सेल इंस्टेंस के पैराग्राफ संग्रह में एसवीजी छवि जोड़ें
cell.Paragraphs.Add(img);
```

## चरण 7: दस्तावेज़ में एक पेज बनाएं और जोड़ें

अब, एक पेज ऑब्जेक्ट बनाएं और इसे दस्तावेज़ में जोड़ें। तालिका को पृष्ठ के पैराग्राफ संग्रह में जोड़ा जाएगा। निम्नलिखित कोड जोड़ें:

```csharp
// पेज ऑब्जेक्ट बनाएं और इसे दस्तावेज़ उदाहरण के पेज संग्रह में जोड़ें
Page page = doc.Pages.Add();
// पेज ऑब्जेक्ट के पैराग्राफ संग्रह में तालिका जोड़ें
page.Paragraphs.Add(table);
```

## चरण 8: पीडीएफ फाइल को सेव करें

अंत में, हम पीडीएफ फाइल को निर्दिष्ट स्थान पर सहेजेंगे। निम्नलिखित कोड जोड़ें:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// पीडीएफ फाइल सेव करें
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके SVG ऑब्जेक्ट जोड़ने के लिए उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// त्वरित दस्तावेज़ ऑब्जेक्ट
Document doc = new Document();
// एक छवि उदाहरण बनाएँ
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// छवि प्रकार को एसवीजी के रूप में सेट करें
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// स्रोत फ़ाइल के लिए पथ
img.File = dataDir + "SVGToPDF.svg";
// छवि उदाहरण के लिए चौड़ाई निर्धारित करें
img.FixWidth = 50;
// छवि उदाहरण के लिए ऊँचाई निर्धारित करें
img.FixHeight = 50;
// तालिका उदाहरण बनाएँ
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// तालिका कक्षों के लिए चौड़ाई निर्धारित करें
table.ColumnWidths = "100 100";
//पंक्ति ऑब्जेक्ट बनाएं और इसे तालिका उदाहरण में जोड़ें
Aspose.Pdf.Row row = table.Rows.Add();
// सेल ऑब्जेक्ट बनाएं और इसे पंक्ति उदाहरण में जोड़ें
Aspose.Pdf.Cell cell = row.Cells.Add();
// सेल ऑब्जेक्ट के पैराग्राफ संग्रह में टेक्स्टफ्रैगमेंट जोड़ें
cell.Paragraphs.Add(new TextFragment("First cell"));
// पंक्ति ऑब्जेक्ट में एक और सेल जोड़ें
cell = row.Cells.Add();
// हाल ही में जोड़े गए सेल इंस्टेंस के पैराग्राफ संग्रह में एसवीजी छवि जोड़ें
cell.Paragraphs.Add(img);
// पेज ऑब्जेक्ट बनाएं और इसे दस्तावेज़ उदाहरण के पेज संग्रह में जोड़ें
Page page = doc.Pages.Add();
// पेज ऑब्जेक्ट के पैराग्राफ संग्रह में तालिका जोड़ें
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// पीडीएफ फाइल सेव करें
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि .NET लाइब्रेरी के लिए Aspose.PDF का उपयोग करके एक पीडीएफ फाइल में एक एसवीजी ऑब्जेक्ट कैसे जोड़ा जाए। हमने दस्तावेज़ बनाने, पर्यावरण स्थापित करने, तालिका सेल में एक एसवीजी छवि जोड़ने और पीडीएफ फ़ाइल को सहेजने की चरण-दर-चरण प्रक्रिया को कवर किया। अब आप एसवीजी ऑब्जेक्ट्स को अपने पीडीएफ दस्तावेजों में प्रोग्रामेटिक रूप से शामिल कर सकते हैं।

### पीडीएफ फाइल में एसवीजी ऑब्जेक्ट जोड़ने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं पीडीएफ दस्तावेज़ में एकाधिक एसवीजी ऑब्जेक्ट जोड़ सकता हूँ?

 उ: हां, आप पीडीएफ दस्तावेज़ में एकाधिक एसवीजी ऑब्जेक्ट जोड़ सकते हैं। बस अतिरिक्त बनाएं और कॉन्फ़िगर करें`Aspose.Pdf.Image` प्रत्येक एसवीजी छवि के उदाहरण जिन्हें आप जोड़ना चाहते हैं और फिर उन्हें पीडीएफ दस्तावेज़ में वांछित तालिका कोशिकाओं या पैराग्राफ में जोड़ें।

#### प्रश्न: मैं तालिका सेल में एसवीजी छवि के आकार और स्थिति को कैसे समायोजित कर सकता हूं?

 ए: तालिका सेल में एसवीजी छवि के आकार और स्थिति को समायोजित करने के लिए, आप संशोधित कर सकते हैं`FixWidth` और`FixHeight` के गुण`Aspose.Pdf.Image`उदाहरण। आप अन्य संपत्तियों का भी उपयोग कर सकते हैं जैसे`HorizontalAlignment` और`VerticalAlignment` स्थिति को नियंत्रित करने के लिए टेबल सेल की।

#### प्रश्न: क्या उसी तालिका सेल में एसवीजी छवि के साथ टेक्स्ट जोड़ना संभव है?

 उ: हां, उसी तालिका सेल में एसवीजी छवि के साथ टेक्स्ट जोड़ना संभव है। आप इसका उपयोग कर सकते हैं`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` एसवीजी छवि के साथ सेल में टेक्स्ट जोड़ने की विधि।

#### प्रश्न: क्या मैं एसवीजी छवि में हाइपरलिंक जोड़ सकता हूं?

 उ: हां, आप इसका उपयोग करके एसवीजी छवि में हाइपरलिंक जोड़ सकते हैं`Hyperlink` की संपत्ति`Aspose.Pdf.Image` उदाहरण। छवि को क्लिक करने योग्य बनाने के लिए हाइपरलिंक यूआरएल या क्रिया सेट करें।

#### प्रश्न: क्या .NET के लिए Aspose.PDF .NET Core 3.1 या बाद के संस्करणों के साथ संगत है?

उत्तर: हाँ, .NET के लिए Aspose.PDF .NET Core 3.1 और बाद के संस्करणों के साथ संगत है। आप इसे .NET फ्रेमवर्क और .NET कोर एप्लिकेशन दोनों में उपयोग कर सकते हैं।