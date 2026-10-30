# Sincronia

App de atenção com música em cores: o paciente vê o vídeo, toca junto e o app conta os acertos.
Tudo está em um único arquivo, `index.html`. Não precisa instalar nada.

## Como usar
1. Abra `index.html` no Chrome, Edge ou Safari (computador, celular ou tablet).
2. Abra o vídeo da atividade (MP4 H.264 é o formato mais seguro).
3. Aba **Entrada**: escolha como o paciente toca.
   - **Teclado na tela (toque)**: para celular e tablet.
   - **Teclado MIDI**, **microfone** (teclado ou sinos/outros instrumentos) ou **teclado do computador**.
4. Aba **Gabarito**: grave tocando junto com o vídeo ou leia as cores do vídeo.
5. Aba **Sessão**: inicie com o paciente. O resultado fica no **Histórico**.

## Gabarito de 1 ou 2 notas
- Cada evento do gabarito tem **um tempo e 1 ou 2 notas**. Na aba Gabarito, em **Configuração da atividade**, escolha "Notas esperadas": 1 nota por vez (padrão) ou 1 ou 2 notas juntas (intervalo).
- Em **Programar o gabarito**, escolha o tempo e toque as teclas do piano na tela. Clique num evento da lista para editar ou apagar.
- A tolerância de tempo e a janela das "notas juntas" (padrão 150 ms no toque e MIDI, 250 ms no microfone) são ajustadas por atividade.
- **Acerto** só quando as notas esperadas foram tocadas, dentro da tolerância, e nenhuma a mais. O resultado mostra o que faltou ou sobrou, as notas tocadas e a latência de cada evento, e a taxa de acerto separada para nota única e para cada intervalo.
- Gabaritos antigos são convertidos sozinhos.

## Entradas
- **Teclado na tela (toque)**, com 2 dedos ao mesmo tempo.
- **Teclado MIDI por cabo USB**: lê a nota e o instante exatos. Se o navegador não tiver MIDI (Safari e Chrome no iPad e iPhone), o app avisa e segue funcionando com as outras entradas.
- **Microfone** e **teclado do computador**.

## Sessão: treino e avaliação
- **Treino**: feedback verde/vermelho em cada toque, contador de acertos, erros e perdidas, e a faixa que antecipa as notas (pode ser desligada).
- **Avaliação**: sem nenhum feedback e sem a faixa; só o vídeo e as teclas. O resultado aparece no fim.
- A sessão pode entrar em **tela cheia** sozinha; há botões para sair e para encerrar.

## Microfone
- **Volume mínimo** em dB, com botões − / +, e botão **Medir o ruído da sala**.
- **Ajustes avançados**: ganho, intervalo entre toques, força do ataque, tempo de escuta, faixa de notas e tolerância.
- **Amostras de som por nota**: ensine cada nota (3 toques) a um conjunto/instrumento. O app guarda o "jeito" do som e um áudio curto que dá para ouvir (▶). As amostras entram na **Cópia de segurança**.

## Se o vídeo não abrir
Converta para MP4 (H.264 + AAC). Se estiver usando dentro de outro aplicativo, baixe o `index.html` e abra direto no navegador.
