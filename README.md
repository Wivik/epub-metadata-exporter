# Epub Metadata Extractor

A simple tool to extract various data from an EPUB3 file. I wanted something to easily calculate how many pages and words my books contains.

[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=Wivik_epub-metadata-exporter&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=Wivik_epub-metadata-exporter)

## Output

Provide an epub3 file and this tool will return :

- The title
- The Author
- The Description
- The ISBN
- The License
- The total of words
- An estimation of the total of pages

The page number estimated is based on a average of 350 words per page. This setting can be changed.

## How to

Clone this repository.

Initiate a virtualenv and enable it.

```bash
virtualenv venv
source venv/bin/activate
```

Install the dependencies

```bash
pip install -r requirements.txt
```

```bash
python epub-metadata-extractor.py somefile.epub

```

## Arguments

- `--words_per_page` : Number of words per page to count the page total. Default is 350.
- `--output_format` : Possible values are : `text`, `json`, `yaml`. Default is `text`.

## Output examples

Default text :

```
Title: Le patient Daniel
Author: Seb Astien
ISBN: 978-2-9591085-4-9
License: Creative Commons Attribution ShareAlike 4.0
Description: Rencontrez Daniel et plongez dans les abysses de son esprit tourmenté. Interné dans un institut psychiatrique depuis plusieurs mois, cet homme est en proie à une intense dépression depuis des années causée par la perte d’un lien qui lui était cher. Depuis, il ne fait que de revivre en boucle ce qu’il prétend être ses innombrables vies passées. Les souvenirs et détails qu’il témoigne à sa thérapeute défient l’entendement et réveillent en lui d’indicibles traumatismes qui semblent appartenir à une époque lointaine, révolue, voire oubliée si d’aventure celle-ci aurait vraiment existé. Docteure en Psychologie, Ingrid Kirdjanen s’est donnée pour mission de faire la lumière sur le cas du patient Daniel.
Total words: 34409
Total pages: 98
```

JSON :

```json
{"title": "Le patient Daniel", "author": "Seb Astien", "isbn": "978-2-9591085-4-9", "license": "Creative Commons Attribution ShareAlike 4.0", "description": "Rencontrez Daniel et plongez dans les abysses de son esprit tourmenté. Interné dans un institut psychiatrique depuis plusieurs mois, cet homme est en proie à une intense dépression depuis des années causée par la perte d’un lien qui lui était cher. Depuis, il ne fait que de revivre en boucle ce qu’il prétend être ses innombrables vies passées. Les souvenirs et détails qu’il témoigne à sa thérapeute défient l’entendement et réveillent en lui d’indicibles traumatismes qui semblent appartenir à une époque lointaine, révolue, voire oubliée si d’aventure celle-ci aurait vraiment existé. Docteure en Psychologie, Ingrid Kirdjanen s’est donnée pour mission de faire la lumière sur le cas du patient Daniel.", "total_words": 34409, "total_pages": 98}

```

YAML

```yaml
author: Seb Astien
description: Rencontrez Daniel et plongez dans les abysses de son esprit tourmenté.
  Interné dans un institut psychiatrique depuis plusieurs mois, cet homme est en proie
  à une intense dépression depuis des années causée par la perte d’un lien qui lui
  était cher. Depuis, il ne fait que de revivre en boucle ce qu’il prétend être ses
  innombrables vies passées. Les souvenirs et détails qu’il témoigne à sa thérapeute
  défient l’entendement et réveillent en lui d’indicibles traumatismes qui semblent
  appartenir à une époque lointaine, révolue, voire oubliée si d’aventure celle-ci
  aurait vraiment existé. Docteure en Psychologie, Ingrid Kirdjanen s’est donnée pour
  mission de faire la lumière sur le cas du patient Daniel.
isbn: 978-2-9591085-4-9
license: Creative Commons Attribution ShareAlike 4.0
title: Le patient Daniel
total_pages: 98
total_words: 34409

```

## License

MIT - See [LICENSE.md](LICENSE.md).

## Contribute

Fork, open a pull request :)
