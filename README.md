# Referência da linguagem

## Variáveis em C# (Visual C-Sharp)

Geralmente, _variável_, ou _var_ em C# (Visual C-Sharp), é o nome usado para definir um ou mais valores que são manipulados pelos programas durante seu funcionamento.

## Sobre o repositório

Aqui, neste repositório, veremos um passo a passo das _mais usadas_ para poder começar a programar.

É um imenso prazer:

Me chamo Fábio Santos, e este é meu _primeiro contato_ com a linguagem de programação C# (Visual C-Sharp). Nasci em meados dos anos 80 e tenho um conhecimento rápido de QBasic (Microsoft QuickBASIC) e Assembly para processadores 80x86 e um conhecimento _mais profundo_ em Visual Basic.

Bem-vindo!

## Sintaxe

&nbsp;&nbsp;&nbsp;&nbsp;[ _access_ ( **`VAR` | _type_** ) _name_ = { _value_ } ]

### Parâmetros

#### _access_ [opcional]

   + **`Public`** A palavra-chave `Público` na instrução de declaração especifica que o elemento pode ser acessado a partir do código em qualquer lugar do mesmo projeto, em outros projetos que referenciam o projeto e em qualquer assembly criado a partir do projeto.
   + **`Protected`** A palavra-chave `Protected` na instrução de declaração especifica que o elemento só pode ser acessado de dentro da mesma classe ou de uma classe derivada dessa classe.
   + **`Friend`** A palavra-chave `Friend` na instrução de declaração especifica que o elemento pode ser acessado no mesmo assembly, mas não de fora do assembly.
   + **`Private`** A palavra-chave `Private` na instrução de declaração especifica que o elemento só pode ser acessado no mesmo módulo, classe ou estrutura.
   + **`Protected Friend`** A combinação de palavras-chave `Protected Friend` na instrução de declaração especifica que o elemento pode ser acessado nas classes derivadas, no mesmo assembly ou em ambos.
   + **`Private Protected`** A combinação de palavras-chave `Private Protected` na instrução de declaração especifica que o elemento só pode ser acessado na mesma classe, bem como nas classes derivadas encontradas no mesmo assembly que a classe relativa.

#### _`type`_

+ **`object`** 32-bits ou 64-bits sendo possível armazenar qualquer tipo em uma variável do tipo Object.
+ **`bool`** 1-bit  (2^1), com sinal (0) [ true | false ], depende da implementação da plataforma.
+ **`sbyte`** 8-bits ((2^8)/2)-1, com sinal (-128 a 127).
+ **`byte`** 8-bits (2^8)-1, sem sinal (0 a 255).
+ **`char`** 16-bits (2^16)-1, sem sinal (0 a 65535) sintaxe 'A' e não "A".
+ **`short`** 16-bits ((2^16)/2)-1, com sinal (-32768 a 32767 ), **System.Int16**.
+ **`ushort`** 16-bits (2^16)-1, sem sinal (0 a 65535) **System.UInt16**, **`WORD`**.
+ **`[int]`** 32-bits ((2^16)/2)-1, com sinal (-2147483648 a 2147483647 ) **System.Int32**.
+ **`uint`** 32-bits (2^32)-1, sem sinal (0 a 4294967295) **System.UInt32**, DoubleWORD (**`DWORD`**).
+ **`long`** 64-bits ((2^64)/2)-1, com sinal (-9223372036854775808L a 9223372036854775807L) **System.Int64**.
+ **`ulong`** 64-bits (2^64)-1, sem sinal (0L a 18446744073709551615L) **System.UInt64**.
+ **`float`** 32-bits, FLOAT, -1.175494351E-38F a 3.402823466E+38F **System.Single**.
+ **`[double]`** 64-bits, DoubleFLOAT, -2.2250738585072014E-308 a 1.7976931348623158E+308 **System.Double**.
+ **`decimal`** 96-bits  int/float (-79228162514264337593543950335M a 79228162514264337593543950335M) **System.Decimal**.
+ **`string`** 2 bilhões de caracteres Unicode.

> Nota: sempre use o sufixo literal forçado L/UL ou l/ul para diferenciar o tipo long e ulong do padrão int, use F ou f para diferenciar o tipo float do padrão double racional, use M ou m para distinguir decimal de todos os outros valores numéricos. Também podemos usar o prefixo literal @ (verbatim) para ignorar comandos de string ou $ (interpolar) para aceitar e converter  comandos {variáveis} e \x0041 em string.

#### _name_

+ Um nome válido para descrever procedimentos, tipos de dados ou objetos.

#### _value_

+ Um valor de atribuição para dados char 'a', string "a", números 123 ou até mesmo objeto.

## Literais e conversões

> Dica: podemos converter valores, desde que tenham possibilidade de conversão. Não podemos converter um "rato" em "elefante"! As possíveis conversões são _numéricas_ em tipos de números, _não numéricas_ em tipos de textos e também _classes_, _(diversas)_ em tipos de objetos.

var SignedByte = (sbyte)42;<br>
uint UnsignedInt = (uint)SignedByte;

