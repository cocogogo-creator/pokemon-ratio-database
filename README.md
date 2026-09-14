# Pokémon Ratio Corpus — 0 € / forum-dl / GitHub Actions

Ce dépôt ne recrée pas un scraper.

Il utilise **forum-dl**, outil open source existant compatible phpBB, pour aspirer
les fils Pokécardex listés dans `threads.txt`.

## Lancer

1. Créer un dépôt GitHub **public**.
2. Envoyer tout le contenu de ce dossier à la racine du dépôt.
3. GitHub : `Settings` → `Actions` → `General`.
4. Dans `Workflow permissions`, choisir `Read and write permissions`.
5. `Actions` → `Collect Pokecardex ratio threads` → `Run workflow`.

## Résultat

Le workflow crée :

- `data/threads/<id>.jsonl` : un fichier par fil ;
- `data/pokecardex_ratio_corpus.jsonl` : corpus fusionné ;
- `data/errors.log` : fils qui auraient échoué.

Le corpus est également disponible dans l'Artifact GitHub
`pokecardex-ratio-corpus`.

## Étape suivante

Donner `pokecardex_ratio_corpus.jsonl` à ChatGPT.

L'analyse doit alors ignorer tout sauf :

- Alternative / Alt Art
- SAR
- SIR

et récupérer uniquement :

`extension | carte | catégorie | item d'origine | attribution certaine/ambiguë | source`

Puis compter les provenances :

`ETB | tripack | display | coffret | blister | bundle | duopack | mini-tin | autre | indéterminé`

## Outil utilisé

forum-dl :
https://pypi.org/project/forum-dl/

Aucun scraper Pokémon personnalisé n'est utilisé ici.
