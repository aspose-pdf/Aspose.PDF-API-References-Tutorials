---
title: पीडीएफ दस्तावेज़ में तालिका बदलें
linktitle: पीडीएफ दस्तावेज़ में तालिका बदलें
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में तालिका को बदलने का तरीका जानें।
type: docs
weight: 180
url: /hi/net/programming-with-tables/replace-table/
---
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.PDF का उपयोग करके पीडीएफ दस्तावेज़ में एक तालिका को बदलने के लिए चरण दर चरण मार्गदर्शन करेंगे। हम दिए गए C# स्रोत कोड को समझाएंगे और आपको दिखाएंगे कि इसे कैसे लागू किया जाए।

## चरण 1: मौजूदा पीडीएफ दस्तावेज़ लोड करना
सबसे पहले, आपको निम्नलिखित कोड का उपयोग करके मौजूदा पीडीएफ दस्तावेज़ को लोड करना होगा:

```csharp
// दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// मौजूदा पीडीएफ दस्तावेज़ लोड करें
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## चरण 2: तालिकाओं को खोजने के लिए TableAbsorber ऑब्जेक्ट बनाना
इसके बाद, हम पीडीएफ दस्तावेज़ में तालिकाओं को खोजने के लिए एक TableAbsorber ऑब्जेक्ट बनाएंगे:

```csharp
// तालिकाओं को खोजने के लिए एक TableAbsorber ऑब्जेक्ट बनाएं
TableAbsorber absorber = new TableAbsorber();
```

## चरण 3: अवशोषक के साथ पहले पृष्ठ पर जाएँ
अब हम अवशोषक का उपयोग करके पीडीएफ दस्तावेज़ के पहले पृष्ठ पर जाएंगे:

```csharp
// अवशोषक के साथ पहले पृष्ठ पर जाएँ
absorb.Visit(pdfDocument.Pages[1]);
```

## चरण 4: पृष्ठ पर पहली तालिका प्राप्त करना
तालिका को बदलने में सक्षम होने के लिए, हम पृष्ठ की पहली तालिका प्राप्त करेंगे:

```csharp
// पृष्ठ पर पहली तालिका प्राप्त करें
AbsorbedTable table = absorb.TableList[0];
```

## चरण 5: एक नई तालिका बनाना
अब हम वांछित कॉलम और सेल के साथ एक नई तालिका बनाएंगे:

```csharp
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row. Cells. Add("Col 1");
row. Cells. Add("Col 2");
row. Cells. Add("Col 3");
```

## चरण 6: मौजूदा तालिका को नई तालिका से बदलना
अब हम दस्तावेज़ के पहले पृष्ठ पर मौजूदा तालिका को नई तालिका से बदल देंगे:

```csharp
// तालिका को नई तालिका से बदलें
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## चरण 7: दस्तावेज़ सहेजना
अंत में, हम संशोधित पीडीएफ दस्तावेज़ को सहेजते हैं:

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### .NET के लिए Aspose.PDF का उपयोग करके तालिका बदलें का उदाहरण स्रोत कोड

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// मौजूदा पीडीएफ दस्तावेज़ लोड करें
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

// तालिकाएँ ढूँढ़ने के लिए TableAbsorber ऑब्जेक्ट बनाएँ
TableAbsorber absorber = new TableAbsorber();

// अवशोषक के साथ प्रथम पृष्ठ पर जाएँ
absorber.Visit(pdfDocument.Pages[1]);

// पृष्ठ पर पहली तालिका प्राप्त करें
AbsorbedTable table = absorber.TableList[0];

// नई तालिका बनाएं
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

// टेबल को नये से बदलें
absorber.Replace(pdfDocument.Pages[1], table, newTable);

// दस्तावेज़ सहेजें
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## निष्कर्ष
बधाई हो! अब आपने सीख लिया है कि .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ में तालिका को कैसे बदला जाए। इस चरण-दर-चरण मार्गदर्शिका ने आपको दिखाया कि दस्तावेज़ को कैसे लोड करें, मौजूदा तालिका ढूंढें, एक नई तालिका बनाएं और उसे कैसे बदलें। अब आप इस ज्ञान को अपनी परियोजनाओं पर लागू कर सकते हैं।

