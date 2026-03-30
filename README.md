# 🇵🇹 FlagPrefix — Plugin PaperMC

Sistema de bandeiras no nick dos jogadores para servidores PaperMC.

---

## 📦 Como compilar

### Requisitos
- Java 17+
- Maven 3.8+
- Acesso à internet (para baixar dependências)

### Compilar
```bash
cd FlagPrefix
mvn clean package
```

O JAR final estará em: `target/FlagPrefix-1.0.0.jar`

### Instalar no servidor
1. Copia o JAR para a pasta `plugins/` do teu servidor PaperMC
2. Reinicia o servidor
3. Pronto! ✅

---

## 📋 Requisitos do servidor
- PaperMC 1.21+ (funciona com 1.20.4+)
- Java 17+

---

## 🎮 Comandos

| Comando | Descrição |
|---------|-----------|
| `/flag set portugal` | Equipa a bandeira de Portugal 🇵🇹 |
| `/flag remove` | Remove a tua bandeira |
| `/flag list` | Ver bandeiras disponíveis (clicável!) |

**Alias:** `/bandeira` também funciona!

---

## 🔐 Permissões

| Permissão | Descrição | Default |
|-----------|-----------|---------|
| `flagprefix.use` | Usar o comando /flag | Todos |
| `flagprefix.admin` | Gerir bandeiras de outros | OP |

---

## 📁 Ficheiros gerados

```
plugins/
└── FlagPrefix/
    ├── config.yml       — Configuração geral
    └── playerdata.yml   — Dados dos jogadores (auto-gerado)
```

---

## ➕ Adicionar mais bandeiras no futuro

Abre o ficheiro `FlagManager.java` e adiciona na secção indicada:

```java
// Exemplos de bandeiras futuras:
register(new Flag("brazil",  "Brasil",          "🇧🇷"));
register(new Flag("spain",   "Espanha",         "🇪🇸"));
register(new Flag("usa",     "Estados Unidos",  "🇺🇸"));
register(new Flag("france",  "França",          "🇫🇷"));
register(new Flag("germany", "Alemanha",        "🇩🇪"));
register(new Flag("italy",   "Itália",          "🇮🇹"));
register(new Flag("uk",      "Reino Unido",     "🇬🇧"));
```

Emojis de bandeiras Unicode funcionam em todos os clientes Minecraft modernos.

---

## 🔧 config.yml

```yaml
# Formato do nick com bandeira
# %flag% = emoji, %player% = nome do jogador
nick-format: "%flag% %player%"
```

---

## 📖 Como funciona

1. Jogador usa `/flag set portugal`
2. O plugin guarda a escolha em `playerdata.yml`
3. O display name e a tab list são atualizados: `🇵🇹 NomeDoJogador`
4. No chat aparece: `🇵🇹 NomeDoJogador: mensagem`
5. Ao sair e entrar, a bandeira é restaurada automaticamente

---

*Plugin desenvolvido para PaperMC — Adventure API nativa*