## Exemplo
```cs
using System;
namespace variable_type
{
    public partial class VariableType : System.Windows.Forms.Form
    {
        public VariableType()
        {
            InitializeComponent();
        }
        private void button1_Click(object sender, System.EventArgs e)
        {
            // statements //////////////////////////////////////////////////////////////
            var Int_EmployeeID = 1;
            var Str_LastName = "Hejlsberg";
            var Str_FirstName = "Anders";
            var Chr_Gender = 'M';
            var Date_BirthDate = System.DateTime.Parse("2/12/1960", new System.Globalization.CultureInfo("pt-BR"));
            var Int_Age = System.DateTime.Now.Year - Date_BirthDate.Year; // metadados
            var Sng_Salary = 92400.55F;
            var Str_CurrencyType = string.Format(new System.Globalization.CultureInfo("pt-BR"), "{0:C}", Sng_Salary); // metadados
            var Bool_Deleted = false;
            var Bool_Enabled = true;
            var Str_Notes = "Anders Hejlsberg é um engenheiro de software dinamarquês que ganhou prestígio pelo desenvolvimento do Delphi e Turbo Pascal na Borland e a plataforma .NET após ter migrado para a Microsoft. Projetista Chefe da linguagem C#.";
            var Obj_Photo = new System.Drawing.Bitmap("./res/empid1.png", true);
            // fields //////////////////////////////////////////////////////////////////
            this.textBox1.Text = $"{Int_EmployeeID}";
            this.textBox2.Text = Str_LastName;
            this.textBox3.Text = Str_FirstName;
            this.textBox4.Text = $"{Chr_Gender}";
            this.textBox5.Text = $"{Date_BirthDate.Day}/{Date_BirthDate.Month}/{Date_BirthDate.Year}";
            this.textBox6.Text = $"{Int_Age}";
            this.textBox7.Text = $"{Str_CurrencyType}";
            this.checkBox1.Checked = Bool_Deleted;
            this.checkBox2.Checked = Bool_Enabled;
            // notes ///////////////////////////////////////////////////////////////////
            this.textBox8.Multiline = true;
            this.textBox8.Size = new System.Drawing.Size(383, 64);
            this.textBox8.ScrollBars = System.Windows.Forms.ScrollBars.Both;
            this.textBox8.WordWrap = true;
            this.textBox8.Text = Str_Notes;
            // photo ///////////////////////////////////////////////////////////////////
            this.pictureBox1.BackColor = System.Drawing.ColorTranslator.FromHtml("#000000");
            this.pictureBox1.SizeMode = System.Windows.Forms.PictureBoxSizeMode.Zoom;
            this.pictureBox1.Image = Obj_Photo;
        }
    }
}
```

## Captura de tela

![variable-type-sample](https://github.com/fabasapro/variable-type/blob/main/screenshot/variable-type.png)<br>
Explore, no [repositório](https://github.com/fabasapro/variable-type/tree/main), este código simples para iniciantes.

## Referências
<sup>` 1.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) [«wiki» &#x2B0F;](), Encyclopædia Britannica, 1, London: Encyclopædia Britannica, Inc., 2007, consultado em 27 de janeiro de 2018, cópia arquivada em 24 de abril de 2008</sup><br />
<sup>` 2.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) Mitchell, Scott (julho de 2008), Easy Wiki Hosting, Scott Hanselman's blog, and Snagging Screens, MSDN Magazine, consultado em 9 de março de 2010, cópia arquivada em 16 de março de 2010</sup><br />
<sup>` 3.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) Alexa Top Sites, consultado em 1 de dezembro de 2016, cópia arquivada em 2 de março de 2015</sup><br />
<sup>` 4.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) Cunningham, Ward (27 de junho de 2002), What is a Wiki, WikiWikiWeb, consultado em 10 de abril de 2008, cópia arquivada em 16 de abril de 2008</sup><br />
<sup>` 5.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) mauimapp.com. Hawaiian Words; Hawaiian to English [archived 14 de setembro de 2008; citado em 19 de setembro de 2008].</sup><br />
<sup>` 6.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) Hasan, Heather (2012), Wikipedia, 3.5 million articles and counting, ISBN 9781448855575, p. 11</sup><br />
<sup>` 7.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) Andrews, Lorrin (1865), A dictionary of the Hawaiian language to which is appended an English-Hawaiian vocabulary and a chronological table of remarkable events, Henry M. Whitney, p. 514</sup><br />
<sup>` 8.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) «wiki wiki - Tradução em português». Dicionário Linguee. Consultado em 29 de dezembro de 2022</sup><br />
<sup>` 9.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) Barrett, Daniel J (2009). MediaWiki. Sebastopol, CA: O´Reily. ISBN 978-0-596-51979-7</sup><br />
<sup>`10.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) «Meatball Wiki: WikiMarkupStandard». meatballwiki.org. Consultado em 29 de maio de 2022</sup><br />





ref

https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/tokens/verbatim
https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/tokens/interpolated


Considerações finais

1 ponto positivo

--- falando sobre a maneira inteligente de usar literais, existem apenas aqueles que são necessários, ao contrário do Visual Basic que tem todos eles, o C# é focado em algo mais racional e produtivo.

   e 1 negativo apenas

-- os nomes nos menus e dentro das bibliotecas em letras maiúsculas são muito confusos, exigindo sempre o uso de uma IDE com assistente, mas mesmo com a IDE o código não tem muita formatação, parece que estou programando no "Notepad " sem formatação automática, apenas mensagens de erro.

conclusão

mas tudo para se obter uma linguagem com uma dimensão extremamente maior que o Visual Basic e outras linguagens, além de ser fácil para quem já programou em .NET ou Java.














  Parâmetro `name`:
    Determine o nome da variável declarada.
            //
    Parâmetro `value`:
    Determine o valor da variável declarada.

































<code>
+--------+ +-------+
¦ início +-¦ i = 0 +-+
+--------+ +-------+ ?
        +------------¦
        ? verdadeiro ¦ falso
  +-----------+  +-------+
  ¦ i = i + 1 +--¦ i < 6 +-+
  +-----------+  +-------+ ?
                        +-----+
                        ¦ fim ¦
                        +-----+
</code>







<p><sub>Artigo</sub><br><strong>Criando uma visualização de código melhor e mais rápida</strong><br><sup>O novo GitHub Code View traz aos usuários muitos novos recursos para melhorar as experiências de leitura e exploração de código, e superamos vários obstáculos técnicos exclusivos para fornecer esses recursos sem comprometer o desempenho.</sup></p>

