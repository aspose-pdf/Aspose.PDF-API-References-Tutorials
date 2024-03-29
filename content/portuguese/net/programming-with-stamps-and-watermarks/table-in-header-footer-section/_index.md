---
title: Tabela na seção cabeçalho e rodapé
linktitle: Tabela na seção cabeçalho e rodapé
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como adicionar uma tabela na seção de cabeçalho/rodapé de um documento PDF com Aspose.PDF for .NET.
type: docs
weight: 170
url: /pt/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
Neste tutorial, iremos guiá-lo passo a passo sobre como adicionar uma tabela na seção de cabeçalho ou rodapé de um documento PDF usando Aspose.PDF for .NET. O código-fonte C# fornecido mostra como criar um documento PDF vazio, adicionar uma página, configurar a seção de cabeçalho, criar uma tabela, adicionar linhas e células à tabela e, finalmente, salvar o documento PDF.

## Passo 1: Configurando o ambiente

Antes de começar, certifique-se de ter o seguinte:

- Um ambiente de desenvolvimento .NET instalado.
- A biblioteca Aspose.PDF para .NET baixada e referenciada em seu projeto.

## Etapa 2: Criando o documento e a página PDF

 O primeiro passo é criar uma instância do`Document` class e adicione uma página ao documento. Veja como:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instanciar um objeto Document
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Crie uma página no documento PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório onde deseja salvar o documento PDF.

## Etapa 3: configurar a seção do cabeçalho

 Agora configuraremos a seção de cabeçalho do documento PDF criando uma instância do`HeaderFooter` aula. Veja como:

```csharp
// Crie uma seção de cabeçalho para o arquivo PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Defina a seção de cabeçalho da página
page. Header = header;

// Defina a margem superior da seção do cabeçalho
header. Margin. Top = 20;
```

## Etapa 4: Criando a tabela

 Agora vamos criar uma tabela usando o`Table` classe e adicione-a à coleção de parágrafos da seção de título. Veja como:

```csharp
// Instanciar um objeto Table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Adicione a tabela à coleção de parágrafos da seção de cabeçalho
header.Paragraphs.Add(tab1);

// Defina as larguras das colunas da tabela
tab1.ColumnWidths = "60,300";
```

O código acima cria uma tabela com duas colunas de larguras especificadas.

## Etapa 5: adicionar linhas e células à tabela

 Agora adicionaremos linhas e células à tabela usando o`Row` classe e o`Cell` aula. Veja como:

```csharp
// Crie uma linha na tabela e adicione células
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Mesclar a primeira célula da primeira linha
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Crie outra linha na tabela e adicione uma célula com uma imagem
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Passo 6: Salvando o Documento PDF

Depois que a tabela for adicionada à seção de cabeçalho, podemos salvar o documento PDF. Veja como:

```csharp
// Salve o arquivo PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório onde deseja salvar o documento PDF.

### Exemplo de código-fonte para tabela na seção cabeçalho e rodapé usando Aspose.PDF para .NET 
```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancie a instância do Document chamando o construtor vazio
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Crie uma página no documento PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// Crie uma seção de cabeçalho do arquivo PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//Defina o cabeçalho ímpar para o arquivo PDF
page.Header = header;

// Defina a margem superior para a seção do cabeçalho
header.Margin.Top = 20;

// Instanciar um objeto de tabela
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Adicione a tabela na coleção de parágrafos da seção desejada
header.Paragraphs.Add(tab1);

// Definir borda de célula padrão usando o objeto BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Definir com larguras de coluna da tabela
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Crie linhas na tabela e depois células nas linhas
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Defina o valor do intervalo de linha para a primeira linha como 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Crie linhas na tabela e depois células nas linhas
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Defina a cor de fundo da Linha2
row2.BackgroundColor = Color.White;

// Adicione a célula que contém a imagem
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Defina a largura da imagem para 60
img.FixWidth = 60;

// Adicione a imagem à célula da tabela
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Defina o alinhamento vertical do texto como alinhado ao centro
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Salve o arquivo PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Conclusão

Parabéns! Você aprendeu como adicionar uma tabela na seção de cabeçalho ou rodapé de um documento PDF usando Aspose.PDF for .NET. Agora você pode personalizar seus cabeçalhos e rodapés adicionando tabelas para exibir informações adicionais em seus documentos PDF.

### Perguntas frequentes para tabela na seção de rodapé do cabeçalho

#### P: Qual é o propósito de adicionar uma tabela na seção de cabeçalho ou rodapé de um documento PDF?

R: Adicionar uma tabela na seção de cabeçalho ou rodapé de um documento PDF permite exibir informações estruturadas e organizadas, como títulos, subtítulos, logotipos ou qualquer outro conteúdo que você deseja que apareça de forma consistente em cada página do documento.

#### P: Como o código-fonte C# fornecido consegue adicionar uma tabela na seção de cabeçalho ou rodapé de um documento PDF?

R: O código demonstra o processo de criação de um documento PDF vazio, adição de uma página, configuração da seção de cabeçalho, criação de uma tabela com linhas e células e, finalmente, salvamento do documento PDF. O resultado é uma tabela exibida na seção de cabeçalho do documento PDF.

#### P: Posso personalizar a aparência das células da tabela, como bordas, cor de fundo e estilo do texto?

R: Sim, você pode personalizar a aparência das células da tabela definindo propriedades como bordas das células, cor de fundo, estilo do texto, fonte, tamanho da fonte e muito mais.

#### P: Como a tabela é adicionada à seção de cabeçalho do documento PDF?

R: O código adiciona a tabela à coleção de parágrafos da seção de cabeçalho, o que garante que a tabela seja exibida no cabeçalho de cada página.

#### P: Posso adicionar mais linhas e células à tabela conforme necessário?

 R: Com certeza, você pode adicionar mais linhas e células à tabela usando o`Rows.Add()` e`Cells.Add()` métodos. Isso permite estruturar o conteúdo da tabela conforme desejado.

#### P: É possível ajustar a largura das colunas da tabela?
 R: Sim, você pode ajustar a largura das colunas da tabela usando o`ColumnWidths` propriedade. Isso permite que você controle o layout da tabela.

#### P: Como posso distribuir células por várias colunas ou linhas da tabela?
 R: Para abranger células em várias colunas, você pode usar o`ColSpan` propriedade da célula correspondente. Da mesma forma, você pode usar o`RowSpan` propriedade para abranger células em várias linhas.

#### P: O que acontece se eu quiser adicionar uma tabela às seções de cabeçalho e rodapé do documento PDF?

R: Você pode seguir uma abordagem semelhante para as seções de cabeçalho e rodapé. Basta criar um`HeaderFooter` instância para o rodapé, configure-a e adicione a tabela à sua coleção de parágrafos.

#### P: Posso usar imagens nas células da tabela e como isso é feito?

 R: Sim, você pode adicionar imagens nas células da tabela. O exemplo de código demonstra a adição de uma imagem a uma célula criando um`Image` objeto, definindo seu caminho de arquivo e dimensões e, em seguida, adicionando-o aos parágrafos de uma célula.

#### P: Como posso garantir que a tabela apareça de forma consistente em todas as páginas do documento PDF?

 R: Quando você adiciona a tabela à seção de cabeçalho ou rodapé usando o`HeaderFooter` Por exemplo, Aspose.PDF garante que a tabela apareça de forma consistente em cada página, fornecendo um layout uniforme.