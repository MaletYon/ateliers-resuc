# Ateliers RESUC · Sécurité du SIG-RESUC et protection des données

Plateforme des ateliers de sensibilisation des utilisateurs du SIG du Registre social unifié du Cameroun (RESUC) : guide du participant, présentations par journée et salle de classe NDAP SUKULU chiffrée, sur le modèle de la formation OPJ-APJ.

**Accès réservé.** Le contenu ne s'ouvre qu'avec l'identifiant et le mot de passe remis par le Secrétariat technique du RESUC.

| Utilisation | Adresse |
|---|---|
| En ligne | `https://maletyon.github.io/ateliers-resuc/ndap-sukulu/` |
| Sur téléphone (fiches seulement) | `https://maletyon.github.io/ateliers-resuc/ndap-sukulu/telephone/` |
| Sans Internet | archive `ndap-sukulu/NDAP_SUKULU_RESUC_ordinateur.zip` |
| Serveur du RESUC | même paquet déposé sur le serveur web du RESUC, lien depuis l'interface du SIG (voir `serveur/LISEZMOI.md`) |

Document confidentiel, propriété de la Banque mondiale. Publication sur GitHub seulement après accord écrit du chef d'équipe de la Banque.

## Contenu du dossier de travail (privé)

| Élément | Contenu |
|---|---|
| `RESUC_main.tex`, `RESUC_main.pdf` | Guide du participant (prologue, 16 chapitres, annexes A à F), version française 0.1 |
| `Style_RESUC.sty` | Feuille de style reprise de `Style_OPJ-APJ.sty`, même charte, sans logo institutionnel |
| `front/`, `partie0/` à `partie6/`, `annexes/`, `bibliographie/` | Sources LaTeX |
| `corriges/` | Corrigé des activités, jamais publié |
| `_sources_guide/` | Générateurs : contenu des chapitres et banques (`contenu1.py` à `contenu3.py`), `gen.py`, `annexes.py`, `gen_labs.py`, `gen_specs.py` |
| `Présentation/` | Vision globale et journées JC1, JC2, JC3, JY1, JY2, JG4 ; moteur et specs dans `_sources/` |
| `ndap-sukulu/`, `verification/` | Paquet publié, scellé |
| `outils/publier_ndap.py` | Reconstruit et scelle le paquet |
| `serveur/` | Notice de déploiement sur le serveur du RESUC |
| `conception/` | Structures validées |

Les banques de questions et les labs vivent dans `COURS\Prototypes\Ndap Sukulu\cours\RESUC` ; les clés et les comptes dans son sous-dossier `acces`, jamais publié.

## Mettre à jour

1. Modifier le contenu dans `_sources_guide/contenu*.py` (chapitres et banques) ou `gen_labs.py` (labs).
2. `py _sources_guide/gen.py <dossier>` puis copier les `.tex` ici et les banques dans `Prototypes\Ndap Sukulu\cours\RESUC\banques`.
3. Compiler le guide (pdfLaTeX, biber, makeindex) : `latexmk -pdf RESUC_main.tex`.
4. `py Présentation/_sources/gen_specs.py Présentation/_sources` puis `py Présentation/_sources/run.py RESUC all`.
5. `py outils/publier_ndap.py`.
