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

_access_ [opcional]

   + **`Public`** A palavra-chave `Público` na instrução de declaração especifica que o elemento pode ser acessado a partir do código em qualquer lugar do mesmo projeto, em outros projetos que referenciam o projeto e em qualquer assembly criado a partir do projeto.
   + **`Protected`** A palavra-chave `Protected` na instrução de declaração especifica que o elemento só pode ser acessado de dentro da mesma classe ou de uma classe derivada dessa classe.
   + **`Friend`** A palavra-chave `Friend` na instrução de declaração especifica que o elemento pode ser acessado no mesmo assembly, mas não de fora do assembly.
   + **`Private`** A palavra-chave `Private` na instrução de declaração especifica que o elemento só pode ser acessado no mesmo módulo, classe ou estrutura.
   + **`Protected Friend`** A combinação de palavras-chave `Protected Friend` na instrução de declaração especifica que o elemento pode ser acessado nas classes derivadas, no mesmo assembly ou em ambos.
   + **`Private Protected`** A combinação de palavras-chave `Private Protected` na instrução de declaração especifica que o elemento só pode ser acessado na mesma classe, bem como nas classes derivadas encontradas no mesmo assembly que a classe relativa.

_`type`_

+ **`object`** 32-bits ou 64-bits sendo possível armazenar qualquer tipo em uma variável do tipo Object
+ **`bool`** 1-bit  (2^1), com sinal (0) [ true | false ], depende da implementação da plataforma
+ **`sbyte`** 8-bits ((2^8)/2)-1, com sinal (-128 a 127) 
+ **`byte`** 8-bits (2^8)-1, sem sinal (0 a 255)
+ **`char`** 16-bits (2^16)-1, sem sinal (0 a 65535) sintaxe 'A' e não "A"
+ **`short`** 16-bits ((2^16)/2)-1, com sinal (-32768 a 32767 ), **System.Int16**
+ **`ushort`** 16-bits (2^16)-1, sem sinal (0 a 65535) **System.UInt16**, **`WORD`**
+ **`[int]`** 32-bits ((2^16)/2)-1, com sinal (-2147483648 a 2147483647 ) **System.Int32**
+ **`uint`** 32-bits (2^32)-1, sem sinal (0 a 4294967295) **System.UInt32**, DoubleWORD (**`DWORD`**)
+ **`long`** 64-bits ((2^64)/2)-1, com sinal (-9223372036854775808L a 9223372036854775807L) **System.Int64**
   + _Sufixo literal L ou l para diferir do padrão **`int`**._
+ **`ulong`** 64-bits (2^64)-1, sem sinal (0L a 18446744073709551615L) **System.UInt64**
   + _Sufixo literal L ou l para diferir do padrão **`int`**._
+ **`float`** 32-bits, FLOAT, -1.175494351E-38F a 3.402823466E+38F **System.Single**
   + Sufixo literal F ou f para diferir do valor do padrão racional **`double`**
+ **`[double]`** 64-bits, DoubleFLOAT, -2.2250738585072014E-308 a 1.7976931348623158E+308 **System.Double**
+ **`decimal`** 96-bits  int/float (-79228162514264337593543950335M a 79228162514264337593543950335M) **System.Decimal**
   + _Sufixo literal M ou m para distinguir-se dos anteriores._
+ **`string`** 2 bilhões de caracteres Unicode
   + _Prefixo literal @ (verbatim) ignorar comandos, apenas string.
   + _Prefixo literal $ (interpolate) converter {variáveis} e comandos \x0041 em string.

_name_

+ Um nome válido para descrever procedimentos, tipos de dados ou objetos.

_value_

+ Um valor de atribuição para dados char 'a', string "a", números 123 ou até mesmo objeto.

