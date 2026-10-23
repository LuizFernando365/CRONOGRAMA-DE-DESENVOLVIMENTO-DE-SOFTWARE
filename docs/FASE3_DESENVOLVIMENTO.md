# ⚙️ Documento de Desenvolvimento, Integração e Homologação (Fase 3)

> 📥 **Download da Versão Oficial:** [Clique aqui para baixar o PDF completo da Fase 3](Documento_Fase3_Desenvolvimento.pdf)  
> 🌐 **Ambiente de Homologação (Site Online):** [Acessar Loja Cyber Y2K Live](https://criar-loja-online-via-figma-e8oqosras.vercel.app)

---

**Projeto:** Sistema de Gerenciamento e Vendas para Loja de Roupas (Cyber Y2K / Dark Streetwear)  
**Responsável:** Luiz  

---

## 1. Configuração do Ambiente e Tech Stack
O projeto foi totalmente configurado e integrado com as seguintes tecnologias principais:

- **Front-end / Framework:** React / Next.js
- **Estilização:** Tailwind CSS (com tema Dark Mode Cyber Y2K)
- **Linguagem:** TypeScript
- **Back-end & Banco de Dados:** Node.js / PostgreSQL (via Supabase)
- **Hospedagem & Deploy:** Vercel (Ambiente de Homologação)

---

## 2. Módulos do Sistema Desenvolvidos e Funcionais

### 🛒 2.1 Vitrine e Catálogo de Produtos
- Exibição de roupas em grid com cards personalizados.
- Filtros interativos por categoria (Camisetas, Moletons, Calças, Acessórios).
- Campo de busca em tempo real por nome do produto.
- Modal / Página de detalhes do produto com seleção de variações (Tamanho P, M, G, GG e Cor).

### 🛍️ 2.2 Carrinho de Compras e Simulador de Checkout
- Adição e remoção dinâmica de produtos no carrinho.
- Validação automática de quantidade disponível em estoque.
- Cálculo de subtotal e valor total do pedido.
- Simulação de checkout com confirmação do pedido.

### 🔐 2.3 Autenticação e Gestão de Usuários
- Login e cadastro de clientes e administradores.
- Proteção de rotas administrativas.

### 📊 2.4 Painel Administrativo e Estoque
- Cadastro, edição e exclusão de novos produtos (CRUD).
- Atualização do saldo de estoque por variação.
- Histórico resumido de pedidos de vendas realizados.

---

## 3. Ambiente de Homologação e Deploy
A aplicação foi implantada em um ambiente público de testes para validação funcional das regras de negócio.

- **Link de Acesso:** [https://seu-site.vercel.app](https://criar-loja-online-via-figma-e8oqosras.vercel.app)
- **Status do Servidor:** Ativo / Online
- **Integração com Banco de Dados:** Conectado ao Supabase PostgreSQL
