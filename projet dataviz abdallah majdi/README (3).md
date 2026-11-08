# Temps d'écran, réseaux sociaux, sommeil et santé mentale des jeunes

Projet de visualisation des données – Licence Big Data (3ème année, S1)
Réalisé par **Abdallah Yazidi** et **Majdi Gharbi**

![Aperçu du tableau de bord](images/apercu.png)

## Problématique

À partir de quel seuil d'usage quotidien les réseaux sociaux dégradent-ils le sommeil et la santé mentale des jeunes, et quels liens les données ne permettent-elles pas d'affirmer ?

## Résultats clés (dans les jeux de données utilisés)

| Constat | Valeur |
|---|---|
| Sommeil moyen des étudiants selon l'usage quotidien | 7,9 h (0-2 h) → 5,4 h (6 h et plus) |
| Score de santé mentale moyen (sur 10) | 8 → 5 |
| Part d'étudiants déclarant un impact négatif | 0 % → 7 % → 56 % → 100 % (par tranche d'usage croissante) |
| Enfants dépassant la limite d'écran recommandée | environ 86 % |

Indicateurs de contexte : 2 h 21 par jour sur les réseaux sociaux dans le monde (DataReportal, Digital 2026) ; usage problématique chez les adolescents passé de 7 % à 11 % entre 2018 et 2022 (OMS Europe / HBSC, 2024).

## Données

| Fichier | Lignes | Statut |
|---|---|---|
| Social_media_impact_on_life.csv | 1 705 | Retenu |
| Indian_Kids_Screen_Time.csv | 9 712 | Retenu |
| Students_Social_Media_Addiction.csv | 705 | Écarté (704 lignes déjà dans le premier fichier) |
| Smartphone_Usage_And_Addiction_Analysis_7500_Rows.csv | 7 500 | Écarté (aucun lien exploitable) |
| reels_attention_span_dataset_12000.csv | 12 000 | Écarté (aucun lien exploitable) |

Les jeux de données viennent de Kaggle. Vérifiez la licence de chaque jeu avant de le republier ; à défaut, ajoutez seulement le lien de téléchargement dans `data/README.md`.

## Méthode

Préparation dans **Power Query** :
- suppression de 44 doublons (enfants : 9 712 → 9 668 lignes) ;
- remplacement du texte « None » par « Aucun » ;
- conversion des colonnes décimales avec les paramètres régionaux anglais (le point décimal du CSV donnait des erreurs en français) ;
- création de tranches d'usage (0-2 h, 2-4 h, 4-6 h, 6 h et plus) ;
- colonne 0/1 pour le dépassement de la limite d'écran.

Visuels dans **Power BI** : graphique en courbes, histogramme empilé à 100 %, carte et graphique à barres, avec des mesures de moyenne.

## Cible

Lycéens, étudiants et parents (numératie faible à moyenne, expertise faible) ; infirmiers et enseignants en cible secondaire. Les visuels sont donc simples, avec des titres qui énoncent le message.

## Structure du dépôt

```
.
├── README.md
├── data/            # liens ou échantillons des jeux de données
├── powerbi/         # fichier .pbix
├── livrables/       # livrable 1 et livrable 2 (PDF)
├── presentation/    # présentation finale (PDF)
└── images/          # captures du tableau de bord
```

## Limites

- Les jeux de données ne sont pas des statistiques officielles ; certaines régularités sont inhabituelles pour de vraies enquêtes.
- Une corrélation n'est pas une causalité.
- Les populations (étudiants dans le monde, enfants en Inde) ne sont pas comparables entre elles.

## Utilisation de l'IA

Un assistant d'IA a servi d'aide à l'apprentissage (structure du projet, syntaxe Power Query) et à générer des illustrations, qui ne représentent pas les données. Tous les résultats ont été vérifiés dans Power BI.

## Références

- DataReportal (Kepios), *Digital 2026 Global Overview Report*, 2025.
- OMS Europe / HBSC, *A focus on adolescent social media use and gaming in Europe, central Asia and Canada*, 2024.
