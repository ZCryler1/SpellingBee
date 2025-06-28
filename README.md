# 🐝 Spelling Bee - Jogo de Digitação

Um jogo de digitação onde você deve escrever as palavras que ouve o mais rápido possível!

## ✨ Funcionalidades

- 🎧 **Síntese de voz** em português brasileiro
- 🤖 **IA para gerar palavras** usando Gemini 2.0 Flash via OpenRouter
- ⏱️ **Cronômetro** para medir velocidade de digitação
- 📊 **Sistema de pontuação** com histórico de acertos
- 🎨 **Interface moderna** com design responsivo

## 🚀 Como usar

### Modo Básico (Lista Local)
1. Abra o `index.html` no seu navegador
2. Clique em "🎮 Iniciar Jogo"
3. Ouça a palavra falada
4. Digite o que você ouviu
5. Pressione Enter ou clique em "✅ Verificar"

### Modo Avançado (IA)
1. **Obtenha uma chave da API OpenRouter:**
   - Acesse [OpenRouter.ai](https://openrouter.ai/)
   - Crie uma conta e obtenha sua chave da API
   - Garanta que tem créditos suficientes para usar o modelo `google/gemini-2.0-flash-001`

2. **Configure a API no jogo:**
   - Marque a opção "Usar IA para gerar palavras"
   - Insira sua chave da API OpenRouter
   - Clique em "💾 Salvar"

3. **Jogue com palavras geradas por IA:**
   - O status mudará para "🤖 IA ATIVA"
   - Cada nova palavra será gerada dinamicamente pelo Gemini 2.0 Flash
   - Palavras são adequadas para todas as idades e têm 4-12 letras

## 🛠️ Tecnologias Utilizadas

- **HTML5** - Estrutura da página
- **CSS3** - Estilização com gradientes e efeitos visuais
- **JavaScript** - Lógica do jogo e integração com APIs
- **Web Speech API** - Síntese de voz do navegador
- **OpenRouter API** - Acesso ao Gemini 2.0 Flash
- **LocalStorage** - Armazenamento das configurações

## 🔧 Arquivos do Projeto

```
Digitagames/
├── index.html              # Página principal
├── assets/
│   ├── css/
│   │   └── style.css       # Estilos do jogo
│   └── js/
│       └── jogo.js         # Lógica principal
└── README.md               # Este arquivo
```

## 💡 Características da IA

- **Modelo**: Google Gemini 2.0 Flash
- **Palavras**: Geradas dinamicamente em português brasileiro
- **Filtros**: Apenas palavras de 4-12 letras, adequadas para todas as idades
- **Fallback**: Se a API falhar, usa lista local de 30 palavras

## 🔐 Segurança

- Chaves da API são armazenadas localmente no navegador
- Comunicação segura via HTTPS com OpenRouter
- Dados não são enviados para servidores externos além da API

## 📝 Exemplo de Uso da API (Python)

```python
from openai import OpenAI

client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key="sua-chave-aqui",  # Substitua pela sua chave
)

completion = client.chat.completions.create(
    extra_headers={
        "HTTP-Referer": "http://localhost",
        "X-Title": "Spelling Bee Game",
    },
    model="google/gemini-2.0-flash-001",
    messages=[
        {
            "role": "user",
            "content": "Gere uma palavra em português para um jogo de digitação"
        }
    ]
)
print(completion.choices[0].message.content)
```

## 🎯 Dicas para Jogar

1. Use fones de ouvido para melhor qualidade do áudio
2. Configure o volume adequadamente
3. Pratique com palavras conhecidas primeiro
4. Tente ser o mais rápido possível mantendo a precisão

## 🐛 Solução de Problemas

- **Áudio não funciona**: Verifique se o navegador permite reprodução de áudio
- **API não responde**: Verifique sua chave da API e conexão com internet
- **Erro de CORS**: Use um servidor web local em vez de abrir diretamente o arquivo HTML

## 📄 Licença

Este projeto é de código aberto. Sinta-se livre para modificar e distribuir.

---

Divirta-se jogando! 🎮
