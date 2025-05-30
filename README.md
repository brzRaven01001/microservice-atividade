
# 🏫 School System + Atividades — Microsserviços

Este projeto é composto por dois microsserviços desenvolvidos para gerenciar dados de um ambiente escolar.

- 🎯 **School System:** responsável pela gestão dos professores.
- 🎯 **Atividades:** responsável pelo cadastro e controle de atividades, vinculadas a um professor registrado no School System.

Os microsserviços se comunicam entre si via API REST para garantir que apenas professores válidos possam criar atividades.

---

## 🚀 Tecnologias Utilizadas

- **Python 3.10+**
- **Flask** — Framework web
- **Requests** — Biblioteca HTTP cliente (para integração entre os microsserviços)
- **JSON** — Formato de comunicação entre APIs
- **Docker (opcional)** — Para conteinerização (caso desejado)
- **Postman / Insomnia** — Para testes das rotas (opcional)

---

## 👥 Integrantes do Projeto

- Murilo
- Kauan
- Yuri
- Beatriz
- Guilherme

---

## 🗂️ Estrutura dos Microsserviços

```
school-system/
│   app.py
│   controllers/
│       professor_controller.py
│   ...
atividade/
│   app.py
│   controllers/
│       atividade_controller.py
│   services/
│       school_system_client.py
│   ...
```

---

## ⚙️ Como Executar o Projeto

### ✅ Pré-requisitos:
- Ter o **Python 3.10+** instalado.
- (Opcional) Ter **Docker** instalado, caso queira rodar conteinerizado.

---

### 📥 Passo 1 — Clonar o Projeto

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
```

---

### 🏫 Passo 2 — Executar o School System

1. Acesse a pasta:

```bash
cd school-system
```

2. Instale as dependências:

```bash
pip install -r requirements.txt
```

3. Execute o servidor:

```bash
python app.py
```

🔗 O School System estará rodando em:  
`http://localhost:5000`

---

### 📝 Passo 3 — Executar o Microsserviço de Atividades

1. Em outro terminal, acesse a pasta:

```bash
cd atividade
```

2. Instale as dependências:

```bash
pip install -r requirements.txt
```

3. Execute o servidor:

```bash
python app.py
```

🔗 O Microsserviço de Atividades estará rodando em:  
`http://localhost:5001`

---

## 🔗 Integração Entre Microsserviços

- O microsserviço de **Atividades** se comunica com o **School System** para validar se o professor existe antes de cadastrar uma atividade.

---

## 🗒️ Endpoints

### 🏫 School System

| Método | Endpoint                            | Descrição                           |
|--------|--------------------------------------|--------------------------------------|
| GET    | `/professor/<id_professor>`         | Verifica se um professor existe     |

### 🔥 Atividades

| Método | Endpoint               | Descrição                             |
|--------|-------------------------|----------------------------------------|
| POST   | `/atividades`           | Cria uma nova atividade               |
| GET    | `/atividades`           | Lista todas as atividades cadastradas |

---

## 📜 Exemplos de Requests

### ➕ Criar uma atividade

**POST** `http://localhost:5001/atividades`  
**Body (JSON):**
```json
{
  "descricao": "Atividade de Matemática",
  "id_professor": 1
}
```

✔️ Se o professor existir no School System, a atividade será criada.  
❌ Se não existir, receberá uma resposta:

```json
{
  "error": "Professor não encontrado no School System"
}
```

---

## 🗑️ Encerrando os Servidores

Aperte `CTRL + C` no terminal onde cada servidor está rodando.

---

## 🚀 Melhorias Futuras (Sugestões)

- Adicionar persistência real com banco de dados (SQLite, PostgreSQL ou MySQL).
- Implementar autenticação e autorização.
- Adicionar testes automatizados.
- Criar mais microsserviços, como **Turmas** ou **Disciplinas**.

---

## ❤️ Agradecimentos

Projeto desenvolvido com fins acadêmicos para estudo de **microsserviços**, **API REST** e **integração entre sistemas**.

---

## 🏁 Status do Projeto:  
✅ **Concluído para entrega acadêmica**  
🚀 **Em desenvolvimento para melhorias futuras**