<p><img aria-label="Profile" title="" src="https://avatars.githubusercontent.com/u/137560489?u=7f7818d3a0f04cb8bd1e4f6da0603d4a9c475182&amp;v=4" alt="@fabasapro" width="40" height="40">
<strong>Por <a aria-label="Overview" href="https://github.com/fabasapro" title="Clique e 'follow'">@FabasapPro</a> for social</strong><br><sup>Publicado 21 jul 2023 03h20 &#x02022; Atualizado 21 jul 2023 03h20</sup></p>

<p><svg aria-label="Overview" aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true"><path d="M0 1.75A.75.75 0 0 1 .75 1h4.253c1.227 0 2.317.59 3 1.501A3.743 3.743 0 0 1 11.006 1h4.245a.75.75 0 0 1 .75.75v10.5a.75.75 0 0 1-.75.75h-4.507a2.25 2.25 0 0 0-1.591.659l-.622.621a.75.75 0 0 1-1.06 0l-.622-.621A2.25 2.25 0 0 0 5.258 13H.75a.75.75 0 0 1-.75-.75Zm7.251 10.324.004-5.073-.002-2.253A2.25 2.25 0 0 0 5.003 2.5H1.5v9h3.757a3.75 3.75 0 0 1 1.994.574ZM8.755 4.75l-.004 7.322a3.752 3.752 0 0 1 1.992-.572H14.5v-9h-3.495a2.25 2.25 0 0 0-2.25 2.25Z"></path>
</svg>&nbsp;<a aria-label="Overview" href="https://github.com/fabasapro" title="Visão geral">Principal</a>&nbsp;&#x22EE;&nbsp;<svg aria-label="Repositories" aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true">
<path d="M2 2.5A2.5 2.5 0 0 1 4.5 0h8.75a.75.75 0 0 1 .75.75v12.5a.75.75 0 0 1-.75.75h-2.5a.75.75 0 0 1 0-1.5h1.75v-2h-8a1 1 0 0 0-.714 1.7.75.75 0 1 1-1.072 1.05A2.495 2.495 0 0 1 2 11.5Zm10.5-1h-8a1 1 0 0 0-1 1v6.708A2.486 2.486 0 0 1 4.5 9h8ZM5 12.25a.25.25 0 0 1 .25-.25h3.5a.25.25 0 0 1 .25.25v3.25a.25.25 0 0 1-.4.2l-1.45-1.087a.249.249 0 0 0-.3 0L5.4 15.7a.25.25 0 0 1-.4-.2Z"></path>
</svg>&nbsp;<a aria-label="Repositories" href="https://github.com/fabasapro?tab=repositories" title="Repositórios">Repositórios</a>&nbsp;&#x22EE;&nbsp;<svg aria-label="Projects" aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true"><path d="M0 1.75C0 .784.784 0 1.75 0h12.5C15.216 0 16 .784 16 1.75v12.5A1.75 1.75 0 0 1 14.25 16H1.75A1.75 1.75 0 0 1 0 14.25ZM6.5 6.5v8h7.75a.25.25 0 0 0 .25-.25V6.5Zm8-1.5V1.75a.25.25 0 0 0-.25-.25H6.5V5Zm-13 1.5v7.75c0 .138.112.25.25.25H5v-8ZM5 5V1.5H1.75a.25.25 0 0 0-.25.25V5Z"></path>
</svg>&nbsp;<a aria-label="Projects" href="https://github.com/fabasapro?tab=projects" title="Projects">Projetos</a>&nbsp;&#x22EE;&nbsp;<svg aria-label="Packages" aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true"><path d="M0 1.75C0 .784.784 0 1.75 0h12.5C15.216 0 16 .784 16 1.75v12.5A1.75 1.75 0 0 1 14.25 16H1.75A1.75 1.75 0 0 1 0 14.25ZM6.5 6.5v8h7.75a.25.25 0 0 0 .25-.25V6.5Zm8-1.5V1.75a.25.25 0 0 0-.25-.25H6.5V5Zm-13 1.5v7.75c0 .138.112.25.25.25H5v-8ZM5 5V1.5H1.75a.25.25 0 0 0-.25.25V5Z"></path>
</svg><a aria-label="Packages" href="https://github.com/fabasapro?tab=packages" title="Pacotes">Pacotes</a>&nbsp;&#x22EE;&nbsp;<svg aria-label="Stars" aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true"><path d="M8 .25a.75.75 0 0 1 .673.418l1.882 3.815 4.21.612a.75.75 0 0 1 .416 1.279l-3.046 2.97.719 4.192a.751.751 0 0 1-1.088.791L8 12.347l-3.766 1.98a.75.75 0 0 1-1.088-.79l.72-4.194L.818 6.374a.75.75 0 0 1 .416-1.28l4.21-.611L7.327.668A.75.75 0 0 1 8 .25Zm0 2.445L6.615 5.5a.75.75 0 0 1-.564.41l-3.097.45 2.24 2.184a.75.75 0 0 1 .216.664l-.528 3.084 2.769-1.456a.75.75 0 0 1 .698 0l2.77 1.456-.53-3.084a.75.75 0 0 1 .216-.664l2.24-2.183-3.096-.45a.75.75 0 0 1-.564-.41L8 2.694Z"></path>
</svg>&nbsp;<a aria-label="Stars" href="https://github.com/fabasapro?tab=stars" title="Estrelas">Estrelas</a></p>



