### पीडीएफ दस्तावेज़ में तालिका बदलने के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: क्या मैं इस दृष्टिकोण का उपयोग करके एक ही पीडीएफ दस्तावेज़ में एकाधिक तालिकाओं को बदल सकता हूँ?

 उ: हाँ, आप जिस तालिका को बदलना चाहते हैं उसके लिए समान प्रक्रिया का पालन करके एक ही पीडीएफ दस्तावेज़ में कई तालिकाओं को बदल सकते हैं। प्राप्त करने के बाद`AbsorbedTable` प्रत्येक तालिका के लिए ऑब्जेक्ट का उपयोग करें`TableAbsorber` , आप संबंधित नई तालिकाएँ बना सकते हैं और फिर इसका उपयोग कर सकते हैं`absorber.Replace()` प्रत्येक मौजूदा तालिका को संबंधित नई तालिका से बदलने की विधि।

#### प्रश्न: यदि नई तालिका में मूल तालिका की तुलना में स्तंभों की संख्या भिन्न हो तो क्या होगा?

उ: यदि नई तालिका में मूल तालिका की तुलना में स्तंभों की संख्या भिन्न है, तो इसके परिणामस्वरूप संशोधित पीडीएफ दस्तावेज़ में अप्रत्याशित व्यवहार या लेआउट समस्याएं हो सकती हैं। यह सुनिश्चित करना आवश्यक है कि नई तालिका की संरचना (स्तंभों की संख्या और उनकी चौड़ाई) निर्बाध प्रतिस्थापन के लिए मूल तालिका की संरचना से मेल खाती है।

#### प्रश्न: क्या मैं किसी तालिका को पहले पृष्ठ के अलावा किसी विशिष्ट पृष्ठ पर बदल सकता हूँ?

 उ: हाँ, आप पृष्ठ अनुक्रमणिका को बदलकर पहले पृष्ठ के अलावा किसी विशिष्ट पृष्ठ पर तालिका को प्रतिस्थापित कर सकते हैं`pdfDocument.Pages[]` प्राप्त करते समय विधि कॉल करें`AbsorbedTable` वस्तु। उदाहरण के लिए, दूसरे पृष्ठ पर किसी तालिका को बदलने के लिए, आप इसका उपयोग करेंगे`pdfDocument.Pages[2]`.

#### प्रश्न: क्या मैं नई तालिका के स्वरूप को अनुकूलित कर सकता हूँ, जैसे पृष्ठभूमि रंग या बॉर्डर जोड़ना?

 उ: हां, आप विभिन्न गुणों को सेट करके नई तालिका के स्वरूप को अनुकूलित कर सकते हैं`Table` और इसकी कोशिकाएँ। उदाहरण के लिए, आप सेट कर सकते हैं`BackgroundColor` पृष्ठभूमि रंग जोड़ने के लिए कोशिकाओं की संपत्ति। आप भी सेट कर सकते हैं`DefaultCellBorder` बॉर्डर जोड़ने के लिए नई तालिका या व्यक्तिगत कक्षों की संपत्ति।

#### प्रश्न: क्या किसी तालिका को बदलने से शेष पीडीएफ दस्तावेज़ की सामग्री लेआउट प्रभावित होती है?

उ: यदि नई तालिका का आकार या संरचना मूल तालिका से काफी भिन्न है, तो तालिका को बदलने से सामग्री लेआउट प्रभावित हो सकता है। नई तालिका को समायोजित करने के लिए पृष्ठ की शेष सामग्री पुनः प्रवाहित होगी। किसी भी लेआउट समस्या से बचने के लिए मौजूदा लेआउट के भीतर मूल रूप से फिट होने के लिए नई तालिका को सावधानीपूर्वक डिजाइन करना आवश्यक है।