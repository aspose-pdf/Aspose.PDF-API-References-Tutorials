---
title: MHT를 PDF로
linktitle: MHT를 PDF로
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 MHT를 PDF로 변환하는 단계별 안내입니다.
type: docs
weight: 70
url: /ko/net/document-conversion/mht-to-pdf/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 MHT 파일을 PDF로 변환하는 과정을 안내합니다. MHT(MIME HTML)는 이미지 및 관련 콘텐츠를 포함하여 전체 웹 페이지를 저장하는 데 사용되는 형식입니다. 아래 단계에 따라 MHT 파일을 PDF 형식으로 변환할 수 있습니다.

## 전제조건
시작하기 전에 다음 전제 조건을 충족하는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- 시스템에 설치된 .NET용 Aspose.PDF 라이브러리.
- Visual Studio와 같은 개발 환경.

## 1단계: MHT 파일 로드
이 단계에서는 .NET용 Aspose.PDF를 사용하여 MHT 파일을 로드합니다. 아래 코드를 따르십시오.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// 문서를 로드하세요
Document document = new Document(dataDir + "test.mht", options);
```

 꼭 교체하세요`"YOUR DOCUMENTS DIRECTORY"` MHT 파일이 있는 실제 디렉터리를 사용합니다.

## 2단계: MHT를 PDF로 변환
MHT 파일을 로드한 후 PDF로 변환을 진행할 수 있습니다. 다음 코드를 사용하세요.

```csharp
// 출력을 PDF 문서로 저장
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 위의 코드는 MHT 파일을 PDF 형식으로 변환하고 파일 이름으로 저장합니다.`"MHTToPDF_out.pdf"`.

### .NET용 Aspose.PDF를 사용하여 MHT를 PDF로 변환하는 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// 문서 로드
Document document = new Document(dataDir  + "test.mht", options);
// 출력을 PDF 문서로 저장
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 MHT 파일을 PDF로 변환하는 단계별 프로세스를 다루었습니다. 위에 설명된 지침을 따르면 이제 MHT 파일을 PDF 형식으로 변환할 수 있습니다. 이 기능은 전체 웹 페이지를 PDF 문서로 변환해야 할 때 유용할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.PDF는 이미지가 포함된 MHT 파일을 PDF로 변환하는 것을 지원합니까?

A: 예, .NET용 Aspose.PDF는 이미지가 포함된 MHT 파일을 PDF로 변환하는 것을 지원합니다. 라이브러리는 이미지 및 관련 리소스를 포함한 전체 웹 페이지 콘텐츠를 처리하고 이를 PDF 문서로 변환할 수 있습니다.

#### Q: MHT를 PDF로 변환하는 동안 PDF 출력을 사용자 정의할 수 있습니까?

A: 예, .NET용 Aspose.PDF는 MHT에서 PDF로 변환하는 동안 PDF 출력을 사용자 정의할 수 있는 다양한 옵션을 제공합니다. 페이지 크기, 방향, 여백 등과 같은 속성을 설정하여 결과 PDF 문서의 모양을 제어할 수 있습니다.

#### Q: .NET용 Aspose.PDF는 PDF 출력에서 원본 MHT 파일의 하이퍼링크와 서식을 유지합니까?

A: 예, .NET용 Aspose.PDF는 PDF 출력에서 원본 MHT 파일의 하이퍼링크와 서식을 유지합니다. 라이브러리는 변환된 PDF가 소스 MHT 파일과 동일한 레이아웃 및 내용을 유지하도록 보장합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 여러 MHT 파일을 별도의 PDF 문서로 변환할 수 있습니까?

A: 예, .NET용 Aspose.PDF를 사용하여 여러 MHT 파일을 별도의 PDF 문서로 변환할 수 있습니다. 각 MHT 파일을 로드하고 고유한 파일 이름을 가진 별도의 PDF 문서로 저장하기만 하면 됩니다.