<p><a href="https://github.com/FabasaPro/wikis/blogs/tree/main" aria-label="Blogs" title="Artigos e Postagens de publicações">Blogues</a> &#x22EE; <a href="https://github.com/FabasaPro/wikis/tutorials/tree/main" aria-label="Tutorials" title="Samples e Soluções de projetos">Tutoriais</a> &#x22EE; <a href="https://github.com/FabasaPro/wikis/pulls" aria-label="Pulls" title="Contribua por Pull Requests">Contribuir</a> &#x22EE; <a href="LICENSE" aria-label="License" title="Serviços e Políticas de privacidade">Termos de Uso</a><br><sup><strong>Copyright © 1996 – 2023 Developer & Design, por Fábio Santos. Todos os direitos reservados.</strong></sup></p>

<p><strong>Artigo</strong><br>Por FabasaPro for social<br><sup>Publicado 21 jul 2023 03h20 &#x02022; Atualizado 21 jul 2023 03h20</sup>

<p><strong>Postagem</strong><br>Por FabasaPro for social<br><sup>Publicado 21 jul 2023 03h20 &#x02022; Atualizado 21 jul 2023 03h20</sup>

<p><strong>Sample</strong><br>Por FabasaPro for social<br><sup>Criado 21 jul 2023 03h20 &#x02022; Atualizado 21 jul 2023 03h20</sup>

<p><strong>Projeto</strong><br>Por FabasaPro for social<br><sup>Publicado 21 jul 2023 03h20 &#x02022; Atualizado 21 jul 2023 03h20</sup></p>

123 



<p><a href="https://github.com/FabasaPro/wikis/blogs/tree/main" aria-label="Directory" data-anchorjs-icon="??" title="Artigos e Postagens de publicações"><svg aria-label="Directory" aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true"><path d="M1.75 1A1.75 1.75 0 0 0 0 2.75v10.5C0 14.216.784 15 1.75 15h12.5A1.75 1.75 0 0 0 16 13.25v-8.5A1.75 1.75 0 0 0 14.25 3H7.5a.25.25 0 0 1-.2-.1l-.9-1.2C6.07 1.26 5.55 1 5 1H1.75Z"></path></svg><span>Blogs</span></a></p>

<p><a href="https://github.com/FabasaPro/wikis/blogs/tree/main" aria-label="Directory" data-anchorjs-icon="??" title="Samples e Soluções de projetos"><svg aria-label="Directory" aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true"><path d="M1.75 1A1.75 1.75 0 0 0 0 2.75v10.5C0 14.216.784 15 1.75 15h12.5A1.75 1.75 0 0 0 16 13.25v-8.5A1.75 1.75 0 0 0 14.25 3H7.5a.25.25 0 0 1-.2-.1l-.9-1.2C6.07 1.26 5.55 1 5 1H1.75Z"></path></svg><span>Tutoriais</span></a></p>

<p><a href="https://github.com/FabasaPro/wikis/blogs/tree/main" aria-label="File" data-anchorjs-icon="??" title="Sobre o LEIA-ME.md"><svg aria-label="File" aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true"><path d="M2 1.75C2 .784 2.784 0 3.75 0h6.586c.464 0 .909.184 1.237.513l2.914 2.914c.329.328.513.773.513 1.237v9.586A1.75 1.75 0 0 1 13.25 16h-9.5A1.75 1.75 0 0 1 2 14.25Zm1.75-.25a.25.25 0 0 0-.25.25v12.5c0 .138.112.25.25.25h9.5a.25.25 0 0 0 .25-.25V6h-2.75A1.75 1.75 0 0 1 9 4.25V1.5Zm6.75.062V4.25c0 .138.112.25.25.25h2.688l-.011-.013-2.914-2.914-.013-.011Z"></path></svg><span>README.md</span></a></p>



# Wiki Hyperlinks

Criado em 20 de junho de 2023 às 19h00 &#x22EE; Atualizado em 21 de junho de 2023 às 12h30


Conteúdos de `Blogs`, `Artigos`, `Posts`, `Tutoriais`, `Projetos` e `Samples` podem pertencer ao mesmo contexto, pora isso este repositório foi criado, para evitar ambiguidades e disponibilizar `Hiperlinks` em um único `Commit` em nível global.

# Histórico

+ 21 jun 2023 - Apply ISS standard
+ 20 jun 2023 - Set a default format
+ 20 jun 2023 - Initial commit

---

