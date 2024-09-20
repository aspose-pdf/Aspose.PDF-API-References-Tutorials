---
title: Adicionar e pesquisar texto oculto em arquivo PDF
linktitle: Adicionar e pesquisar texto oculto em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda a adicionar e pesquisar texto oculto em documentos PDF usando o Aspose.PDF para .NET. Guia passo a passo com exemplos de código incluídos.
type: docs
weight: 20
url: /pt/net/programming-with-text/add-and-search-hidden-text/
---
## Introdução

Neste tutorial, nós o levaremos por um guia passo a passo sobre como adicionar e pesquisar texto oculto em um arquivo PDF usando o Aspose.PDF para .NET. Seja você um desenvolvedor experiente ou um novato procurando aprimorar suas habilidades de programação, este artigo fornecerá os insights necessários para incorporar a funcionalidade de texto oculto em seus aplicativos.

## Pré-requisitos

Antes de mergulhar na parte de codificação, há alguns pré-requisitos que você precisa cuidar:

### Lista de verificação de requisitos
- Visual Studio: Certifique-se de ter o Visual Studio instalado. Este tutorial pressupõe que você esteja usando o .NET Framework.
-  Aspose.PDF para .NET: Você precisa ter a biblioteca Aspose.PDF para .NET. Você pode baixá-la[aqui](https://releases.aspose.com/pdf/net/).
- Conhecimento básico de C#: A familiaridade com a programação em C# ajudará você a entender melhor os trechos de código.

## Pacotes de importação

Antes de começar com seu código, você precisa garantir que importou os namespaces Aspose.PDF necessários. Veja como fazer isso:

### Configure seu projeto
1. Abra o Visual Studio e crie um novo projeto C# ou use um existente.
2.  Instale o Aspose.PDF adicionando o pacote NuGet. Você pode fazer isso navegando até o Gerenciador de Pacotes NuGet e procurando por`Aspose.PDF`. 
3.  Alternativamente, você pode baixar a biblioteca diretamente de[aqui](https://releases.aspose.com/pdf/net/) e adicione-o como referência em seu projeto.

### Importar namespaces necessários
No topo do seu arquivo C#, importe os seguintes namespaces:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Esta etapa é crucial, pois esses namespaces contêm as classes e os métodos necessários para manipular documentos PDF.

## Criando um documento PDF com texto oculto

Agora que você configurou tudo, vamos seguir as etapas para criar um documento PDF que contenha texto visível e invisível.

### Etapa 1: Definir diretório de documentos
Primeiro, você vai querer configurar o caminho onde o PDF será salvo. É aqui que a mágica começa!

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Altere isso para seu diretório
```

 Esta linha define onde seu PDF gerado será armazenado. Não esqueça de substituir`YOUR DOCUMENT DIRECTORY` com seu caminho atual.

### Etapa 2: Crie um documento PDF
Em seguida, vamos criar um novo documento PDF e adicionar páginas a ele.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
```

Aqui, estamos inicializando um novo documento e adicionando uma página onde colocaremos nossos fragmentos de texto.

### Etapa 3: Adicionar texto visível e oculto
Agora adicionaremos texto visível e invisível ao nosso PDF.

```csharp
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
```

 Neste trecho,`frag1` será visível, enquanto`frag2` será definido como invisível em seguida.

### Etapa 4: Defina o texto como invisível
 Para fazer o texto de`frag2` invisível, você simplesmente modifica seu`TextState`.

```csharp
frag2.TextState.Invisible = true;
```

 Ao definir esta propriedade, qualquer texto associado a`frag2` não será renderizado quando o PDF for visualizado.

### Etapa 5: Adicionar fragmentos de texto à página
Por fim, adicionamos esses fragmentos de texto à página e salvamos o PDF.

```csharp
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Esta parte do código adiciona nossos fragmentos de texto à página. Depois disso, salvamos e descartamos o documento corretamente.

## Procurando por texto oculto no PDF

Agora que criamos nosso PDF com texto visível e oculto, como buscamos esse texto oculto? Vamos decompô-lo.

### Etapa 1: Carregue o documento PDF
Para procurar texto dentro do PDF, primeiro precisamos carregar o documento que acabamos de criar.

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
```

### Etapa 2: Crie um absorvedor de fragmentos de texto
 Nós usaremos`TextFragmentAbsorber` para capturar todos os fragmentos de texto no PDF.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
```

Aqui, especificamos que queremos absorver todos os fragmentos de texto da primeira página.

### Etapa 3: iterar pelos fragmentos
Agora, podemos iterar pelos fragmentos de texto coletados para descobrir quais estão visíveis e quais estão ocultos.

```csharp
foreach (TextFragment fragment in absorber.TextFragments)
{
    Console.WriteLine("Text '{0}' on pos {1} invisibility: {2}",
        fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
```

 Este loop verifica cada fragmento de texto e imprime seu conteúdo junto com sua posição e status de visibilidade. Se`fragment.TextState.Invisible` estiver definido como verdadeiro, significa que o texto está oculto!

### Etapa 4: descarte o documento
Por fim, lembre-se de descartar o documento novamente quando terminar.

```csharp
doc.Dispose();
```

## Conclusão

Neste tutorial, percorremos o emocionante processo de adicionar e pesquisar texto oculto em arquivos PDF usando o Aspose.PDF para .NET. Aprendemos como criar um documento PDF com texto visível e oculto, bem como pesquisar esse texto oculto programaticamente. Esse recurso pode ser incrivelmente útil em vários aplicativos, seja para armazenar informações confidenciais ou fornecer uma experiência de usuário única em seus documentos.

Conforme você se familiariza mais com o ASPose.PDF, as possibilidades se tornam infinitas. Continue experimentando e expandindo os limites do que você pode alcançar com seus documentos PDF!

## Perguntas frequentes

### O Aspose.PDF pode manipular arquivos PDF criptografados?  
Sim, o Aspose.PDF suporta criptografia e descriptografia de documentos PDF. Você pode proteger facilmente seus PDFs com senhas.

### Existe uma versão de teste disponível para o Aspose.PDF?  
 Absolutamente! Você pode baixar a versão de teste gratuita em[aqui](https://releases.aspose.com/).

### Quais linguagens de programação o Aspose.PDF suporta?  
Aspose.PDF oferece suporte para diversas linguagens, incluindo C#, Java e Python.

### Onde posso encontrar a documentação do Aspose.PDF?  
 Você pode acessar a documentação[aqui](https://reference.aspose.com/pdf/net/).

### Como posso obter suporte se tiver problemas?  
 Para obter suporte, você pode visitar os fóruns do Aspose[aqui](https://forum.aspose.com/c/pdf/10).