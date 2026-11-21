# Ateliers RESUC · Sécurité du SIG-RESUC et protection des données

<p><img src="ndap-sukulu/img/armoiries_logo.jpg" alt="Armoiries de la République du Cameroun" height="64"> <img src="ndap-sukulu/img/banque_mondiale_logo.png" alt="Logo de la Banque mondiale" height="64"></p>

Coopération Cameroun - Banque mondiale

Plateforme des ateliers de sensibilisation des utilisateurs du SIG du Registre social unifié du Cameroun (RESUC) : guides du participant, présentations par lieu et salle de classe NDAP SUKULU chiffrée, sur le modèle de la formation OPJ-APJ.

Deux ateliers de deux jours, deux parcours sur la plateforme :

| Parcours | Atelier | Public |
|---|---|---|
| CENTRAL | Yaoundé, 9 et 10 décembre 2026 | Cadres du ST-RESUC et administrateurs du SIG |
| REGIONAL | Mbankomo (14 et 15 décembre), Bafoussam (17 et 18 décembre), Garoua (22 et 23 décembre) | Chefs de CESO, points focaux et superviseurs |

Toute la formation reste ouverte. Seuls les chapitres du parcours comptent pour les badges et le certificat de parcours validé.

**Accès réservé.** Le contenu ne s'ouvre qu'avec l'identifiant et le mot de passe remis par le Secrétariat technique du RESUC.

| Utilisation | Adresse |
|---|---|
| En ligne | `https://maletyon.github.io/ateliers-resuc/ndap-sukulu/` |
| Sur téléphone (fiches seulement) | `https://maletyon.github.io/ateliers-resuc/ndap-sukulu/telephone/` |
| Adresse de secours, si `github.io` est bloqué par le réseau | `https://raw.githack.com/MaletYon/ateliers-resuc/main/ndap-sukulu/` |
| Adresse de secours sur téléphone | `https://raw.githack.com/MaletYon/ateliers-resuc/main/ndap-sukulu/telephone/` |
| Sans Internet | archive `ndap-sukulu/NDAP_SUKULU_RESUC_ordinateur.zip` |
| Serveur du RESUC | même paquet déposé sur le serveur web du RESUC, lien depuis l'interface du SIG (voir `serveur/LISEZMOI.md`) |

Document confidentiel, propriété de la Banque mondiale. Seul le paquet scellé est publié, avec l'accord écrit du chef d'équipe de la Banque. Aucune donnée collectée ni aucun résultat d'analyse n'est publié.

## Contenu du dossier de travail (privé)

| Élément | Contenu |
|---|---|
| `RESUC_main.tex`, `RESUC_main.pdf` | Guide complet (prologue, 16 chapitres, annexes A à F), version française 0.1 |
| `RESUC_central_main.tex`, `RESUC_regional_main.tex` et leurs PDF | Guide de l'atelier central (tous les chapitres) et guide des ateliers régionaux (sans les chapitres 6, 14 et 15) |
| `Style_RESUC.sty` | Feuille de style reprise de `Style_OPJ-APJ.sty`, même charte, sans logo institutionnel |
| `front/`, `partie0/` à `partie6/`, `annexes/`, `bibliographie/` | Sources LaTeX |
| `corriges/` | Corrigé des activités, jamais publié |
| `_sources_guide/` | Générateurs : contenu des chapitres et banques (`contenu1.py` à `contenu3.py`), `gen.py`, `annexes.py`, `gen_labs.py`, `gen_specs.py` |
| `Présentation/` | Vision globale, puis un dossier par lieu (`Yaounde/`, `Mbankomo/`, `Bafoussam/FR/`, `Garoua/`), lieu et date sur chaque diapositive ; moteur et specs dans `_sources/` |
| `ndap-sukulu/`, `verification/` | Paquet publié, scellé |
| `outils/publier_ndap.py` | Reconstruit et scelle le paquet |
| `serveur/` | Notice de déploiement sur le serveur du RESUC |
| `conception/` | Structures validées |

Les banques de questions et les labs vivent dans `COURS\Prototypes\Ndap Sukulu\cours\RESUC` ; les clés et les comptes dans son sous-dossier `acces`, jamais publié.

## Mettre à jour

1. Modifier le contenu dans `_sources_guide/contenu*.py` (chapitres et banques) ou `gen_labs.py` (labs).
2. `py _sources_guide/gen.py <dossier>` puis copier les `.tex` ici et les banques dans `Prototypes\Ndap Sukulu\cours\RESUC\banques`.
3. Compiler les guides (pdfLaTeX, biber, makeindex) : `latexmk -pdf RESUC_central_main.tex` et `latexmk -pdf RESUC_regional_main.tex`.
4. `py Présentation/_sources/gen_specs.py Présentation/_sources` puis `py Présentation/_sources/run.py RESUC all`.
5. `py outils/publier_ndap.py`.
