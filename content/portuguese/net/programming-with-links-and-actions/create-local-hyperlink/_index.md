---
title: Criar hiperlink local em arquivo PDF
linktitle: Criar hiperlink local em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Crie facilmente hiperlinks locais em arquivos PDF usando o Aspose.PDF para .NET.
type: docs
weight: 40
url: /pt/net/programming-with-links-and-actions/create-local-hyperlink/
---
Criar hyperlinks locais em um arquivo PDF permite que você crie links clicáveis que levam os usuários a outras páginas no mesmo documento PDF. Com o Aspose.PDF para .NET, você pode criar facilmente esses links seguindo o seguinte código-fonte:

## Etapa 1: Importar bibliotecas necessárias

Antes de começar, você precisa importar as bibliotecas necessárias para seu projeto C#. Aqui está a diretiva import necessária:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Etapa 2: Defina o caminho para a pasta de documentos

 Nesta etapa, você precisa especificar o caminho para a pasta onde deseja salvar o arquivo PDF resultante. Substituir`"YOUR DOCUMENT DIRECTORY"` no código a seguir com o caminho real para sua pasta de documentos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 3: Crie uma instância do Documento

 Criaremos uma instância do`Document` class para representar nosso documento PDF. Aqui está o código correspondente:

```csharp
Document doc = new Document();
```

## Etapa 4: adicione página e texto com hiperlinks

Nesta etapa, adicionaremos uma página ao nosso documento PDF e adicionaremos algum texto contendo hiperlinks locais. Definiremos as páginas de destino para cada link. Aqui está o código correspondente:

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## Etapa 5: Salve o documento atualizado

Agora vamos salvar o arquivo PDF atualizado usando o`Save` método do`doc` objeto. Aqui está o código correspondente:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Código-fonte de exemplo para criar hiperlink local usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Criar instância de documento
Document doc = new Document();
// Adicionar página à coleção de páginas do arquivo PDF
Page page = doc.Pages.Add();
// Criar instância de Fragmento de Texto
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Criar instância de hiperlink local
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Definir página de destino para instância de link
link.TargetPageNumber = 7;
// Definir hiperlink TextFragment
text.Hyperlink = link;
// Adicionar texto à coleção de parágrafos da página
page.Paragraphs.Add(text);
// Criar nova instância TextFragment
text = new TextFragment("link page number test to page 1");
// TextFragment deve ser adicionado sobre a nova página
text.IsInNewPage = true;
// Crie outra instância de hiperlink local
link = new LocalHyperlink();
// Definir página de destino para o segundo hiperlink
link.TargetPageNumber = 1;
// Definir link para o segundo TextFragment
text.Hyperlink = link;
// Adicionar texto à coleção de parágrafos do objeto de página
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Salvar documento atualizado
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Conclusão

Parabéns! Agora você tem um guia passo a passo para criar hiperlinks locais em um PDF usando Aspose.PDF para .NET. Você pode usar este código para criar links clicáveis que levam os usuários a outras páginas no mesmo documento.

Não deixe de conferir a documentação oficial do Aspose.PDF para obter mais informações sobre recursos avançados de hiperlink.

### Perguntas frequentes sobre como criar hiperlink local em arquivo PDF

#### P: O que são hiperlinks locais em um arquivo PDF?

R: Os hyperlinks locais em um arquivo PDF são links clicáveis que navegam os usuários para diferentes páginas dentro do mesmo documento. Esses links melhoram a navegação e permitem que os leitores acessem rapidamente as seções relevantes.

#### P: Como os hiperlinks locais podem beneficiar meu documento PDF?

R: Os hiperlinks locais fornecem uma maneira eficiente de conectar conteúdo relacionado dentro do mesmo documento PDF. Eles melhoram a experiência do usuário ao permitir que os leitores pulem rapidamente para seções específicas sem rolar pelo documento inteiro.

#### P: Como o Aspose.PDF para .NET oferece suporte à criação de hiperlinks locais?
A: O Aspose.PDF para .NET oferece suporte abrangente para criar hiperlinks locais. O tutorial passo a passo fornecido neste guia demonstra como adicionar hiperlinks locais ao seu documento PDF usando C#.

#### P: Posso personalizar a aparência dos hiperlinks locais?

R: Sim, você pode personalizar a aparência dos hiperlinks locais, incluindo a cor e o estilo do texto, para garantir que eles correspondam ao design do seu documento e forneçam uma experiência visual consistente.

#### P: É possível criar vários hiperlinks locais em uma única página PDF?

R: Com certeza! Você pode criar vários hyperlinks locais dentro de uma única página PDF, permitindo que os leitores pulem para várias seções ou páginas conforme necessário. Cada hyperlink local pode ser adaptado ao seu respectivo alvo.

#### P: Posso criar links para seções específicas de uma página usando hiperlinks locais?

A: Embora os hiperlinks locais normalmente naveguem para páginas inteiras, você pode criar âncoras ou marcadores dentro do seu documento PDF para obter links direcionados. O Aspose.PDF para .NET suporta várias opções de hiperlinks.

#### P: Como posso verificar se meus hiperlinks locais estão funcionando corretamente?

R: Seguindo o tutorial e o código de exemplo fornecidos, você pode criar hiperlinks locais funcionais com confiança. Você pode testar os links abrindo o documento PDF gerado e clicando no texto com hiperlink.

#### P: Há alguma limitação ao usar hiperlinks locais?

R: Os hiperlinks locais são uma maneira eficaz de melhorar a navegação no documento, mas é importante garantir que a estrutura do documento permaneça clara e intuitiva. Hiperlinks e âncoras devidamente rotulados contribuem para uma experiência positiva do usuário.

#### P: Posso criar hiperlinks locais dentro de tabelas ou imagens?

R: Sim, você pode criar hyperlinks locais dentro de vários elementos do seu documento PDF, incluindo tabelas, imagens e texto. O Aspose.PDF for .NET oferece flexibilidade para adicionar hyperlinks a diferentes tipos de conteúdo.