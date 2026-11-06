# v1.1.1 · 2026-11-06

# Capitulares v1.1.1 — What Changed

## English

1. **Improved EPUB compatibility:** better detection of chapter openings in light novels and books with alternative HTML structures.
2. **Refined screen-based drop caps:** additional drop caps now appear only at the beginning of eligible paragraphs, never in text continuing from previous screens.
3. **Improved consistency:** maximum of one additional drop cap per screen, with the counting interval resetting at each new chapter.

## Português (PT-PT)

1. **Compatibilidade EPUB melhorada:** deteção mais eficaz de inícios de capítulos em light novels e livros com estruturas HTML alternativas.
2. **Capitulares por ecrãs aperfeiçoadas:** as capitulares adicionais aparecem apenas no início de parágrafos elegíveis, nunca em continuações de texto de ecrãs anteriores.
3. **Maior consistência:** máximo de uma capitular adicional por ecrã, com reinício da contagem em cada novo capítulo.

# v1.1 · 2026-11-04

**Capitulares v1.1 — what changed **

English

1. Preserve font weight: new per-font option that keeps ornamental drop caps at a consistent weight, regardless of KOReader's global font-weight setting. The preference is saved individually for each font, while contrast and proportional scaling remain unaffected.
2. Custom profiles: create, save, and manage profiles containing different fonts, sizes, positions, and settings.
3. Quick profile switching: switch profiles directly from the KOReader menu without opening the editor.
4. Live View: size and position adjustments are reflected on the book page in real time.
5. Editorial Premium interface: reorganized controls, improved spacing, three ornamental initial previews, and more intuitive navigation.
6. More precise adjustments: improved directional controls with 1, 2, or 5-pixel increments.
7. Per-book customization: apply changes to the current book or save them as a reusable profile.
8. Stability improvements: fixes for the size slider, menu behavior, and dialogs when suspending or resuming the device.
9. Fixed popups: profile and detection dialogs now appear above the KOReader menu, which remains open for further adjustments.

Português (PT-PT)

1. Preservar peso da fonte: nova opção por fonte que permite manter a espessura das capitulares ornamentais, independentemente do peso global definido no KOReader. A preferência é guardada individualmente para cada fonte, sem afetar o contraste nem a escala proporcional.
2. Perfis personalizados: agora é possível criar, guardar e gerir perfis com diferentes fontes, tamanhos, posições e configurações.
3. Seleção rápida de perfis: permite alternar entre perfis diretamente no menu do KOReader, sem abrir o editor.
4. Live View: as alterações de tamanho e posição são refletidas diretamente na página do livro, em tempo real.
5. Interface Editorial Premium: reorganização dos controlos, melhoria do espaçamento, pré-visualização de três letras ornamentais e navegação mais intuitiva.
6. Ajustes mais precisos: controlos direcionais melhorados, com incrementos de 1, 2 ou 5 pixels.
7. Personalização por livro: possibilidade de aplicar alterações apenas ao livro atual ou guardá-las num perfil reutilizável.
8. Melhorias de estabilidade: correções no slider, na abertura dos menus e no comportamento das janelas ao suspender ou retomar o dispositivo.
9. Popups corrigidos: os seletores de perfil e deteção aparecem por cima do menu do KOReader, mantendo o menu aberto para outras alterações.

# v1.0 · 2026-11-03

# Capitulares v1.0 — First Public Release / Primeira Versão Pública

## English

**One universal KOReader plugin for Kobo and Kindle.**

Capitulares brings ornamental drop caps to EPUB books, with a font preview, per-book customization, and additional drop caps at configurable paragraph or screen intervals. It supports nested EPUB HTML structures and avoids enlarging dialogue dashes. An optional color palette is available on color-capable devices supported by KOReader.

### Installation

1. Download `Capitulares-v1.0.zip` from the **Assets** section of this release.
2. Close KOReader and extract the ZIP **into the plugins folder** on your device:
   - **Kobo:** `.adds/koreader/plugins/`
   - **Kindle:** `koreader/plugins/`
3. Check that the resulting folder is `plugins/capitulares.koplugin/`, restart KOReader, and open an EPUB.
4. In **Tools → Capitulares**, enable drop caps for the book and customize their appearance.

The ZIP contains **one `capitulares.koplugin/` folder at its root**. It does not include fonts, books, or diagnostic files.

### Important notes

- The plugin does **not** modify the original EPUB file.
- Screen-based drop cap placement depends on actual pagination and may not work perfectly with every EPUB.
- **Kindle Colorsoft:** color support and some EPUB structures may behave differently depending on the KOReader version.
- **License:** GNU Affero General Public License v3.0 (**AGPL-3.0**). See the `LICENSE` file in the repository.
- This is an **unofficial KOReader plugin**, not an official KOReader release.

---

## Português (Portugal)

**Um único plugin universal para KOReader em Kobo e Kindle.**

O Capitulares adiciona letras capitulares ornamentais aos EPUBs, com pré-visualização de fontes, personalização por livro e capitulares adicionais em intervalos configuráveis de parágrafos ou ecrãs. Suporta estruturas HTML aninhadas e evita ampliar os travessões de diálogo. Inclui uma paleta de cores opcional para dispositivos a cores suportados pelo KOReader.

### Instalação

1. Descarrega `Capitulares-v1.0.zip` na secção **Assets** desta Release.
2. Fecha o KOReader e extrai o ZIP **para a pasta de plugins** do dispositivo:
   - **Kobo:** `.adds/koreader/plugins/`
   - **Kindle:** `koreader/plugins/`
3. Confirma que ficou criada a pasta `plugins/capitulares.koplugin/`, reinicia o KOReader e abre um EPUB.
4. Em **Ferramentas → Capitulares**, ativa as capitulares para esse livro e personaliza-as.

O ZIP contém **uma única pasta `capitulares.koplugin/` na raiz**. Não inclui fontes, livros nem ficheiros de diagnóstico.

### Notas importantes

- O plugin **não modifica** o ficheiro EPUB original.
- A distribuição das capitulares por ecrãs depende da paginação real e pode não funcionar perfeitamente em todos os EPUBs.
- **Kindle Colorsoft:** as cores e algumas estruturas de EPUB podem comportar-se de forma diferente consoante a versão do KOReader.
- **Licença:** GNU Affero General Public License v3.0 (**AGPL-3.0**). Consulta o ficheiro `LICENSE` do repositório.
- Este é um **plugin não oficial do KOReader**, não uma versão oficial do KOReader.
