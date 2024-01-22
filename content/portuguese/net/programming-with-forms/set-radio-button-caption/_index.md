---
title: Definir legenda do botão de opção
linktitle: Definir legenda do botão de opção
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como usar Aspose.PDF for .NET para definir a legenda de um botão de opção em um formato PDF.
type: docs
weight: 280
url: /pt/net/programming-with-forms/set-radio-button-caption/
---
Neste guia, explicaremos passo a passo como usar a biblioteca Aspose.PDF para .NET para definir a legenda de um botão de opção em um formato PDF. Mostraremos como acessar o campo do botão de opção, criar uma nova opção de botão de opção e personalizar a legenda do botão.

## Passo 1: Configurando o diretório do documento

 O primeiro passo é configurar o diretório do documento onde está localizado o formulário PDF no qual você deseja trabalhar. Você pode usar o`dataDir` variável para especificar o caminho do diretório.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Certifique-se de substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real para o diretório de documentos.

## Etapa 2: Carregando o formulário PDF de origem

 Nesta etapa, carregaremos o formulário PDF de origem usando o`Aspose.Pdf.Facades.Form` classe de Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Certifique-se de que o arquivo PDF que contém o formulário esteja presente no diretório de documentos especificado.

## Etapa 3: editando a legenda do botão de opção

Percorreremos os nomes dos campos do formulário e procuraremos os campos dos botões de opção. Se um campo correspondente for encontrado, criaremos uma nova opção de botão de opção com uma legenda personalizada e a adicionaremos ao campo existente.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// Crie um objeto TextParagraph
TextParagraph par = new TextParagraph();
// Definir posição do parágrafo
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Especifique o modo de quebra de linha
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Adicione o novo TextFragment ao parágrafo
par.AppendLine(updatedFragment);
// Adicione o TextParagraph usando TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Personalize o botão de opção de legenda e outras configurações conforme necessário.

## Passo 4: Salvando o PDF resultante

 Agora que terminamos de modificar a legenda do botão de opção, podemos salvar o PDF resultante usando o`Save` método do`Document` aula.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Certifique-se de especificar o caminho completo e o nome do arquivo do PDF resultante.

### Exemplo de código-fonte para definir legenda do botão de opção usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Carregar formulário PDF de origem
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// Criar objeto TextParagraph
		TextParagraph par = new TextParagraph();
		// Definir posição do parágrafo
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Especifique o modo de quebra automática de palavras
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Adicionar novo TextFragment ao parágrafo
		par.AppendLine(updatedFragment);
		// Adicione o TextParagraph usando TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Conclusão

Neste guia, aprendemos como usar a biblioteca Aspose.PDF para .NET para definir a legenda de um botão de opção em formato PDF. Seguindo as etapas descritas, você pode personalizar as opções do botão de opção e alterar a legenda conforme necessário. Sinta-se à vontade para explorar ainda mais os recursos do Aspose.PDF for .NET para expandir as possibilidades de manipulação de arquivos PDF.

### Perguntas frequentes

#### P: Posso usar o Aspose.PDF for .NET para definir legendas para botões de opção em um formato PDF?

R: Sim, você pode usar Aspose.PDF for .NET para definir legendas para botões de opção em formato PDF. O exemplo de código-fonte fornecido demonstra como acessar o campo do botão de opção, criar uma nova opção de botão de opção com uma legenda personalizada e atualizar o campo existente.

#### P: Como posso personalizar a aparência da legenda do botão de opção, como tamanho e cor da fonte?

 R: Você pode personalizar a aparência da legenda do botão de opção ajustando as propriedades do`TextFragment` usado para a legenda. Por exemplo, você pode definir a fonte, o tamanho da fonte, a cor, o espaçamento entre linhas e outras opções de formatação de texto.

#### P: É possível adicionar várias opções de botões de opção com legendas diferentes a um único grupo de botões de opção?

R: Sim, você pode adicionar várias opções de botões de opção com legendas diferentes a um único grupo de botões de opção. Cada opção representará uma escolha diferente e os usuários poderão selecionar apenas uma opção do grupo.

#### P: Posso usar o Aspose.PDF for .NET para modificar outros campos de formulário em um documento PDF?

R: Sim, o Aspose.PDF for .NET fornece um conjunto abrangente de recursos para manipular vários campos de formulário em um documento PDF, como campos de texto, caixas de seleção, listas suspensas e muito mais. Você pode usar a biblioteca para definir valores, modificar aparências e adicionar interatividade aos campos de formulário.

#### P: O Aspose.PDF for .NET oferece suporte ao trabalho com PDFs gerados de outras fontes, como documentos digitalizados?

R: Sim, o Aspose.PDF for .NET suporta trabalhar com PDFs gerados de várias fontes, incluindo documentos digitalizados. A biblioteca fornece recursos de OCR (reconhecimento óptico de caracteres) para extrair texto de PDFs digitalizados e manipular o conteúdo de forma programática.