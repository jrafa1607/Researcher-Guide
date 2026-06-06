### 📑 Guia para Registro de Software no INPI

Este guia descreve um passo a passo para realizar o registro de programas de computador junto ao Instituto Nacional da Propriedade Industrial (**INPI**). 
Este respositório serve como um mapa de referência para pesquisadores gerarem hashes, formatarem a documentação e navegarem pelos portais federais.
Este procedimento foi desenvolvido buscando facilitar e orientar o processo de Registro de Software. 
Todo o procedimento é baseado no **[Manual para Registro de Software](https://www.gov.br/inpi/pt-br/servicos/programas-de-computador/programa-de-computador-manual-completo)**.

---

### Pré-requisitos e Portais Necessários

Antes de iniciar o processo, certifique-se de possuir cadastro ativo nas seguintes plataformas do governo federal:

* **[Conta Gov.br](https://sso.acesso.gov.br/)**: Conta de Pessoa física ou jurídica, com nével **Prata** ou **Ouro**.
* **[Portal e-INPI](https://busca.inpi.gov.br/pePI/)**: Sistema principal para gerar guias de recolhimento, peticionamentos e acompanhar o status do registro.

---

### Geração do Hash Criptográfico (Resumo Digital)

O INPI não armazena o código-fonte legível do software que se deseja registrar. 
Para garantir a segurança da informação do software, você deve gerar um **Valor Hash ( Preferencialmente, com o Algoritmo SHA-256 )** do código-fonte. 
Para isso, Compacte todo o diretório do seu código-fonte em um único arquivo (ex: `codigo_fonte.zip` ou `codigo_fonte.tar.gz`). 
Abra o terminal do seu sistema operacional e execute o comando correspondente para extrair a chave de 64 caracteres:

```bash
# No Linux / macOS
shasum -a 256 codigo_fonte.zip

# No Windows (PowerShell)
Get-FileHash codigo_fonte.zip -Algorithm SHA256
```

Concluída a geração do Hash, **Copie o Valor** gerado e **guarde-o** em um local seguro. 
Este valor será utilizado no formulário do INPI posteriormente no preenchimento do Formulário Eletrônico.

---

### Emissão e Pagamento da GRU (Guia de Recolhimento da União)

Todo registro de software possui uma taxa federal obrigatória que deve ser paga antes da abertura do pedido.
Esta taxa é chamada **Guia de Recolhimento da União (GRU)**.
Para realizar o pagamento, siga os seguintes passos:

1. Acesse o **[Sistema de Emissão de GRU do INPI](https://meu.inpi.gov.br/pag/)**.
2. Faça o login com suas credenciais do e-INPI / Gov.br.
3. No campo **Tipo de Serviço:**, escolha *Registro de Programas de Computador*
4. No campo **Serviço:**, escolha *Pedido de registro de programa de computador (Código do Serviço: **730**)*
5. Faça o **Download da GRU (Gerar Boleto)**.
6. Realize o **Pagamento da GRU**.
7. Guarde as seguintes informações: **Comprovante de Pagamento** e o **Número da GRU**

---

### Preenchimento do Formulário Eletrônico (e-Software)

O sistema do INPI pode levar de 24 a 48 horas úteis para compensar o pagamento e liberar o formulário.
Com a GRU compensada pelo banco, o formulário de peticionamento estará desbloqueado. Sendo assim, basta seguir os seguintes passos:

1. Acesse o Sistema de Peticionamento Eletrônico: **[e-Software](https://gru.inpi.gov.br/peticionamentoeletronico/)**.
2. Insira o número da GRU paga para iniciar o preenchimento da petição.
3. Insira as informações técnicas solicitadas:
* **Título do Software:** Nome oficial do programa de computador.
* **Linguagem de Programação:** As linguagens utilizadas no desenvolvimento.
* **Data de Criação:** Data em que o software se tornou funcional.
* **Campo de Aplicação:** Categorize o escopo do software com base na tabela internacional fornecida pelo próprio INPI.
* **Resumo Digital (Hash):** Cole exatamente a chave **SHA-256** obtida no *Passo 1*.

```
+-----------------------------------------------------------------+
|                        Portal e-Software                        |
+-----------------------------------------------------------------+
|                                                                 |
|  Número da GRU: [ 2026XXXXXXXXX ] -> [ VALIDADA ]               |
|                                                                 |
|  Título do Software: [ Nome do Seu App ]                         |
|  Linguagem: [ Python / TypeScript ]                             |
|                                                                 |
|  Resumo Digital (SHA-256):                                      |
|  [ a591a6d40bf420404a01173cfb7a1200150931d871e... ]             |
|                                                                 |
+-----------------------------------------------------------------+

```

*Figura 1: Representação conceitual do formulário de dados no sistema e-Software.*

---

### Assinatura da Declaração de Veracidade (DTD)

O último requisito é anexar a *Declaração de Veracidade Ideológica e Especificação Técnica (DTD)* assinada digitalmente. 

1. O próprio sistema e-Software gerará um arquivo PDF contendo o resumo dos dados declarados e o valor hash SHA-256.
2. Faça o download do PDF gerado pelo e-Software.
3. Acesse o **[Assinador Digital do Gov.br](https://assinador.iti.br/assinatura/index.xhtml)**.
4. Faça o upload do PDF da DTD e realize a assinatura digital utilizando sua conta Prata ou Ouro.
5. Faça o download do documento assinado (ele conterá o manifesto de assinatura do Gov.br ao final).
6. **(Opcional)** Valide o documento assinado no **[Serviço de Validação de Assinaturas Eletrônicas](https://validar.iti.gov.br/)**
7. Retorne à página do e-Software, faça o upload do PDF assinado e clique em **Protocolar Pedido**.

---

### Acompanhamento e Emissão do Certificado

Após o protocolo bem-sucedido, o processo é automatizado. O registro costuma ser publicado na **[RPI (Revista da Propriedade Industrial)](https://revistas.inpi.gov.br/rpi/)** em um prazo médio de **7 a 10 dias**.
É possível acompanhar a publicação pesquisando pelo seu nome, nome do software ou número de protocolo diretamente no **[Portal de Busca do INPI](https://busca.inpi.gov.br/pePI/)**. <br><br>
Assim que o status constar como "Concedido", o **Certificado de Registro de Programa de Computador** ficará disponível para download em formato PDF.
Em caso de dúvidas, é possível entrar em contato com o INPI pela Página do **[Fale Conosco](https://faleconosco.inpi.gov.br/faleconosco/)**.

---

### ⚖️ Aviso Legal

*Este repositório é um guia técnico de referência simplificado. 
Ele não substitui as consultas aos manuais normativos e as diretrizes atualizadas fornecidas pelo 
portal oficial do [Ministério do Desenvolvimento, Indústria, Comércio e Serviços / INPI](https://www.google.com/search?q=https%3A%2F%2Fwww.gov.br%2Finpi%2F).*
