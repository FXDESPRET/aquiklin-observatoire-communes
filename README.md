# Aquiklin · Observatoire Communes (back-office)

Application **indépendante** de l'Observatoire actuel (`aquiklin-observatoire`), réservée au personnel Aquiklin.

## Contenu du dépôt

| Fichier | Rôle |
|---|---|
| `index.html` | l'application (une seule page, sans compilation) |
| `config.js` | adresse Supabase, clé publique « anon », clé de session propre à cet outil |
| `vercel.json` | pages non indexées par les moteurs de recherche |

## Règles de séparation

- Le code n'appelle que des tables et fonctions **`oc_*`** : toute autre table est refusée avant l'appel à la base.
- L'Observatoire actuel n'est lu qu'au travers des fonctions de lecture `oc_sites_commune`, `oc_priorite_communes`, `oc_sites_a_verifier`.
- Session de connexion distincte (`aquiklin-oc-auth`) : se connecter ici ne change rien dans l'Observatoire.

## Prérequis base (Supabase, éditeur SQL)

Scripts `oc_02`, `oc_03`, `oc_05`, `oc_07`, `oc_09`, `oc_10` exécutés (dans cet ordre), contrôle `oc_00` identique avant/après.

## Déploiement

1. Déposer les 3 fichiers à la racine du dépôt GitHub `aquiklin-observatoire-communes` (« Add file → Upload files »).
2. Vercel → « Add New… → Project » → importer ce dépôt → Framework : **Other** → Deploy (aucun réglage de build).
3. Ouvrir l'adresse fournie par Vercel et se connecter avec le compte administrateur habituel.

## Utilisation

Tableau de prospection → commune → vérifier les sites → vérifier le destinataire → préparer le courriel → relire, valider → copier dans la messagerie → « J'ai envoyé ce courriel ».
