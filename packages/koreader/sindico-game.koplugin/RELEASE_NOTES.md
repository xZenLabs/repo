# v1.1.1 · 2026-11-13


- Fewer repeated cards: a card you have not seen yet in the game is three times as likely to be drawn. In the second term, repeats go from about a quarter of the cards to about one in nine, and the difficulty stays about the same. A game in progress gets this too.

# v1.1.0 · 2026-11-12


- A new look for every screen. The home screen shows the game in progress, the gallery is a collection of the endings found and the ones still locked, each with the icon of how it is reached, the minutes are a page of a minutes book, an ending shows the numbers of the game, and how to play shows examples.
- What a decision led to shows in large type, on a screen of its own after the tap, or as a note on top of the next card: you choose in the new Settings screen.
- The date, the time and the battery in the corner of every screen, updated with each tap. They can be turned off in Settings.
- Buttons and headings have only the first letter in capitals.
- The game is also in English and Spanish, following the language of KOReader (English for any other language). The jokes were adapted for each language, and the building stays in Brazil. A game in progress follows a change of language, minutes included.
- On devices with keys, the Back key goes back one screen and closes the game from the home screen.
- If the game cannot open, a notice shows up instead of KOReader closing, and the screen rotation goes back to what it was.
- The screen flashes to clear what e-ink leaves behind after nine updates in a row, in the lists too, and when the device wakes up.
- A saved game that no longer fits (from a version with other cards, or a damaged file) is dropped without losing the records and the gallery. Games in progress from 1.0.x carry on.
- Reviewed card texts: jokes that were hard to get, vague one-liners, repeated lines and lines in the wrong character's voice were rewritten.
- The sleep screen cover has a new look, in the style of the other Beater Studios games.
- Portraits are saved at 600 px and fill the room the question leaves in the card, so they show larger and stay sharp on big screens.
- Touched up portraits. The frame sits on the edge with nothing showing outside it, the clothes show where the arms meet the chest, items reach the bottom of the frame instead of floating, and the floating key and pencil are gone. Faces: the nose shows above mustaches and beards, the hairline no longer runs past the hair, earrings hang from the ears, stubble stays on the face and the forehead lines that looked like a second pair of brows are gone. Hair: the bald sides grow above the ears, Pedro's spiky hair fills his headphones, the ponytail and long hair have clean outlines, combed hair follows its curve and Dona Carmem's white hair stands out from her face. Clothes: open collars, t-shirts and dresses show the neck, dresses have buttons and the necklace sits under the chin, aprons and Renata's uniform stand out from the outlines and the background. The hats close against their brims, the headphones are gray against the hair and Almirante's collar sits around his neck.

# v1.0.2 · 2026-11-08


- Com o jogo aberto, a tela de descanso mostra a capa do Síndico no lugar da capa do livro.

# v1.0.1 · 2026-11-04


- Vencer os 5 mandatos agora conta 5 mandatos completos na tela de final e no recorde, não 4.
- Os dias da partida param em 720 por mandato, e o mês exibido não passa de 24.
- Uma escolha pode definir os próprios `days`. "Tirar uns dias", do Kleber, passa a consumir 30 dias, como estava previsto.
- A galeria não conta mais o final de segurança `no_cards`, que não aparece em jogo. Agora dá para completá-la.
- Finais alcançados por uma escolha mostram o prédio inteiro, e o campo `good` dos finais passa a valer.
- Sem cartas elegíveis, o motor nunca repete a prestação de contas nem as demais cartas `at_day`.
- O validador recusa chaves desconhecidas, valores não inteiros, `resolve` inválido, carta de eleição com só um lado e personagem sem retrato.

# v1.0.0 · 2026-11-04


Primeira versão pública.

- 266 cartas em 8 decks, 18 personagens, 15 arcos com consequências agendadas e 25 finais.
- Quatro medidores, mandatos com assembleias e eleição, ata da partida e galeria de finais.
- Progresso salvo a cada decisão.
- Tela Sobre com versão, autoria e licenças.
- Sempre em retrato: aberto em paisagem, o jogo gira a tela e restaura a rotação ao fechar.
