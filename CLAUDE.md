# Site APR · Huff Studio

Gustavo (Huff Studio) faz sites imersivos de empreendimentos imobiliários para incorporadoras.
Este repositório é uma **amostra de projeto** para apresentar a clientes: marca fictícia "Huff" e prédios com nomes inventados.
É o site publicado e também o arquivo de trabalho: a versão aqui é sempre a mais recente.
Fale com ele em português, de forma simples e direta. Ele não é programador.

## Links (GitHub Pages, publica sozinho ~1 min após o push na `main`)
- Página da construtora (inicial): https://huffstudio.github.io/Site-APR/
- Altavera Residence: https://huffstudio.github.io/Site-APR/altavera/ (também abre dentro da página inicial, num iframe)
- Prévia em moldura de celular: https://huffstudio.github.io/Site-APR/celular/

## Arquivos
- `index.html`: página da construtora fictícia Huff. Nav compacta e centralizada (logo Huff: selo com H, Empreendimentos, A empresa, botão "Fale conosco"), fundo de seda animada em WebGL (`window.grSilk`).
- `altavera/index.html` (~5 MB): site do Altavera Residence. Tem imagens embutidas em base64; **nunca leia o arquivo inteiro**: use grep/offset e edições pontuais.
  Ordem das seções: intro, 01 Localização (`#localizacao`), 02 Apartamentos/plantas (`#unidades`), Passeio pelos ambientes (`#passeio`), 03 Ambientes (`#ambientes`, só áreas comuns), 04 Lazer (`#lazer`), 05 Térreo e garagem (`#terreo`), 06 Obra, 07 Arquitetura, 08 Conceito, 09 Reserva (`#reservar`).
- `altavera/img/`: imagens do site (incluindo `apto/` e as imagens de satélite `sat-z*.webp`).
- `altavera/tour/`: fotos do Passeio pelos ambientes (efeito Ken Burns, troca a cada 5,6 s com crossfade, mini planta com ponto pulsante).
- `celular/index.html`: página que mostra o site dentro de um celular (iPhone / Pro Max / Android, girar, recarregar).

## Regras do Gustavo (sempre)
- Antes de editar: `git pull` (outra sessão pode ter mexido).
- Bonito no computador **e** no celular. Nunca entregar versão "mais leve"/simplificada no celular sem ele pedir.
- Paleta vinho/terracota. O Altavera mantém o visual da página inicial.
- É amostra: **nunca** usar nome, logo, endereço, telefone ou e-mail de construtora real, nem nome de prédio real. Nomes atuais (todos inventados): Altavera Residence, Aurélia Club Residence, Orbe Corporate Tower, Bellacqua, Vale Serena, Monte Velluto, Opus Lumière. As fotos da fachada tiveram o letreiro do pórtico trocado por "Altavera Residence".
- Sem WhatsApp em lugar nenhum. Sem links para redes sociais.
- O fundo da página inicial não pode ser foto do Altavera.
- Cursor personalizado: ponto pequeno.
- Seda do fundo: movimento lento (`float t=T*.04;` no shader). Ela pausa quando `window.__silkPause` está ativo (ex.: planta 3D aberta); o iframe do Altavera avisa a página pai por postMessage `{grSilk:bool}`.
- Planta 3D (Three.js r128): no celular usa configuração leve (sem antialias, pixelRatio ≤ 1,35, sombras 1024) e volta para 2D se o iPhone derrubar o WebGL.
- Nunca digitar senhas nem pedir chaves secretas. Login no GitHub é o próprio Gustavo quem faz.

## Como publicar
1. `git pull`
2. Editar, abrir no navegador (Playwright) e conferir em tela de computador e de celular (390 px).
3. `git commit` com mensagem em português explicando a mudança e `git push` na `main`.
4. Mandar o link para ele conferir.
