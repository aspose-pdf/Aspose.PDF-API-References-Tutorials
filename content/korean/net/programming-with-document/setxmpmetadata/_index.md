---
title: PDF 파일에 XMPMetadata 설정
linktitle: PDF 파일에 XMPMetadata 설정
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 XMPMetadata를 설정하는 방법을 알아보세요. 이 단계별 가이드를 따르세요.
type: docs
weight: 330
url: /ko/net/programming-with-document/setxmpmetadata/
---
이 글에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 XMP 메타데이터를 설정하는 방법에 대한 단계별 가이드를 제공합니다. 글의 마지막에 전체 예제 소스 코드를 제공합니다.

## 1단계: 문서 디렉토리 경로 설정

시작하기 전에 PDF 문서가 있는 디렉토리 경로를 설정해야 합니다. 이 경로를 "dataDir"이라는 변수에 저장합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 교체를 꼭 해주세요`YOUR DOCUMENT DIRECTORY` PDF 파일의 실제 경로를 포함합니다.

## 2단계: PDF 파일 열기

 첫 번째 단계는 XMP 메타데이터를 설정하려는 PDF 파일을 여는 것입니다. 이를 위해 새`Document` 객체를 만들고 PDF 파일의 경로를 전달합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## 3단계: XMP 메타데이터 속성 설정

이제 PDF 파일을 열었으므로 XMP 메타데이터 속성을 설정할 수 있습니다. 설정하는 속성은 특정 요구 사항에 따라 달라지지만, 설정할 수 있는 몇 가지 일반적인 속성은 다음과 같습니다.

- `xmp:CreateDate`: PDF 파일의 생성 날짜.
- `xmp:Nickname`: PDF 파일의 별명 또는 별칭입니다.
- `xmp:CustomProperty`: 사용자가 지정한 값을 갖는 사용자 정의 속성입니다.

 이러한 속성을 설정하려면 다음을 사용할 수 있습니다.`Metadata` 의 속성`Document` 객체. 다음은 예입니다.

```csharp
// 속성 설정
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

이 튜토리얼에서는 생성 날짜를 현재 날짜와 시간으로, 별명을 "별명"으로, 사용자 지정 속성을 "사용자 지정 값"으로 설정합니다. 이러한 값을 사용자 지정 값으로 바꿀 수 있습니다.

## 4단계: PDF 파일 저장

 XMP 메타데이터 속성을 설정한 후에는 PDF 파일을 저장해야 합니다. 이를 위해 다음을 사용할 수 있습니다.`Save` 의 방법`Document` 객체를 만들고 업데이트된 PDF 파일을 저장할 경로를 전달합니다.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
// 문서 저장
pdfDocument.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 XMPMetadata를 설정하기 위한 예제 소스 코드

다음은 .NET용 Aspose.PDF를 사용하여 XMPMetadata를 설정하는 전체 예제 소스 코드입니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

// 속성 설정
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

dataDir = dataDir + "SetXMPMetadata_out.pdf";
// 문서 저장
pdfDocument.Save(dataDir);

Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);
```

## 결론

Aspose.PDF for .NET은 PDF 파일에 XMP 메타데이터를 설정하는 간단한 방법을 제공하여 문서에 설명 정보와 속성을 추가할 수 있습니다. 위에 제공된 단계별 가이드는 C# 소스 코드를 사용하여 다양한 XMP 메타데이터 속성을 설정하는 방법을 보여줍니다. 또한 XMP 메타데이터를 사용자 지정하여 특정 요구 사항과 비즈니스 요구 사항에 맞출 수 있습니다. Aspose.PDF for .NET을 사용하면 PDF 메타데이터를 효율적으로 관리하고 PDF 문서를 더 잘 구성하고 검색할 수 있습니다.

### PDF 파일의 XMPMetadata 설정에 대한 FAQ

#### 질문: PDF 파일의 XMP 메타데이터는 무엇이며, 왜 중요한가요?

A: XMP(Extensible Metadata Platform)는 PDF를 포함한 다양한 파일 형식에 메타데이터를 내장하기 위한 표준입니다. PDF 파일의 XMP 메타데이터를 사용하면 생성 날짜, 작성자, 제목, 키워드 및 사용자 지정 속성과 같은 설명적 정보와 속성을 문서에 추가할 수 있습니다. PDF 문서의 더 나은 구성, 검색 가능성 및 보관에 필수적입니다.

#### 질문: 예시에 언급된 것 외에도 다른 XMP 메타데이터 속성을 설정할 수 있나요?

 A: 네, 귀하의 특정 요구 사항에 따라 광범위한 XMP 메타데이터 속성을 설정할 수 있습니다. 몇 가지 일반적인 속성은 다음과 같습니다.`dc:title` (문서 제목),`dc:creator` (문서 작성자),`dc:description` (문서 설명),`pdf:Keywords` (문서 키워드) 등이 있습니다. XMP 사양은 다양한 유형의 메타데이터를 설정하기 위한 다양한 표준 네임스페이스와 사용자 정의 네임스페이스를 제공합니다.

#### 질문: 기존 PDF 파일에서 XMP 메타데이터를 검색하여 읽을 수 있나요?

 A: 네, Aspose.PDF for .NET은 기존 PDF 파일에서 XMP 메타데이터를 읽고 검색할 수 있는 기능을 제공합니다.`Metadata` 의 속성`Document` XMP 메타데이터에 접근하고 특정 속성의 값을 검색하는 클래스입니다.