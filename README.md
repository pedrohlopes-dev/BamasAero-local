# Bamas Aero 🕹️

Jogo de damas (checkers) desenvolvido em **HTML, CSS e JavaScript puro**, com estilo visual "Frutiger Aero" (vidro fosco, gradientes e transparências) e integração opcional com **Supabase** para histórico de partidas.

## 👥 Autores

- Guilherme Caetano Lima
- Gustavo de Souza Carvalho
- Jeferson Cordeiro dos Santos
- Pedro Henrique Lopes de Oliveira

## 📋 Sobre o projeto

O Bamas é um jogo de damas completo, jogado localmente entre dois jogadores no mesmo navegador. O projeto inclui:

- **Tela inicial** com vídeo de fundo e opção de ativar som;
- **Login** simples onde os dois jogadores informam seus nomes;
- **Seleção de tema** visual do tabuleiro (dois papéis de parede diferentes);
- **Tabuleiro de damas 8x8** com todas as regras clássicas: movimentos simples, capturas obrigatórias em sequência, promoção a dama (rainha) e empate por 20 lances de dama sem captura;
- **Histórico de jogadas** em tempo real durante a partida (jogador, origem, destino e capturas);
- **Placar** de vitórias e capturas por jogador;
- **Histórico de partidas** salvo em `localStorage` e (opcionalmente) sincronizado com um banco de dados **Supabase**;
- **Trilha sonora** de fundo durante a partida.

## 🛠️ Tecnologias utilizadas

- HTML5
- CSS3 (glassmorphism, `backdrop-filter`, gradientes)
- JavaScript (ES6+, POO)
- [Supabase](https://supabase.com/) (client-side, via CDN) para persistência remota do histórico de partidas

## 📁 Estrutura do projeto

```
bamas-aero/
├── index.html          # Tela inicial (vídeo de fundo + histórico via Supabase)
├── login.html          # Cadastro dos nomes dos jogadores
├── selecao.html        # Seleção do tema visual do tabuleiro
├── jogo.html           # Tela do jogo (tabuleiro, placar, histórico)
├── historico.html      # Histórico de partidas salvas localmente
├── css/
│   └── style.css       # Estilos do tabuleiro e painéis do jogo
├── js/
│   └── app.js          # Lógica do jogo (classe DamaGame)
├── img/                # Imagens (peças, ícones, papéis de parede, telas)
└── audio/              # Trilha sonora do jogo
```

> ⚠️ **Nota:** os arquivos de mídia (pasta `img/` e `audio/`) referenciados no código (peças, papéis de parede, vídeo de fundo, trilha sonora) precisam ser adicionados manualmente ao repositório, pois não fazem parte deste pacote de código-fonte.

## 🚀 Como rodar o projeto

Como o projeto usa apenas HTML/CSS/JS puro, basta servir os arquivos localmente:

```bash
# Usando o servidor embutido do Python
python -m http.server 8000
```

Depois acesse `http://localhost:8000/index.html` no navegador.

> Alguns navegadores bloqueiam `autoplay` de vídeo/áudio com som — por isso a tela inicial pede um clique para ativar o som.

## 🎮 Como jogar

1. Na tela inicial, clique no botão de **play** (imagem de start).
2. Informe os nomes do **Jogador 1** e do **Jogador 2**.
3. Escolha o tema visual do tabuleiro.
4. Jogue as damas: clique na peça e depois na casa de destino (capturas são obrigatórias quando disponíveis).
5. Ao final da partida, o resultado é salvo no histórico (local e, se configurado, no Supabase).

## 🗄️ Configuração do Supabase (opcional)

O `index.html` já vem com uma URL e chave anônima de um projeto Supabase de exemplo. Para usar seu próprio banco:

1. Crie um projeto em [supabase.com](https://supabase.com/);
2. Crie uma tabela `partidas` com colunas equivalentes a: `player1`, `player2`, `movimentos_p1`, `movimentos_p2`, `capturas_p1`, `capturas_p2`, `pontos_p1`, `pontos_p2`, `vencedor`, `data_partida`;
3. Substitua `supabaseUrl` e `supabaseKey` em `index.html` pelas credenciais do seu projeto.

## 📌 Status do projeto

Projeto acadêmico em desenvolvimento. Possíveis melhorias futuras:
- Persistir o histórico completo direto no Supabase (hoje o registro final também depende do `localStorage`);
- Adicionar modo online / multiplayer remoto;
- Adicionar testes automatizados para a lógica de movimentos e capturas.

## 📄 Licença

Projeto acadêmico — uso livre para fins educacionais.
