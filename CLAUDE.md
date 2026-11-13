# Site APR · Huff Studio

Gustavo (Huff Studio) faz sites imersivos de empreendimentos imobiliários para incorporadoras.
Este repositório é o site publicado e também o arquivo de trabalho: a versão aqui é sempre a mais recente.
Fale com ele em português, de forma simples e direta. Ele não é programador.

## Links (GitHub Pages, publica sozinho ~1 min após o push na `main`)
- Página da Haacke (inicial): https://huffstudio.github.io/Site-APR/
- Gran Reserva Residence: https://huffstudio.github.io/Site-APR/gran-reserva/ (também abre dentro da página da Haacke, num iframe)
- Prévia em moldura de celular: https://huffstudio.github.io/Site-APR/celular/

## Arquivos
- `index.html`: página da Haacke. Nav compacta e centralizada (logo vetorial oficial, Empreendimentos, A empresa, botão "Fale conosco"), fundo de seda animada em WebGL (`window.grSilk`).
- `gran-reserva/index.html` (~5 MB): site do Gran Reserva. Tem imagens embutidas em base64; **nunca leia o arquivo inteiro**: use grep/offset e edições pontuais.
  Ordem das seções: intro, 01 Localização (`#localizacao`), 02 Apartamentos/plantas (`#unidades`), Passeio pelos ambientes (`#passeio`), 03 Ambientes (`#ambientes`, só áreas comuns), 04 Lazer (`#lazer`), 05 Térreo e garagem (`#terreo`), 06 Obra, 07 Arquitetura, 08 Conceito, 09 Reserva (`#reservar`).
- `gran-reserva/img/`: imagens do site (incluindo `apto/` e as imagens de satélite `sat-z*.webp`).
- `gran-reserva/tour/`: fotos do Passeio pelos ambientes (efeito Ken Burns, troca a cada 5,6 s com crossfade, mini planta com ponto pulsante).
- `celular/index.html`: página que mostra o site dentro de um celular (iPhone / Pro Max / Android, girar, recarregar).

## Regras do Gustavo (sempre)
- Antes de editar: `git pull` (outra sessão pode ter mexido).
- Bonito no computador **e** no celular. Nunca entregar versão "mais leve"/simplificada no celular sem ele pedir.
- Paleta vinho/terracota. O Gran Reserva mantém o visual da Haacke.
- Sem WhatsApp em lugar nenhum. Sem links para haacke.com.br nem redes sociais.
- O fundo da página da Haacke não pode ser foto do Gran Reserva.
- Cursor personalizado: ponto pequeno.
- Seda do fundo: movimento lento (`float t=T*.04;` no shader). Ela pausa quando `window.__silkPause` está ativo (ex.: planta 3D aberta); o iframe do Gran Reserva avisa a página pai por postMessage `{grSilk:bool}`.
- Planta 3D (Three.js r128): no celular usa configuração leve (sem antialias, pixelRatio ≤ 1,35, sombras 1024) e volta para 2D se o iPhone derrubar o WebGL.
- Nunca digitar senhas nem pedir chaves secretas. Login no GitHub é o próprio Gustavo quem faz.

## Como publicar
1. `git pull`
2. Editar, abrir no navegador (Playwright) e conferir em tela de computador e de celular (390 px).
3. `git commit` com mensagem em português explicando a mudança e `git push` na `main`.
4. Mandar o link para ele conferir.
