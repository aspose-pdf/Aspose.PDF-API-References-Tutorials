---
title: HTML을 PDF로 변환하는 동안 자격 증명 제공
linktitle: HTML을 PDF로 변환하는 동안 자격 증명 제공
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF와 함께 자격 증명을 제공하여 HTML을 PDF로 변환하는 단계별 가이드입니다.
type: docs
weight: 240
url: /ko/net/document-conversion/provide-credentials-during-html-to-pdf/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 보안 URL에 액세스할 때 자격 증명을 제공하면서 HTML 파일을 PDF로 변환하는 과정을 안내합니다. 아래 단계를 따르면 적절한 자격 증명을 사용하여 HTML 콘텐츠를 PDF로 변환할 수 있습니다.

## 전제조건
시작하기 전에 다음 전제 조건을 충족하는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- 시스템에 설치된 .NET용 Aspose.PDF 라이브러리.
- Visual Studio와 같은 개발 환경.

## 1단계: 보안 HTML 콘텐츠 가져오기
이 단계에서는 적절한 자격 증명을 사용하여 URL에서 보안 HTML 콘텐츠를 가져옵니다. 다음 코드를 사용하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// URL에 대한 요청을 만듭니다.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// 서버에 필요한 경우 자격 증명을 설정합니다.
request.Credentials = CredentialCache.DefaultCredentials;
// 응답을 받으세요.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// 서버에서 반환한 콘텐츠가 포함된 스트림을 가져옵니다.
Stream dataStream = response. GetResponseStream();
// 쉽게 액세스할 수 있도록 StreamReader를 사용하여 스트림을 엽니다.
StreamReader reader = new StreamReader(dataStream);
// 내용을 읽어보세요.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 꼭 교체하세요`"YOUR DOCUMENTS DIRECTORY"` 결과 PDF 파일을 저장하려는 실제 디렉토리를 사용하십시오.

## 2단계: 자격 증명을 제공하여 HTML을 PDF로 변환
이제 검색된 HTML 콘텐츠를 로드하고 적절한 자격 증명을 제공하면서 PDF 형식으로 변환하겠습니다. 다음 코드를 사용하세요.

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// HTML 파일 로드
Document pdfDocument = new Document(stream, options);
```

## 3단계: 결과 PDF 파일 저장
마지막으로 결과 PDF 파일을 저장합니다. 다음 코드를 사용하세요.

```csharp
// 결과 PDF 파일을 저장
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 위의 코드는 결과 PDF 파일을 파일 이름으로 저장합니다.`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### .NET용 Aspose.PDF를 사용하여 HTML을 PDF로 변환하는 동안 자격 증명 제공에 대한 예제 소스 코드

```csharp
try
{
	
	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// URL에 대한 요청을 만듭니다.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// 서버에서 요구하는 경우 자격 증명을 설정합니다.
	request.Credentials = CredentialCache.DefaultCredentials;
	// 응답을 받으세요.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// 서버에서 반환한 콘텐츠가 포함된 스트림을 가져옵니다.
	Stream dataStream = response.GetResponseStream();
	// 쉽게 액세스할 수 있도록 StreamReader를 사용하여 스트림을 엽니다.
	StreamReader reader = new StreamReader(dataStream);
	// 내용을 읽어보세요.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// HTML 파일 로드
	Document pdfDocument = new Document(stream, options);
	// 결과 파일 저장
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 보안 URL에 액세스할 때 자격 증명을 제공하면서 HTML 파일을 PDF로 변환하는 단계별 프로세스를 다루었습니다. 위에 설명된 지침을 따르면 올바른 자격 증명을 제공하면서 HTML 콘텐츠를 PDF로 성공적으로 변환할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.PDF이 무엇인가요?

A: .NET용 Aspose.PDF는 개발자가 C# 애플리케이션에서 PDF 문서 작업을 할 수 있도록 지원하는 강력한 라이브러리입니다. HTML에서 PDF로의 변환을 포함하여 광범위한 기능을 제공합니다.

#### Q: URL에서 보안 HTML 콘텐츠를 어떻게 가져올 수 있나요?

 A: URL에서 보안 HTML 콘텐츠를 가져오려면 다음을 사용할 수 있습니다.`WebRequest` C#의 클래스입니다. 다음을 사용하여 적절한 자격 증명을 설정했는지 확인하십시오.`Credentials` 재산.

#### Q: 이 튜토리얼의 전제 조건은 무엇입니까?

A: 튜토리얼을 진행하기 전에 다음 전제 조건이 충족되었는지 확인하십시오.

- C# 프로그래밍 언어에 대한 기본 지식.
- 시스템에 설치된 .NET용 Aspose.PDF 라이브러리.
- Visual Studio와 같은 개발 환경.

#### Q: HTML을 PDF로 변환하는 동안 .NET용 Aspose.PDF는 외부 리소스를 어떻게 처리합니까?

 A: .NET용 Aspose.PDF는 다음을 제공합니다.`HtmlLoadOptions`HTML을 PDF로 변환하는 동안 외부 리소스를 처리하는 클래스입니다. 다음을 사용하여 외부 리소스 자격 증명을 설정할 수 있습니다.`ExternalResourcesCredentials` 재산.

#### Q: 결과 PDF 파일의 파일 이름을 사용자 정의할 수 있습니까?

 A: 예, PDF 문서를 저장하는 코드를 수정하여 결과 PDF 파일의 파일 이름을 사용자 정의할 수 있습니다. 간단히 원하는 파일 이름을 변경하세요.`pdfDocument.Save()` 방법.