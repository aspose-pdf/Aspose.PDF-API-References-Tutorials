---
title: PDF를 PDFA3b로
linktitle: PDF를 PDFA3b로
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF를 PDF/A-3b로 변환하는 단계별 가이드입니다.
type: docs
weight: 150
url: /ko/net/document-conversion/pdf-to-pdfa3b/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일을 PDF/A-3b 형식으로 변환하는 과정을 안내합니다. PDF/A-3b는 PDF 문서에 파일과 데이터를 삽입하기 위한 ISO 표준입니다. 아래 단계에 따라 PDF 파일을 PDF/A-3b 형식으로 변환할 수 있습니다.

## 전제조건
시작하기 전에 다음 전제 조건을 충족하는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- 시스템에 설치된 .NET용 Aspose.PDF 라이브러리.
- Visual Studio와 같은 개발 환경.

## 1단계: 소스 PDF 문서 열기
이 단계에서는 .NET용 Aspose.PDF를 사용하여 소스 PDF 파일을 엽니다. 아래 코드를 따르십시오.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 소스 PDF 문서 열기
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 꼭 교체하세요`"YOUR DOCUMENTS DIRECTORY"` PDF 파일이 있는 실제 디렉토리를 사용하세요.

## 2단계: PDF/A-3b로 변환
PDF 파일을 연 후 PDF/A-3b 형식으로 변환을 진행할 수 있습니다. 다음 코드를 사용하세요.

```csharp
// PDF/A-3b 형식으로 변환
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

위 코드는 PDF 파일을 PDF/A-3b 형식으로 변환하고 변환 오류를 제거합니다.

## 3단계: 결과 PDF/A-3b 파일 저장
변환이 완료된 후 결과 PDF/A-3b 파일을 저장해야 합니다. 마지막 단계는 다음과 같습니다.

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// 출력 문서 저장
pdfDocument.Save(dataDir);
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 출력 PDF/A-3b 파일을 저장하려는 원하는 디렉토리로 이동합니다.

### .NET용 Aspose.PDF를 사용하여 PDF에서 PDFA3b로의 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// 출력 문서 저장
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일을 PDF/A-3b 형식으로 변환하는 단계별 프로세스를 다루었습니다. 위에 설명된 지침을 따르면 이제 PDF 파일을 PDF/A-3b 형식으로 변환할 수 있습니다. 이 기능은 PDF/A-3b 표준을 준수하는 PDF 문서에 추가 파일과 데이터를 포함하려는 경우에 유용합니다.

### FAQ

#### Q: PDF/A-3b란 무엇이며, 다른 PDF/A 표준과 어떻게 다릅니까?

답변: PDF/A-3b는 PDF 문서에 파일과 데이터를 삽입하여 PDF 문서를 독립적으로 만들고 장기간 보존할 수 있도록 하는 ISO 표준입니다. PDF/A-1 및 PDF/A-2와 같은 다른 PDF/A 표준과 달리 PDF/A-3b를 사용하면 PDF 문서 내에 추가 파일과 데이터를 포함할 수 있습니다. 이 기능을 사용하면 복잡한 대화형 문서를 보관하고 교환하는 데 적합합니다.

#### Q: PDF/A-3b 문서 내에 여러 파일과 데이터를 포함할 수 있습니까?

A: 예, PDF/A-3b의 주요 장점 중 하나는 PDF 문서 내에 여러 파일과 데이터를 포함할 수 있다는 것입니다. 기본 PDF 콘텐츠와 함께 XML, 스프레드시트, 이미지, 기타 PDF 파일 등 다양한 유형의 파일을 포함할 수 있습니다. 결과적으로 PDF/A-3b 문서는 필요한 모든 요소를 포함하는 독립적인 패키지가 됩니다.

#### Q: PDF를 PDF/A-3b로 변환하는 과정에서 오류가 발생하면 어떻게 됩니까?

 A: .NET용 Aspose.PDF를 사용하여 PDF를 PDF/A-3b 형식으로 변환할 때 오류 처리 방법을 제어할 수 있습니다. 그만큼`Convert` 행동 양식`ConvertErrorAction` 매개변수는 오류 발생 시 취할 조치를 결정합니다. 제공된 코드 예제에서는`ConvertErrorAction.Delete` 매개변수가 사용됩니다. 이는 변환 중에 오류가 발생하면 오류가 있는 페이지가 삭제된다는 의미입니다.

#### Q: PDF/A-3b는 문서 장기 보존에 적합한가요?

A: 예, PDF/A-3b는 전자 문서의 장기 보존을 위해 특별히 설계되었습니다. 추가 파일과 데이터를 포함함으로써 필요한 모든 구성 요소가 PDF 문서 자체에 포함되도록 보장하여 시간이 지남에 따라 정보 손실이나 외부 종속성의 위험을 줄입니다. 이 기능은 장기적인 접근성과 일관성을 보장하는 방식으로 문서를 보관하는 데 적합합니다.