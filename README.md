Este projeto combina HTML, CSS e JavaScript para construir uma calculadora funcional com teclado, sons e botões personalizados. A estrutura geral funciona, mas existem repetições, conflitos e excesso de código que precisam ser limpos. Aqui está um resumo completo de tudo o que foi utilizado.

1. HTML – Estrutura da Interface

A interface foi construída com:

 Um contêiner principal .calculator

Ele centraliza todo o conteúdo e define o layout geral.

 Um display

Responsável por mostrar números e resultados.

 Uma grade com 4 colunas

Essa grade organiza todos os botões da calculadora.

 Botões independentes

Cada botão tem:

um id único (ex: tecla1, operadorAdicionar, igual)

a classe .btn

classes adicionais para estilização por imagem (ex: .n1, .add, .back)

O HTML está bem estruturado e funcional.

2. CSS – Estilo e Imagens

O CSS fornece toda a aparência visual. Ele usa:

Reset global

Remove margens e paddings, padronizando o layout.

 Layout da calculadora

Display escuro com texto branco

Caixas arredondadas

Sombras

Grid responsivo

Botões com imagens usando o pseudo-elemento ::before

Cada botão tem uma imagem aplicada assim:

.btn::before {
    background-image: url("img/imagem X.jpg");
}


Isso permite:

imagem no fundo

número ou símbolo por cima

opacidade ajustada

efeito visual moderno

Foram aplicadas imagens para:

todos os números (0–9)

todos os operadores (+, –, *, /)

igual, decimal, inverter

CE, C e Backspace

Imagem de fundo na página

A página usa:

body {
    background-image: url('img/capa 1.jpg');
}

 Problemas encontrados no CSS

Várias repetições de body { … }

Várias repetições de .btn::before com valores diferentes

Reset duplicado

Regras conflitantes

O CSS funciona, mas não está limpo. Precisa ser unificado.

3. JavaScript – Lógica da Calculadora

O JS contém toda a lógica funcional.

Captura de números e operadores

Usa querySelectorAll para vincular eventos aos botões.

 Controle interno

Variáveis importantes:

novoNumero

operador

numeroAnterior

 Sistema de cálculo

Usa:

eval(`${numeroAnterior}${operador}${numeroAtual}`);


Apesar de funcionar, não é a melhor prática.

 Formatação brasileira

Os números são exibidos com vírgula usando:

toLocaleString('BR')

 Funções adicionais

CE (limpa display)

C (limpa tudo)

Backspace

Inverter sinal

Decimal com vírgula

Igual

Mapeamento completo do teclado

Todas as teclas relevantes do teclado físico controlam a calculadora:

números

operadores

Enter

Backspace

C e Esc

Isso torna a calculadora muito mais profissional.

4. Sons nos botões

Você implementou som ao clicar em qualquer botão usando:

const clickSound = new Audio('click.mp3');


E adicionando evento em todos os .btn.

O som reinicia sempre que clicado graças ao:

clickSound.currentTime = 0;

 CONCLUSÃO GERAL

Você usou:

✔ HTML para montar toda a estrutura
✔ CSS para criar um visual com imagens nos botões e fundo personalizado
✔ JavaScript para toda a lógica da calculadora
✔ Mapeamento do teclado
✔ Sistema de som
✔ Formatação brasileira
✔ Funções avançadas como backspace, inverter sinal e decimal
 Mas também deixou:
