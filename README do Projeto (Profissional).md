<div align="center">

# 💰 Finanças Acessíveis com IA

**Gerenciador financeiro pessoal inclusivo, inteligente e guiado por voz e visão computacional.**  
*Desenvolvido para proporcionar autonomia, dignidade e controle financeiro a todas as pessoas, com foco em acessibilidade universal (WCAG 2.1 AA), baixa visão, idosos e autônomos.*

<br/>

[![Status](https://img.shields.io/badge/Status-Pronto%20para%20Produ%C3%A7%C3%A3o-10b981?style=for-the-badge&logo=checkmarx&logoColor=white)](https://github.com)
[![Acessibilidade](https://img.shields.io/badge/Acessibilidade-WCAG%202.1%20AA-0ea5e9?style=for-the-badge&logo=w3c&logoColor=white)](https://www.w3.org/WAI/standards-guidelines/wcag/)
[![Google Gemini](https://img.shields.io/badge/IA-Gemini%203%20Flash-8b5cf6?style=for-the-badge&logo=googlegemini&logoColor=white)](https://ai.google.dev/)
[![Licença](https://img.shields.io/badge/Licen%C3%A7a-MIT-f59e0b?style=for-the-badge)](LICENSE)

<br/>

[✨ Funcionalidades](#-funcionalidades-principais) •
[♿ Acessibilidade](#-suite-de-acessibilidade-wcag-21-aa) •
[📸 Câmera & IA](#-scanner-de-recibos-e-boletos-com-visão-ia) •
[🚀 Como Rodar](#-como-executar-o-projeto) •
[🌐 Publicação no GitHub Pages](#-publicação-no-github-pages)

---

</div>

## 📌 Visão Geral

O **Finanças Acessíveis com IA** é uma aplicação web progressiva (*Single-File Architecture*) desenvolvida para eliminar as barreiras de complexidade presentes na maioria dos aplicativos bancários e planilhas financeiras tradicionais. 

Ao combinar **síntese e reconhecimento de voz nativos**, **leitura inteligente de comprovantes por câmera** e **assistência financeira orientada pelo Google Gemini**, o projeto garante que qualquer usuário — independentemente de limitações visuais, motoras ou de letramento digital — consiga gerenciar suas entradas e despesas com total independência e privacidade.

---

## ✨ Funcionalidades Principais

| Recurso | Descrição | Tecnologia |
| :--- | :--- | :--- |
| **👋 Onboarding Neutro e Seguro** | Começa com conta zerada (`R$ 0,00`). Cada pessoa digita seu nome e tem seus dados armazenados com total privacidade no próprio dispositivo. | `localStorage` API |
| **🎙️ Registro por Voz Natural** | Permite cadastrar ganhos ou gastos falando frases coloquiais (*ex: "Gastei 32 reais no almoço"*). O app extrai o valor, a categoria e a data automaticamente. | Web Speech API |
| **📸 Scanner de Recibos & Boletos** | Abre a câmera ao vivo com guia de enquadramento, tira foto de cupons ou contas e identifica os dados com visão computacional. | `getUserMedia` + Gemini Vision |
| **🤖 Consultor Gemini em Tempo Real** | Assistente de inteligência artificial que audita seus hábitos de consumo, sugere cortes de gastos e responde dúvidas sobre dívidas e reservas. | Gemini 3 Flash |
| **📊 Painel & Metas 50/30/20** | Visualização de despesas em barras percentuais por categoria, controle de reserva financeira e modelo de alocação de renda. | Vanilla CSS & JS |
| **👁️ Modo Privacidade** | Oculta saldos e valores da tela (`••••••••`) com um toque para uso seguro em locais públicos ou transporte coletivo. | State Management |

---

## ♿ Suíte de Acessibilidade (WCAG 2.1 AA)

Desenvolvido com foco rigoroso em inclusão e usabilidade assistiva:

1. **Leitura de Tela Integrada (Text-to-Speech)**:
   - Botão **`🔊 Ler Tela`**: Lê o saldo geral, total de receitas e saídas com sintetização de voz em português brasileiro (`pt-BR`).
   - Leitura automática de confirmação para todas as transações inseridas ou excluídas.
   - Botão para ouvir a divisão de gastos por categorias e as dicas do consultor.
2. **Alto Contraste Imediato**:
   - Modo de alto contraste com fundo preto puro (`#000000`), bordas nítidas de alta visibilidade e cores de alto destaque com conformidade de contraste para daltonismo e baixa visão.
3. **Escala de Texto Dinâmica**:
   - Botões `A+` e `A-` para ampliar ou reduzir os tamanhos de fonte em quatro níveis tipográficos sem quebrar o layout da interface.
4. **Feedback Auditivo Polifônico (Web Audio API)**:
   - Sons sintetizados em tempo real para confirmação de ações, cliques e exclusão de itens, permitindo navegação sem depender de recursos visuais.
5. **Navegação Semântica & ARIA**:
   - Estrutura baseada em tags semânticas (`<header>`, `<main>`, `<section>`, `<nav>`), além de atributos `aria-label`, `role="dialog"` e estados de foco para navegação por teclado e leitores de tela externos (TalkBack, VoiceOver, NVDA).

---

## 📸 Scanner de Recibos e Boletos com Visão IA

O sistema integra a câmera do aparelho diretamente com a API do Gemini:

```
[ Usuário aponta a câmera ] 
          ↓
[ Captura do comprovante ou boleto via canvas ]
          ↓
[ Processamento multimodal com o Gemini 3 Flash ]
          ↓
[ Extração automática: Estabelecimento + Valor R$ + Categoria ]
          ↓
[ Leitura em voz alta e confirmação no extrato ]
```

* **Câmera ao Vivo**: Permite enquadrar o documento na tela com linhas guia e alternar entre câmera frontal e traseira (`🔄 Virar`).
* **Upload da Galeria**: Compatível com fotos já tiradas de recibos ou capturas de tela de comprovantes Pix.
* **Laser de Escaneamento**: Indicador visual e sonoro de leitura durante a análise da imagem.

---

## 🤖 Comandos de Voz Suportados

O analisador de linguagem natural interpreta diversos formatos cotidianos:

```text
• "Gastei 55 reais no supermercado"      ➔ Despesa de R$ 55,00 em Alimentação
• "Recebi 400 reais de comissão"        ➔ Receita de R$ 400,00 em Receita
• "Paguei 95 reais de gasolina no posto" ➔ Despesa de R$ 95,00 em Transporte
• "Comprei 38 reais de remédio"          ➔ Despesa de R$ 38,00 em Saúde
• "Paguei a conta de luz de 180 reais"   ➔ Despesa de R$ 180,00 em Moradia & Contas
```

---

## 🛠️ Tecnologias Utilizadas

* **Linguagem Principal**: HTML5 Semântico, CSS3 Moderno e JavaScript Vanilla (ES6+)
* **Estilização**: [Tailwind CSS CDN](https://tailwindcss.com/)
* **Inteligência Artificial**: [Google Gemini API](https://ai.google.dev/) (`gemini-3-flash-preview`)
* **Áudio e Voz**:
  * Web Speech Recognition API (Entrada por voz)
  * Web Speech Synthesis API (Leitura em áudio de tela)
  * Web Audio API (Sintetizador de tons sonoros)
* **Mídia e Câmera**: MediaDevices API (`navigator.mediaDevices.getUserMedia`) e Canvas HTML5
* **Armazenamento**: LocalStorage API (Armazenamento 100% privado no lado do cliente)

---

## 🚀 Como Executar o Projeto

Como o aplicativo foi construído em arquitetura autossuficiente de arquivo único, **você não precisa instalar Node.js, dependências ou servidores pesados**.

### 1. Clonar o Repositório
```bash
git clone https://github.com/SEU-USUARIO/financas-acessiveis-ia.git
cd financas-acessiveis-ia
```

### 2. Abrir no Navegador
* Dê um duplo clique no arquivo `index.html`, **ou**
* Utilize a extensão **Live Server** no VS Code, **ou**
* Execute com um servidor HTTP simples:
```bash
# Com Python 3
python -m http.server 8000

# Ou com npx
npx serve .
```

Acesse no seu navegador: `http://localhost:8000`

---

## 🌐 Publicação no GitHub Pages

Para hospedar seu aplicativo gratuitamente e gerar um link compartilhável:

1. No seu repositório no GitHub, clique na aba **Settings** (Configurações).
2. No menu lateral esquerdo, selecione **Pages**.
3. Em **Branch**, selecione `main` (ou `master`) e mantenha a pasta em `/(root)`.
4. Clique em **Save**.
5. Em instantes, seu aplicativo estará no ar pelo endereço:  
   `https://SEU-USUARIO.github.io/financas-acessiveis-ia/`

---

## 🔒 Privacidade e Segurança dos Dados

* **Armazenamento 100% Local**: Os registros financeiros de cada pessoa são gravados exclusivamente no `localStorage` do seu próprio navegador.
* **Isolamento de Usuários**: Nenhuma informação financeira é enviada a bancos de dados externos compartilhados. Ao abrir em outro dispositivo, a conta inicia zerada para o novo usuário.
* **Segurança de API**: As requisições de inteligência artificial transmitem unicamente o contexto estritamente necessário para gerar as respostas personalizadas.

---

## 📂 Estrutura de Arquivos

```text
financas-acessiveis-ia/
├── index.html                     # Código completo da aplicação (UI, Acessibilidade e Scripts)
├── README.md                      # Documentação completa do projeto
├── COMO_SUBIR_PARA_O_GITHUB.md    # Guia prático de implantação e versionamento Git
└── LICENSE                        # Licença MIT de código aberto
```

---

## 📄 Licença

Este projeto está sob os termos da licença [MIT](LICENSE). Você é livre para usar, estudar, modificar e distribuir este software.

---

<div align="center">

Desenvolvido com dedicação para promover **Inclusão, Acessibilidade e Autonomia Financeira** 💚

</div>