---
title: PDF 파일에 XMPMetadata 설정
linktitle: PDF 파일에 XMPMetadata 설정
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 XMP 메타데이터를 설정하는 방법을 알아보세요. 이 단계별 가이드는 문서 설정부터 저장까지 전체 프로세스를 안내합니다.
type: docs
weight: 330
url: /ko/net/programming-with-document/setxmpmetadata/
---
## 소개

PDF 파일에 메타데이터를 추가하고 싶으신가요? 생성 날짜, 별명 또는 사용자 지정 속성과 같은 정보를 포함하고 싶을 수도 있습니다. 올바른 곳에 오셨습니다! 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 XMP 메타데이터를 설정하는 방법을 자세히 알아보겠습니다. 프로세스의 모든 단계를 안내하고 간단하고 매력적인 방식으로 설명해 드리겠습니다. 초보자이든 숙련된 개발자이든 이 가이드를 따라하기 쉬울 것입니다.

## 필수 조건

코드로 들어가기 전에 먼저 준비해야 할 몇 가지 사항이 있습니다.

1.  .NET용 Aspose.PDF 라이브러리: 아직 다운로드하지 않았다면 .NET용 Aspose.PDF의 최신 버전을 여기에서 다운로드하세요.[여기](https://releases.aspose.com/pdf/net/).
2. 개발 환경: 코드를 작성하고 실행하려면 Visual Studio나 다른 .NET 개발 환경이 필요합니다.
3. C#에 대한 기본 지식: 걱정하지 마세요. 간단하게 설명하겠지만, C#에 대한 기본적인 이해가 도움이 될 것입니다.

또한 작업할 PDF 문서가 필요합니다. PDF 문서가 없다면 샘플 PDF를 만들거나 인터넷에서 다운로드할 수 있습니다.

## 패키지 가져오기

코드 작성을 시작하기 전에 프로젝트에 필요한 패키지를 가져와야 합니다.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

이제 튜토리얼의 핵심으로 들어가겠습니다. Aspose.PDF for .NET을 사용하여 PDF 파일에 XMP 메타데이터를 설정하는 것입니다. 쉽게 따라할 수 있도록 여러 단계로 나누어 설명하겠습니다.

## 1단계: 디렉토리 경로 설정

 가장 먼저 해야 할 일은 PDF 파일이 저장된 디렉토리를 지정하는 것입니다. 문서가 다른 곳에 있는 경우 간단히 수정합니다.`dataDir` 변수는 올바른 위치를 가리킵니다.

이 단계는 귀하의 코드에 귀하의 PDF 파일을 찾을 수 있는 홈 주소를 제공하는 것으로 생각하세요. 이것이 없다면, 그것은 어디를 찾아야 할지 알 수 없을 것입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

여기서 프로그램에 파일의 위치를 알려줘야 합니다. 올바른 경로를 제공하지 않으면 프로그램이 PDF를 열 수 없기 때문에 중요합니다.

## 2단계: PDF 문서 열기

 이제 디렉토리를 설정했으므로 다음 단계는 다음을 사용하여 PDF 문서를 로드하는 것입니다.`Document` Aspose.PDF의 클래스입니다.

실제 책을 여는 것을 상상해 보세요. 이 단계는 PDF를 열어 변경을 시작할 수 있는 것과 같은 디지털 버전입니다.

```csharp
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

 이 코드 줄은 PDF 파일을 로드합니다.`pdfDocument` 객체. 파일 이름이 디렉토리의 파일 이름과 일치하는지 확인하세요. 그렇지 않으면 프로그램에서 오류가 발생합니다.

## 3단계: XMP 메타데이터 속성 설정

마법이 일어나는 곳은 바로 여기입니다! 이제 PDF 문서를 로드했으므로 생성 날짜, 별명 또는 원하는 사용자 지정 속성과 같은 메타데이터 속성을 설정할 수 있습니다.

이 단계는 프로필의 "나에 대한 정보" 섹션을 채우는 것으로 생각하세요. PDF 파일에 포함하려는 생성 날짜, 별명 또는 기타 세부 정보를 추가하는 곳입니다.

```csharp
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

간단히 설명드리자면,
- CreateDate: 이 속성은 PDF의 생성 날짜를 저장합니다. 현재 날짜와 시간으로 설정합니다.
- 별명: 개인 별명과 마찬가지로 문서에도 별명을 설정할 수 있습니다.
- CustomProperty: 여기에서는 문서와 관련된 사용자 정의 정보를 추가할 수 있습니다.

## 4단계: 업데이트된 PDF 문서 저장

 XMP 메타데이터를 설정한 후 업데이트된 PDF 문서를 저장할 시간입니다.`dataDir` 새 파일이 다른 이름으로 저장되도록 경로를 설정하세요.

노트북에 중요한 메모를 썼다고 상상해 보세요. 이제 다시 선반에 올려야 하지만 이번에는 추가 세부 정보가 적혀 있습니다. 이 단계는 메타데이터와 함께 새 "노트북"을 저장합니다.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
pdfDocument.Save(dataDir);
```

 이 코드 줄은 업데이트된 PDF를 이름으로 저장합니다.`SetXMPMetadata_out.pdf`원하시면 파일 이름을 변경할 수 있습니다.

## 5단계: 성공 메시지 표시

모든 것이 순조롭게 진행되었는지 확인하기 위해 콘솔에 메시지를 출력합니다. 이 단계는 선택 사항이지만 확인을 받는 것은 항상 좋은 일이죠?

```csharp
Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);
```

이 줄은 메타데이터가 성공적으로 추가되었고 파일이 지정된 위치에 저장되었다는 메시지를 콘솔에 인쇄합니다.

## 결론

이제 다 봤습니다! 몇 가지 간단한 단계만 거치면 Aspose.PDF for .NET을 사용하여 PDF 파일에 XMP 메타데이터를 설정하는 방법을 배웠습니다. 생성 날짜, 사용자 지정 속성 또는 문서에 중요한 다른 메타데이터 등 PDF 파일에 추가 정보를 추가하는 좋은 방법입니다.


## 자주 묻는 질문

### PDF 파일의 XMP 메타데이터란 무엇입니까?  
XMP 메타데이터는 문서의 생성 날짜, 작성자, 사용자 정의 속성 등 다양한 속성을 설명하는 PDF 파일에 내장된 데이터를 말합니다.

### PDF에 여러 개의 사용자 정의 속성을 추가할 수 있나요?  
 예, 원하는 만큼 많은 사용자 정의 속성을 추가할 수 있습니다.`Metadata`새로운 키에 값을 할당하기만 하면 객체가 생성됩니다.

### Aspose.PDF for .NET을 사용하려면 라이선스가 필요합니까?  
 예, Aspose.PDF for .NET에는 라이선스가 필요하지만 다음을 사용하여 시도할 수도 있습니다.[무료 체험](https://releases.aspose.com/).

### 파일 경로가 올바르지 않으면 어떻게 되나요?  
파일 경로가 올바르지 않으면 프로그램은 파일을 찾을 수 없다는 오류를 표시합니다. 파일 이름과 경로가 올바른지 확인하세요.

### 암호화된 PDF의 메타데이터를 수정할 수 있나요?  
PDF가 암호화되어 있는 경우, 메타데이터를 수정하기 전에 먼저 PDF를 해독해야 합니다.