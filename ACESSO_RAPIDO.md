# 🏨 Sistema de Reserva de Hotéis - Acesso Rápido

**Projeto:** Prática Profissional em ADS - Universidade Presbiteriana Mackenzie  
**Integrante:** Samyra Driele Alborgueti  
**Data:** 14 de janeiro de 2026

---

## 📂 Estrutura do Projeto

```
hotel-reservation-system/
├── README.md                              # Descrição geral do projeto
├── ACESSO_RAPIDO.md                       # Este arquivo
└── docs/
    ├── entrega_1_documento_final.md       # ⭐ DOCUMENTO PRINCIPAL DE ENTREGA
    ├── project_tracking.md                # Quadro de acompanhamento
    ├── requirements_analysis.md           # Análise completa de requisitos
    ├── use_case_details.md                # Detalhes dos 3 casos de uso essenciais
    ├── use_case_diagram.mmd               # Diagrama em formato Mermaid
    └── use_case_diagram.png               # Diagrama em formato PNG
```

---

## 🎯 Informações Principais do Projeto

| Item | Descrição |
|------|-----------|
| **Tema** | Sistema de Reserva de Hotéis |
| **Fase** | Concepção (Aula 1) |
| **Modelo** | Processo Unificado (Iterativo e Incremental) |
| **Total de Casos de Uso** | 15 casos de uso identificados |
| **Casos de Uso Essenciais** | 3 casos de uso (20% do total) |
| **Interessados** | 6 categorias identificadas |
| **Objetivos Funcionais** | 9 objetivos definidos |
| **Objetivos Não-Funcionais** | 4 critérios de qualidade |

---

## 📋 Casos de Uso Essenciais Detalhados

### 1️⃣ UC01: Fazer Reserva de Quarto
- **Ator Primário:** Hóspede
- **Descrição:** Permite que um hóspede pesquise quartos disponíveis, selecione uma opção e confirme a reserva
- **Fluxo:** Busca → Seleção → Dados Pessoais → Pagamento → Confirmação

### 2️⃣ UC02: Processar Pagamento
- **Ator Primário:** Sistema
- **Descrição:** Coleta dados de pagamento e processa a transação com gateway externo
- **Fluxo:** Formulário Seguro → Validação → Autorização → Confirmação

### 3️⃣ UC03: Gerenciar Disponibilidade de Quartos
- **Ator Primário:** Gerente de Hotel
- **Descrição:** Permite visualizar ocupação e bloquear quartos para manutenção
- **Fluxo:** Acesso ao Painel → Visualização → Seleção → Atualização de Status

---

## 🔍 Interessados Identificados

| Categoria | Interessado | Interesse Principal |
|-----------|-------------|-------------------|
| **Usuários Finais** | Hóspedes | Realizar reservas de forma rápida e segura |
| | Gerentes de Hotel | Otimizar gestão de ocupação e receita |
| | Recepcionistas | Facilitar check-in/check-out |
| | Administradores | Garantir estabilidade e segurança |
| **Internos** | Equipe de Desenvolvimento | Construir software de qualidade |
| **Externos** | Proprietários do Hotel | Aumentar lucratividade |

---

## 🛡️ Objetivos Não-Funcionais

- **Desempenho:** Resposta < 2 segundos, suporta 1.000 usuários simultâneos
- **Segurança:** LGPD, criptografia SSL/TLS, armazenamento seguro de senhas
- **Confiabilidade:** 99.5% de disponibilidade, backups automáticos
- **Usabilidade:** Interface intuitiva, responsiva, acessível (WCAG 2.1 AA)

---

## 📊 Diagrama de Casos de Uso

Veja a imagem `use_case_diagram.png` para visualizar graficamente:
- Todos os 15 casos de uso do sistema
- Relacionamentos entre atores e casos de uso
- Relações de inclusão e extensão

---

## 🔗 Como Acessar os Documentos

### Opção 1: Visualizar Online (Markdown)
Abra qualquer um dos arquivos `.md` em um editor de texto ou visualizador Markdown:
- `entrega_1_documento_final.md` - Documento principal com toda a documentação
- `project_tracking.md` - Quadro de acompanhamento com status das tarefas
- `requirements_analysis.md` - Análise detalhada de requisitos

### Opção 2: Usar Git
```bash
# Navegar até o repositório
cd /home/ubuntu/hotel-reservation-system

# Ver histórico de commits
git log --oneline

# Ver status dos arquivos
git status

# Ver diferenças
git diff
```

### Opção 3: Converter para PDF (Opcional)
Se precisar de um arquivo PDF, use:
```bash
manus-md-to-pdf docs/entrega_1_documento_final.md docs/entrega_1_documento_final.pdf
```

---

## 📈 Próximas Fases do Projeto

| Fase | Aula | Iterações | Foco Principal |
|------|------|-----------|----------------|
| **Concepção** | 1 | 1 | Visão, escopo, casos de uso principais ✓ |
| **Elaboração** | 2 | 2-3 | Requisitos detalhados, arquitetura |
| **Construção** | 3 | Múltiplas | Implementação, testes |
| **Transição** | 4 | 1-2 | Implantação, versões beta |

---

## ✅ Checklist da Entrega 1

- ✓ Título do projeto definido
- ✓ Nomes dos integrantes do grupo documentados
- ✓ URL do repositório de código-fonte criada
- ✓ URL do quadro de acompanhamento criada
- ✓ Interessados identificados
- ✓ Objetivos funcionais definidos
- ✓ Objetivos não-funcionais definidos
- ✓ Diagrama de casos de uso criado
- ✓ Descrição detalhada dos 3 casos de uso essenciais (20%)
- ✓ Documento com capa, sumário, listas de figuras/tabelas, introdução

---

## 📞 Informações de Contato

**Integrante:** Samyra Driele Alborgueti  
**Instituição:** Universidade Presbiteriana Mackenzie  
**Disciplina:** Prática Profissional em ADS  
**Professor:** Tomaz Mikio Sasaki

---

*Documento gerado em 14 de janeiro de 2026*