[`Blogs`](https://github.com/fabasapro/wikis/blogs) &#x22EE; [`Tutoriais`](https://github.com/fabasapro/wikis/tutorials) &#x22EE; [`Contribuir`](https://github.com/fabasapro/wikilinks/pulls) &#x22EE; [`Termos de Uso`](LICENSE)

<sup><b>Copyright © 2023 Fábio Santos. All rights reserved.</b></sup>

















## Artigo

By FabasaPro for Social<br /><sup>Publicado 19 Jun 2023 8h49 &#x22EE; Atualizado 19 Jun 2023 8h49</sup>

## Sintaxe

Repete um bloco de instruções enquanto uma condição é verdadeira ou até que uma condição se torne verdadeira.</sup>

`DO` [ { `WHILE` | `UNTIL` } _condição_ ]<br />
&nbsp;&nbsp;&nbsp;&nbsp;_bloco-instruções_<br />
`LOOP`<br />

`DO`<br />
&nbsp;&nbsp;&nbsp;&nbsp;_bloco-instruções_<br />
`LOOP` [ { `WHILE` | `UNTIL` } _condição_ ]<br />

A parte da _condição_ é tipo [`Boolean`]() [ { _verdadeiro_ | _falso_ } ]. As expressões **_enquanto i < 10_** ou **_até i > 10_** são avaliadas como [`True`](), diferente de zero, ou [`False`](), igual a zero.

## Exemplo
```basic
Dim i = 0
Do While i < 10 ' enquanto i < 10
    i = i + 1
Loop
```
```basic
Dim i = 0
Do
    i = i + 1
Loop Until i > 10 ' até i > 10
```

## Consulte
- [`Exit`]()
- [`For`...`Next`]()
- [`While`...`Wend`]()

---

[`Blogs`](https://github.com/fabasapro/wikis/blogs) &#x22EE; [`Tutoriais`](https://github.com/fabasapro/wikis/tutorials) &#x22EE; [`Contribuir`](https://github.com/fabasapro/wikilinks/pulls) &#x22EE; [`Termos de Uso`](LICENSE)

<sup><b>Copyright © 1996-2023 Fábio Santos. All rights reserved.</b></sup>


























> ![tip](https://github.com/poitanotalk/resources/blob/main/svg/tools/lightbulb.svg) __Dica__<br />
>
> Codificação HTML
> 
> Quando você exibe o conteúdo em uma página usando o @ caractere, como nos
> exemplos anteriores, ASP.NET HTML codifica a saída. Isso substitui
> caracteres HTML reservados (como < e > ) por códigos que permitem que os
> caracteres sejam exibidos como caracteres em uma página da Web em vez de
> serem interpretados como marcas HTML ou entidades. Sem codificação HTML,
> a saída do código do servidor pode não ser exibida corretamente e pode
> expor uma página a riscos de segurança.
>
> Se sua meta for gerar marcação HTML que renderize marcas como marcação
> (por exemplo `<p></p>` , um parágrafo ou <em></em> para enfatizar o texto),
> consulte a seção Combinando Texto, Marcação e Código em Blocos de Código
> mais adiante neste artigo.
>
> Você pode ler mais sobre codificação HTML no Working with HTML Forms in
> Páginas da Web do ASP.NET Sites.


<blockquote>
    <p>
        <img alt="tip"
             height="16px"
             src="https://github.com/poitanotalk/resources/blob/main/svg/tools/lightbulb.svg"
             width="16px"
             title="blockquote tip" />
        <strong>Dica</strong><br /><br/>
        Codificação HTML<br /><br />
        Quando você exibe o conteúdo em uma página usando o @ caractere, como nos exemplos anteriores, ASP.NET HTML codifica a saída. Isso substitui caracteres HTML reservados (como < e >) por códigos que permitem que os caracteres sejam exibidos como caracteres em uma página da Web em vez de serem interpretados como marcas HTML ou entidades. Sem codificação HTML, a saída do código do servidor pode não ser exibida corretamente e pode expor uma página a riscos de segurança.<br /><br />
        Se sua meta for gerar marcação HTML que renderize marcas como marcação (por exemplo p, um parágrafo ou <em></em> para enfatizar o texto), consulte a seção Combinando Texto, Marcação e Código em Blocos de Código mais adiante neste artigo.<br /> <br />
        Você pode ler mais sobre codificação HTML no Working with HTML Forms in Páginas da Web do ASP.NET Sites.
    </p>
</blockquote>





<a href="" title="external link">External Link <img alt="note" height="16px" src="https://github.com/poitanotalk/resources/blob/main/svg/tools/externallink.svg" width="16px" title="external link" /></a>

[External Link ![externallink](https://github.com/poitanotalk/resources/blob/main/svg/tools/externallink.svg)]()



<table border="0" align="none">
    <caption>Uma tabela é composta de header e data:</caption>
    <tr align="none">
        <th>header 1</th>
        <th>header 2</th>
        <th>header 3</th>
    </tr>
    <tr align="none">
        <td>data 1</td>
        <td>data 2</td>
        <td>data 3</td>
    </tr>
</table>

<table border="0" align="none">
    <caption>Uma tabela é composta de header e data:</caption>
    <tr align="none">
        <th>header 1</th>
        <td>data 2</td>
        <td>data 3</td>
    </tr>
    <tr align="none">
        <th>header 2</th>
        <td>data 2</td>
        <td>data 3</td>
    </tr>
</table>








###### Artigo
__Por FabasaPro Designer__<br />
<sup>Publicado 19 jun 2023 8h49 &#x22EE; Atualizado 19 jun 2023 8h49</sup>

# Wiki

Em [informática](), o __web wiki__ (['wiki'](), do havaiano "super veloz") é um [sistema de gestão de conteúdo]() e também uma [linguagem de marcação]() utilizada em [website]() que contém [hipertexto]() e [hiperligações]() que trabalham com o [software wiki](), no qual vários usuários modificam/editam [colaborativamente]() ao mesmo tempo o seu conteúdo e/ou a estrutura do wiki diretamente usando um [navegador web](), com a ajuda de um [editor de texto enriquecido]().[^1]

O software wiki, é um tipo de sistema de gestão de conteúdo, mas diverge da maioria dos outros tais sistemas quanto a [autoria](), inclusive [software de blog](), em que o conteúdo é criado sem qualquer dono ou líder definido.

Wikis possuem pouca estrutura inerente, que permite a estrutura ser melhorada de acordo com as necessidades dos utilizadores[<sup>[2]</sup>](https://github.com/poitanotalk/resources/tree/main#bibliografia). Há dezenas de diferentes softwares de wiki em uso, tanto autônomos quanto partes de outros [softwares](), como sistemas de rastreio de [bugs](). Alguns softwares de wiki são de [código aberto](), enquanto outros são [proprietários](). Alguns permitem controlo sobre diferentes funções (níveis de acesso); por exemplo, direitos de edição podem permitir alteração, adição ou remoção de material. Outros podem permitir acesso sem forçar controlo de acesso. Outras regras podem ser impostas para organizar conteúdo.[<sup>[3]</sup>](https://github.com/poitanotalk/resources/tree/main#bibliografia)

A enciclopédia [Wikipédia]() não é um único wiki, esta é uma união de centenas de wikis — cada um pertence a uma língua específica. Além da Wikipédia, há [milhares de outros wikis em uso](), tanto públicos quanto privados, inclusive wikis a funcionar como recursos de [gestão do conhecimento](), [ferramenta de notas](), [websites de comunidade]() e [intranets](). A Wikipédia em [língua inglesa]() possui a maior coleção de artigos; em setembro de 2016, possuía mais de cinco milhões de artigos. [Ward Cunningham](), o desenvolvedor do primeiro software wiki, [WikiWikiWeb](), descreveu-o originalmente como «a base de dados online mais simples que poderia possivelmente funcionar».[<sup>[4]</sup>](https://github.com/poitanotalk/resources/tree/main#bibliografia) "[Wiki]()" (pronunciado ['[wiki]()'][^1]) é uma palavra [havaiana]() que significa "rápido".[<sup>[5]</sup>](https://github.com/poitanotalk/resources/tree/main#bibliografia)[<sup>[6]</sup>](https://github.com/poitanotalk/resources/tree/main#bibliografia)[<sup>[7]</sup>](https://github.com/poitanotalk/resources/tree/main#bibliografia) O projeto de enciclopédia online Wikipédia é o website baseado em wiki mais popular e é um dos sites mais amplamente vistos no mundo, tendo sido colocado no “top dez” desde 2007.

Contribua para este repositório via [solicitações de pull &#x27A1;](https://github.com/poitanotalk/source/pulls)

## Etimologia

O termo "wiki" na língua havaiana significa "super veloz", devido a velocidade de criação e atualização das páginas, uma das características que define a tecnologia colaborativa wiki.[<sup>[8]</sup>](https://github.com/poitanotalk/resources/tree/main#bibliografia)

## Principais características

Um __Web Wiki__ permite que os documentos sejam editados colectivamente com uma linguagem de marcação muito simples e eficaz, por meio da utilização de um [navegador web]().[<sup>[9]</sup>](https://github.com/poitanotalk/resources/tree/main#bibliografia) Dado que a grande maioria dos wikis é baseada na web, o termo wiki é normalmente suficiente. Uma única página em um wiki é referida como uma "única página", enquanto o conjunto total de páginas, que estão altamente interligadas, chama-se 'o wiki'.

Uma das características definitivas da tecnologia wiki é a facilidade com que as páginas são criadas e alteradas – geralmente não existe qualquer revisão antes de as modificações serem aceitas, e a maioria dos wikis são abertos a todo o público ou pelo menos a todas as pessoas que têm acesso ao servidor wiki. Nem o registro de usuários é obrigatório em todos os wikis.[carece de fontes]

__Coletividade__
> O que faz o "wiki" tão diferente dos outros sítios da Internet é
> certamente o fato de poder ser editado pelos usuários que por ele navegam.
> Por exemplo, esta parte do artigo foi adicionada anos após a criação do
> próprio, e, com certeza, não será a última edição; ela será modificada por
> usuários e visitantes ao longo do tempo. É possível corrigir erros,
> complementar ideias e inserir novas informações. Assim, o conteúdo de um
> artigo atualiza-se graças à coletividade. Os problemas que se podem
> encontrar em wikis são artigos feitos por pessoas que nem sempre são
> especialistas no assunto, ou até alguns atos de vandalismo, substituindo
> o conteúdo do artigo. Porém, o intuito é, justamente, que a página acabe
> por ser editada por alguém com mais conhecimentos. Está fortemente
> relacionado com o conceito de crowdsourcing.<sup>1</sup>
> Alternativamente existem alguns wikis utilizadas como wikis pessoais.
> 
> <sup>1. SCHENK, Eric; Guittard, Claude (2009). [«Crowdsourcing: What can be
> Outsourced to the Crowd, and Why ?» &#x2B0F;](https://hal.archives-ouvertes.fr/file/index/docid/439256/filename/Crowdsourcing_eng.pdf) (PDF). hal.archives-ouvertes.fr[ligação
> inativa]</sup>

## Página e edição

Em wikis tradicionais, existem 3 (três) representações para cada página: o código [HTML](), a página resultante do código da sua edição pelo web browser, e o código-editado em HTML que o servidor produziu.

O raciocínio por trás desse design é que o [HTML](), com sua enorme biblioteca de [tags](), dificulta uma edição mais rápida. Ele, às vezes, não pode usar toda a sua funcionalidade, como [JavaScript]() e [folhas de estilo](), por causa da consistência da linguagem.

Sintaxe [Mediawiki](https://pt.wikipedia.org/wiki/MediaWiki) |	HTML |	Edição de saída
:---|:---|:---
"''Doutor''? Sem outro título? Um ''sábio''? É justa a autoridade civil?" "Porque, certamente," replica Harddriveing, amigavelmente. "Todos nós sábios sabemos mais ou menos." |`<p>"<i>Doutor</i>? Sem outro título? Um <i>sábio</i>? É justa a autoridade civil?" </p><p>"Porque, certamente," replica Harddriveing, amigavelmente. "Todos nós sábios sabemos mais ou menos."</p>`|"Doutor? Sem outro título? Um sábio? É justa a autoridade civil?" "Porque, certamente," replica Harddriveing, amigavelmente. "Todos nós sábios sabemos mais ou menos."

Alguns mecanismos de edição wiki mais recentes usam um método diferente: suportam a edição "[WYSIWYG]()" ("What You See Is What You Get", que significa basicamente "o que se vê é o que se obtém"), geralmente com o suporte de um controle [ActiveX]() ou um [plug-in] que traduz instruções graficamente introduzidas como "negrito" ou "itálico" nas tags correspondentes de HTML.

Em tais implementações, salvar uma edição corresponde ao envio de uma nova versão HTML da página ao servidor, embora o usuário seja preservado desse detalhe técnico, uma vez que o código é gerado automaticamente, de forma transparente. Usuários que não possuem o plug-in necessário podem, em geral, editar a página do mesmo modo, editando diretamente o texto em código HTML.

As instruções de formatação permitidas por um wiki variam consideravelmente, dependendo do mecanismo wiki utilizado.

Wikis simples permitem apenas a formatação básica, enquanto os mais complexos suportam tabelas, imagens, fórmulas, ou até elementos interativos, como votações e jogos. Por esse motivo, atualmente existe um esforço conjunto para definir um Wiki Markup Standard.[<sup>[10]</sup>](https://github.com/poitanotalk/resources/tree/main#bibliografia)

## Ligando e criando páginas

Wikis são verdadeiras mídias hipertextuais, com estrutura de navegação não linear. Cada página geralmente contém um grande número de ligações para outras páginas. Páginas com navegação hierárquica são frequentemente usadas em grandes wikis, mas não devem ser usadas. As ligações são criadas usando-se uma sintaxe específica, o chamado "padrão link".

Originalmente, a maioria dos wikis usava [CamelCase]() como padrão link, produzido por palavras que começam com letras maiúsculas, sem espaço entre elas (a palavra "CamelCase" é em si um exemplo de CamelCase). Embora o CamelCase faça ligações muito facilmente, também cria ligações que são escritas de uma forma que se desvia da escrita padrão. Wikis baseados em CamelCase são instantaneamente reconhecíveis em um grande número de ligações com nomes como "TableOfContents" e "BeginnerQuestions".

Vale lembrar que, dentro de um universo wiki, não existem dois artigos com 'títulos' repetidos, pois faz parte da filosofia wiki utilizar-se da tecnologia de armazenamento para ajudar a eliminar ambiguidades. Ao mesmo tempo, é bom perceber que o wiki tem a sensibilidade de distinguir letras maiúsculas de minúsculas como distintas para o armazenamento. Além disso, a própria [ambiguidade]() do idioma utilizado pode, facilmente, gerar artigos repetidos, até mesmo com títulos extremamente parecidos, diferenciados apenas pelo [caps]() (inglês para "maiúsculas e minúsculas", observado na maioria dos teclados ocidentais).

## Controle de usuários

A ideia por trás de controlar usuários é diretamente relacionada ao tamanho do [universo]() gerado pelo wiki. Quanto mais pessoas estiverem usando o wiki, menor deveria ser a necessidade de [níveis]() de controle, pois o controle é fornecido pela própria [sociedade](). Mas o controle sempre se faz necessário, em pelo menos dois níveis: gerenciamento e utilização.

Dessa forma, um wiki muito pequeno costuma ter a necessidade de adicionar um controle que impede autores anônimos para evitar [vandalismo](). Por outro lado, a maioria dos wikis públicos, que costumam ser grandes, dispensa qualquer tipo de registro.

De todo modo, muitos dos principais mecanismos wiki (incluindo [MediaWiki](), [MoinMoin](), [UseModWiki]() e [TWiki]()) têm como limitar o acesso à publicação. Alguns mecanismos wiki permitem que usuários sejam banidos do processo de edição pelo bloqueio do seu endereço particular na Internet, o endereço IP, ou, quando disponível, o seu nome de usuário. Ainda assim, muitos provedores de acesso à Internet atribuem endereços IP diferentes para cada usuário registrado, então o banimento de IP pode ser superado facilmente. Para lidar com esse problema, embargos temporários de IP são utilizados ocasionalmente e estendidos a todos os endereços IP dentro de um determinado âmbito, assegurando, deste modo, que um vândalo não consiga editar páginas durante um certo tempo; entende-se que isso seja uma barreira suficiente. Pode, contudo, impedir alguns usuários não problemáticos — que venham do mesmo servidor de acesso à Internet — de utilizar o serviço durante o período de embargo.

Uma defesa comum contra vândalos persistentes é deixá-los desfigurar tantas páginas quanto desejarem, sabendo que podem ser facilmente rastreadas e revertidas depois que o vândalo saia. Essa política pode revelar-se pouco prática, no entanto, face a sistemáticas fraudes resultantes de raiva ou frustração.

Como uma medida de emergência, alguns wikis permitem que o banco de dados seja alterado para o modo apenas-leitura, enquanto outros adotam uma política em que apenas usuários que tenham sido registrados antes de algum corte arbitrário possam editar. Em geral, qualquer prejuízo infligido por um "vândalo" pode ser revertido rápida e facilmente. Mais problemáticos são os erros sutis que passam despercebidos, como a alteração de datas de lançamento de álbuns e discografias na Wikipedia.

## Exemplos

Para demonstrar como o wiki essencialmente precisa de somente dois níveis de controle, podem ser traçados alguns paralelos dentre as três áreas de estudos científicos (exatas, biológicas e humanas), o que facilita a visualização.

Um paralelo com o funcionamento de um computador simples, como uma calculadora, por exemplo, pode-se imaginar o wiki como o próprio computador e o processador que executa o controle, enquanto o resto da calculadora a mantém funcionando, fornecendo entradas e saídas de dados em dois dispositivos diferenciados para o processador.

Análogo ao funcionamento de uma célula viva, pode-se imaginar o wiki como sendo a própria célula e o núcleo faz o gerenciamento de tudo que acontece dentro, enquanto o resto da célula, o núcleo inclusive, se utiliza dos recursos disponibilizados através da membrana externa ([membrana plasmática]()) entre outros componentes da célula que executam múltiplas funções para mantê-la [viva]().

Comparado com o funcionamento de uma sociedade, pode-se imaginar o wiki como sendo a própria sociedade e o núcleo seria o governo, que cria a quantidade de regras que forem sendo necessárias para manter a sociedade funcionando com base na vida e dentro das possibilidades oferecidas pela própria sociedade e pelo [ecossistema]().

No ambiente da Educação Corporativa, diversas organizações estão utilizando esta tecnologia, como por exemplo, o [Banco do Brasil]() e sua Universidade Corporativa utilizam em larga escala a Tecnologia Wiki.

## Ver também
* [Bliki]()
* [Comparação de softwares wiki]()
* [Lista de softwares wikis]()
* [Software social]()

## Referências
<sup>` 1.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) [«wiki» &#x2B0F;](), Encyclopædia Britannica, 1, London: Encyclopædia Britannica, Inc., 2007, consultado em 27 de janeiro de 2018, cópia arquivada em 24 de abril de 2008</sup><br />
<sup>` 2.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) Mitchell, Scott (julho de 2008), Easy Wiki Hosting, Scott Hanselman's blog, and Snagging Screens, MSDN Magazine, consultado em 9 de março de 2010, cópia arquivada em 16 de março de 2010</sup><br />
<sup>` 3.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) Alexa Top Sites, consultado em 1 de dezembro de 2016, cópia arquivada em 2 de março de 2015</sup><br />
<sup>` 4.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) Cunningham, Ward (27 de junho de 2002), What is a Wiki, WikiWikiWeb, consultado em 10 de abril de 2008, cópia arquivada em 16 de abril de 2008</sup><br />
<sup>` 5.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) mauimapp.com. Hawaiian Words; Hawaiian to English [archived 14 de setembro de 2008; citado em 19 de setembro de 2008].</sup><br />
<sup>` 6.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) Hasan, Heather (2012), Wikipedia, 3.5 million articles and counting, ISBN 9781448855575, p. 11</sup><br />
<sup>` 7.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) Andrews, Lorrin (1865), A dictionary of the Hawaiian language to which is appended an English-Hawaiian vocabulary and a chronological table of remarkable events, Henry M. Whitney, p. 514</sup><br />
<sup>` 8.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) «wiki wiki - Tradução em português». Dicionário Linguee. Consultado em 29 de dezembro de 2022</sup><br />
<sup>` 9.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) Barrett, Daniel J (2009). MediaWiki. Sebastopol, CA: O´Reily. ISBN 978-0-596-51979-7</sup><br />
<sup>`10.`[&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) «Meatball Wiki: WikiMarkupStandard». meatballwiki.org. Consultado em 29 de maio de 2022</sup><br />

## Bibliografia
<ul>
    <li><sup>Aigrain, Philippe (2000). The Individual and the Collective in Open Information Communities. Invited talk at the 16th Bled Electronic Commerce Conference, Bled, Slovenija, 11 de Junho de 2003. Disponível em: http://www.ufrgs.br/limc/escritacoletiva/pdf/indiv_and_collective.pdf</sup></li>
    <li><sup>Aronsson, Lars (2002). Operation of a Large Scale, General Purpose Wiki Website: Experience from susning.nu's first nine months in service. Paper presented at the 6th International ICCC/IFIP Conference on Electronic Publishing, 6 - 8 de Novembro, 2002, Karlovy Vary, Czech Republic. Disponível em: https://web.archive.org/web/20130724101737/http://aronsson.se/wikipaper.html</sup></li>
    <li><sup>Benkler, Yochai (2002). Coase's penguin, or, Linux and The Nature of the Firm. The Yale Law Jounal. v.112, n.3, pp.369-446.</sup></li>
    <li><sup>Cunningham, Ward and Leuf, Bo (2001): The Wiki Way. Quick Collaboration on the Web. Addison-Wesley, ISBN 0-201-71499-X.</sup></li>
    <li><sup>Delacroix, Jérôme (2005): Les wikis, espaces de l'intelligence collective M2 Editions, Paris, ISBN 2-9520514-4-5. Website: http://www.leswikis.com</sup></li>
    <li><sup>Jansson, Kurt (2002): "Wikipedia. Die Freie Enzyklopädie." Lecture at the 19th Chaos Communications Congress (19C3), 27 de Dezembro, Berlim. Descrição online: http://de.wikipedia.org/wiki/Benutzer:Kurt_Jansson/Vortrag_auf_dem_19C3</sup></li>
    <li><sup>Möller, Erik (2003). Loud and clear: How Internet media can work. Presentation at Open Cultures conference, June 5 - 6, Vienna. Disponível em: https://web.archive.org/web/20031012082345/http://opencultures.t0.or.at/oc/participants/moeller</sup></li>
    <li><sup>Möller, Erik (2003). Tanz der Gehirne. Telepolis, May 9-30. Quatro partes: "Das Wiki-Prinzip", "Alle gegen Brockhaus", "Diderots Traumtagebuch", "Diesen Artikel bearbeiten"</sup></li>
    <li><sup>Nakisa, Ramin (2003). "Wiki Wiki Wah Wah". Linux User and Developer v.29, pp.42-48. Disponível em: http://194.73.118.134/lud29-Collaborative_Software-Wiki.pdf[ligação inativa]</sup></li>
    <li><sup>Remy, Melanie. (2002). Wikipedia: The Free Encyclopedia. Online Information Review. v.26, n.6, pp.434.</sup></li>
</ul>
    
## Ligações externas
<sup>` – ` «How did you come up with the idea for the Wiki?» (em inglês). Uma entrevista em vídeo com Ward Cunningham sobre como ele teve a ideia do Wiki</sup><br />

# ABCDEF

test HEX text

[^1]: [&uarr;](https://github.com/poitanotalk/resources/tree/main#wiki) A pronúncia do fonema havaiano /w/ varia entre [w] e [v], e a pronúncia do fonema /k/ varia entre [k] e [t], entre outras. Assim, a pronúncia da palavra havaiana wiki varia entre ['wiki'], ['witi'], ['viki'], e ['viti'].















