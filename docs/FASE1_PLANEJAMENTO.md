# 📋 Documento de Planejamento e Arquitetura do Sistema

> 📥 **Download da Versão Oficial:** [Clique aqui para baixar o PDF completo em formato oficial](Documento_Fase1_Planejamento.pdf)

---

**Projeto:** Sistema de Gerenciamento e Vendas para Loja de Roupas (Cyber Y2K / Dark Streetwear)  
**Responsável:** Luiz  

---

## 1. Atores do Sistema
* **Administrador / Lojista:** Acessa o painel restrito para gerenciar produtos, estoque, categorias e visualizar relatórios de vendas.
* **Cliente / Usuário:** Navega pela loja, filtra produtos por tamanho e cor, adiciona itens ao carrinho e realiza a simulação da compra.

---

## 2. Regras de Negócio (RN)
* **RN01 – Controle Estrito de Estoque:** O sistema não permite que o cliente adicione ao carrinho uma quantidade superior à disponível em estoque para determinado tamanho e cor.
* **RN02 – Baixa Automática de Estoque:** Ao finalizar um pedido, a quantidade dos itens comprados deve ser subtraída automaticamente do saldo em estoque.
* **RN03 – Totalização do Pedido:** O valor total do pedido é calculated automaticamente multiplicando a quantidade de cada item pelo seu preço unitário e somando os subtotais.

---

## 3. Definição do Escopo

### 3.1 Dentro do Escopo (Funcionalidades Incluídas)
* Cadastro, edição, listagem e remoção de produtos (CRUD).
* Atributos específicos de vestuário: Categoria, Tamanho (P, M, G, GG), Cor, Preço e Imagem do produto.
* Controle de saldo de estoque individual por variação de produto.
* Vitrine virtual de produtos com filtro por categoria e campo de busca.
* Carrinho de compras dinâmico e fluxo de checkout simulado.
* Autenticação de usuários (Login/Senha) para Administrador e Cliente.
* Painel administrativo com histórico de vendas e pedidos realizados.

### 3.2 Fora do Escopo (Funcionalidades Não Incluídas nesta Versão)
* Processamento real de pagamentos via Gateway de cartão de crédito ou Pix.
* Integração direta com APIs de transportadoras para cálculo de frete em tempo real.
* Emissão de Nota Fiscal Eletrônica (NF-e).
* Desenvolvimento de aplicações nativas iOS/Android (foco exclusivo em Web Responsiva).

---

## 4. Requisitos do Sistema

### 4.1 Requisitos Funcionais (RF)
| Código | Descrição | Ator |
| :--- | :--- | :--- |
| **RF01** | O sistema deve permitir o cadastro de roupas informando nome, descrição, preço, categoria, tamanho, cor e estoque. | Administrador |
| **RF02** | O sistema deve permitir alterar os dados ou excluir os produtos do catálogo. | Administrador |
| **RF03** | O sistema deve listar os produtos na vitrine principal com opções de filtro por categoria e busca por nome. | Cliente / Admin |
| **RF04** | O sistema deve permitir ao cliente selecionar tamanhos/cores e adicionar produtos ao carrinho de compras. | Cliente |
| **RF05** | O sistema deve permitir a alteração de quantidades e remoção de itens dentro do carrinho. | Cliente |
| **RF06** | O sistema deve realizar a simulação de checkout e registrar o pedido concluído no banco de dados. | Cliente |
| **RF07** | O sistema deve atualizar automaticamente a quantidade do estoque após a confirmação do pedido. | Sistema |
| **RF08** | O sistema deve exigir autenticação por e-mail e senha para acesso às funcionalidades administrativas. | Administrador |
| **RF09** | O sistema deve exibir um relatório resumido contendo o histórico das vendas efetuadas. | Administrador |

### 4.2 Requisitos Não Funcionais (RNF)
| Código | Categoria | Descrição |
| :--- | :--- | :--- |
| **RNF01** | Responsividade | A interface do sistema deve adaptar-se automaticamente a telas de computadores, tablets e smartphones. |
| **RNF02** | Desempenho | O tempo de resposta para carregamento das páginas e consulta ao catálogo deve ser inferior a 2 segundos. |
| **RNF03** | Segurança | As credenciais de acesso (senhas) devem ser armazenadas utilizando algoritmos de criptografia hash no banco de dados. |
| **RNF04** | Usabilidade | O fluxo de compra, da seleção do produto até a finalização do pedido, não deve ultrapassar 3 telas. |

---

## 5. Arquitetura Técnica e Escolha da Stack

### 5.1 Tecnologias Utilizadas (Tech Stack)
* **Linguagem Principal:** TypeScript (JavaScript)
* **Front-end / Framework:** React / Next.js
* **Estilização / UI:** Tailwind CSS + HTML5 / CSS3
* **Back-end & Banco de Dados:** Node.js + PostgreSQL (via Supabase)
* **Autenticação:** JWT / Supabase Auth
* **Prototipagem:** Figma

### 5.2 Visão da Arquitetura do Sistema
**Arquitetura em 3 Camadas:**

1. **Camada de Apresentação (Front-end):** Interface visual onde o usuário interage com a loja e o painel de administração (HTML5, CSS3, Tailwind CSS, React / Next.js).
2. **Camada de Comunicação (API REST / HTTP):** Responsável por transmitir os dados entre a interface e o servidor de forma padronizada.
3. **Camada de Negócio e Dados (Back-end e Banco de Dados):** Executa o processamento das regras de negócio (como baixa de estoque e validação de login) e armazena os dados no PostgreSQL (Node.js / Supabase).
