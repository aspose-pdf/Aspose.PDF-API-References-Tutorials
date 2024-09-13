---
title: Adicionar dica de ferramenta ao texto em arquivo PDF
linktitle: Adicionar dica de ferramenta ao texto em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como adicionar dicas de ferramentas ao texto em um arquivo PDF usando o Aspose.PDF para .NET.
type: docs
weight: 90
url: /pt/net/programming-with-text/add-tooltip-to-text/
---
Este tutorial guiará você pelo processo de adicionar dicas de ferramentas ao texto em um arquivo PDF usando Aspose.PDF para .NET. O código-fonte C# fornecido demonstra as etapas necessárias.

## Requisitos
Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro compilador C# instalado em sua máquina.
- Biblioteca Aspose.PDF para .NET. Você pode baixá-la do site oficial do Aspose ou usar um gerenciador de pacotes como o NuGet para instalá-la.

## Etapa 1: Configurar o projeto
1. Crie um novo projeto C# no seu ambiente de desenvolvimento preferido.
2. Adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: Importar os namespaces necessários
No arquivo de código onde você deseja adicionar dicas de ferramentas ao texto, adicione as seguintes diretivas using no topo do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Etapa 3: Defina o diretório do documento
 No código, localize a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seus documentos estão armazenados.

## Etapa 4: Crie um documento de amostra com texto
 Criar um novo`Document`objeto e adicione páginas com fragmentos de texto. No código fornecido, dois fragmentos de texto são adicionados ao documento com o respectivo texto de dica de ferramenta.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Etapa 5: Abra o documento e encontre os fragmentos de texto
 Carregue o documento criado usando o`Document` construtor e encontre os fragmentos de texto que precisam de dicas de ferramentas usando`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Etapa 6: adicione dicas de ferramentas aos fragmentos de texto
 Faça um loop pelos fragmentos de texto extraídos e crie botões invisíveis em suas posições. Atribua o texto da dica de ferramenta desejada ao`AlternateName` propriedade do`ButtonField`. Adicione os campos de botão ao formulário do documento.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Etapa 7: Repita para fragmentos de texto adicionais com dicas de ferramentas longas
Repita os passos 5 e 6 para fragmentos de texto com dicas de ferramentas longas. Modifique os critérios de busca e o texto da dica de ferramenta de acordo.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## Etapa 8: Salve o documento modificado
 Salve o documento PDF modificado usando o`Save` método do`Document` objeto.

```csharp
document. Save(outputFile);
```

### Código-fonte de exemplo para Adicionar dica de ferramenta ao texto usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Crie um documento de amostra com texto
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Abrir documento com texto
Document document = new Document(outputFile);
//Crie um objeto TextAbsorber para encontrar todas as frases que correspondem à expressão regular
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Aceite o absorvedor para as páginas do documento
document.Pages.Accept(absorber);
// Obtenha os fragmentos de texto extraídos
TextFragmentCollection textFragments = absorber.TextFragments;
// Percorrer os fragmentos
foreach (TextFragment fragment in textFragments)
{
	// Criar botão invisível na posição do fragmento de texto
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// O valor AlternateName será exibido como dica de ferramenta por um aplicativo visualizador
	field.AlternateName = "Tooltip for text.";
	// Adicionar campo de botão ao documento
	document.Form.Add(field);
}
// O próximo será um exemplo de dica de ferramenta muito longa
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Definir texto muito longo
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// Salvar documento
document.Save(outputFile);
```

## Conclusão
Você adicionou com sucesso dicas de ferramentas ao texto em um documento PDF usando Aspose.PDF para .NET. O arquivo PDF resultante agora pode ser encontrado no caminho do arquivo de saída especificado.

## Perguntas frequentes

#### P: Qual é o foco deste tutorial?

R: Este tutorial foca em adicionar dicas de ferramentas ao texto dentro de um arquivo PDF usando a biblioteca Aspose.PDF for .NET. O código-fonte C# fornecido demonstra as etapas necessárias para fazer isso.

#### P: Quais namespaces precisam ser importados para este tutorial?

R: No arquivo de código onde você deseja adicionar dicas de ferramentas ao texto, importe os seguintes namespaces no início do arquivo:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### P: Como especifico o diretório do documento?

 A: No código, encontre a linha`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

#### P: Como posso criar um documento de amostra com texto?

 R: Na Etapa 4, você criará um novo`Document` objeto e adicionar páginas com fragmentos de texto. O código fornecido adiciona dois fragmentos de texto com o respectivo texto de dica de ferramenta.

#### P: Como abro o documento e encontro os fragmentos de texto?

 R: Na Etapa 5, você carregará o documento criado usando o`Document` construtor e encontre os fragmentos de texto que requerem dicas de ferramentas usando o`TextFragmentAbsorber`.

#### P: Como adiciono dicas de ferramentas aos fragmentos de texto?

 A: Na Etapa 6, você percorrerá os fragmentos de texto extraídos e criará botões invisíveis em suas posições. O texto da dica de ferramenta é atribuído ao`AlternateName` propriedade do`ButtonField`, que é adicionado ao formulário do documento.

#### P: Como repito o processo para fragmentos de texto adicionais com dicas de ferramentas longas?

R: Para fragmentos de texto com dicas de ferramentas longas, repita as etapas 5 e 6. Modifique os critérios de pesquisa e o texto da dica de ferramenta adequadamente.

#### P: Como faço para salvar o documento modificado?

 R: Na Etapa 8, você salvará o documento PDF modificado usando o`Save` método do`Document` objeto.

#### P: Qual é o principal aprendizado deste tutorial?

R: Ao seguir este tutorial, você aprendeu como aprimorar seu documento PDF adicionando dicas de ferramentas ao texto usando o Aspose.PDF para .NET. Isso pode fornecer informações adicionais valiosas para os leitores quando eles interagem com o conteúdo do PDF.