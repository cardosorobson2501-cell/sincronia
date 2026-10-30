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
- **Calibrar** (aba Entrada, com o microfone ativo): "Medir o silêncio" mede 2 segundos de ruído, calcula o piso e coloca o limite um pouco acima (margem ajustável). A barra de volume mostra o limite, a nota detectada e a confiança ao vivo, e há um controle de sensibilidade (− / +). A calibração fica guardada **por aparelho e navegador**; em outro aparelho o app pede para calibrar de novo.
- **1 nota:** reconhecimento por altura (pYIN). A nota só vale se ficar firme por cerca de 80 ms, com confiança acima do mínimo ajustável. O que está abaixo do limite de volume é ignorado.
- **2 notas:** reconhecedor Basic Pitch (Spotify), guardado em `modelos/` e `vendor/`, carregado só quando a atividade tem 2 notas e a entrada é o microfone. Se não carregar, o app usa um método mais simples e avisa.
- O áudio é pedido **bruto**, sem cancelamento de eco, supressão de ruído nem ganho automático, e o app mostra se o aparelho respeitou.
- **Amostras de som por nota** continuam disponíveis (aba Entrada).

## Tela de teste (aba 5)
- **Ao vivo:** o que o app entendeu em cada entrada (MIDI, toque, microfone), com confiança.
- **Teste guiado:** o app pede notas e intervalos e mostra a taxa de acerto separada para nota única e para cada intervalo, e o que foi ouvido nos erros.
- **Comparar MIDI × microfone:** o MIDI é a resposta certa; o app mostra em quais notas e intervalos o microfone erra. Os resultados podem ser baixados em planilha (CSV).

## iPad
- Abra o Sincronia pelo endereço https do Netlify ou GitHub Pages (o microfone só funciona em páginas seguras). Safari → Compartilhar → **Adicionar à Tela de Início** cria o ícone.
- O iOS costuma pedir a permissão do microfone de novo a cada abertura do app; é uma regra do sistema.
- Se o microfone for recusado: Ajustes → Safari → Microfone → Permitir.
- **Roteiro de teste no iPad:** (1) ativar o microfone e conferir a linha "Áudio bruto"; (2) calibrar; (3) tocar uma nota e ver nota e confiança; (4) aba Teste → teste guiado só com notas; (5) trocar a atividade para 2 notas, esperar "Reconhecedor de 2 notas pronto" e repetir o teste com intervalos; (6) abrir pelo ícone da tela inicial e repetir os passos 1 a 3.

## Se o vídeo não abrir
Converta para MP4 (H.264 + AAC). Se estiver usando dentro de outro aplicativo, baixe o `index.html` e abra direto no navegador.
