
---

### **Étape 4 : Partie 4 - Workflow n8n**

**Fichier :** `partie_4_n8n_workflow/documentation.md`

```markdown
# PARTIE 4 : Workflow d'Automatisation n8n - Gestion des Leads par IA

## 1. Objectif du Workflow

Créer un système automatisé de gestion de leads. Lorsqu'un prospect remplit un formulaire de contact, le workflow doit :
1.  Capturer les données.
2.  Les enregistrer dans une feuille Google Sheets.
3.  Classifier automatiquement le lead (Haute/Moyenne/Basse priorité) en fonction du budget et de la description.
4.  Générer une réponse personnalisée par IA (OpenAI) à envoyer au prospect.
5.  Notifier l'équipe commerciale par email avec les détails du lead et la classification.
6.  Maintenir un tableau de bord des leads dans Google Sheets.

## 2. Architecture Conceptuelle

Le workflow suit une logique simple, robuste et évolutive :

1.  **Déclencheur (Trigger) :** Un Webhook n8n reçoit les données du formulaire (simulé ici par une requête HTTP). Cela simule la soumission d'un Google Form ou d'un formulaire de site web.
2.  **Stockage (Storage) :** Les données brutes sont immédiatement sauvegardées dans une feuille **Google Sheets** ("Leads Bruts") pour avoir une trace de toutes les entrées.
3.  **Traitement (Processing) :**
    *   Le workflow utilise un nœud **"IF"** pour une classification initiale basée sur le budget (logique simple : budget > 5M = Haute, > 1M = Moyenne, sinon Basse).
    *   Parallèlement, un nœud **"HTTP Request"** appelle l'**API OpenAI (GPT)** avec un prompt ingénieuré pour analyser la description du besoin, confirmer/ajuster la priorité et extraire des mots-clés.
4.  **Notification & Feedback :**
    *   Un nœud **"Gmail"** envoie un email de remerciement personnalisé au prospect, intégrant la réponse générée par l'IA.
    *   Un second nœud **"Gmail"** envoie une notification à l'équipe commerciale avec la priorité, les mots-clés et un lien vers la feuille de suivi.
5.  **Mise à jour (Update) :** Enfin, un nœud **"Google Sheets"** met à jour la ligne du lead avec la priorité finale, les mots-clés et le statut "Traité".

## 3. Justification des Choix Techniques

*   **n8n (Version gratuite/Community) :** Choisi pour sa flexibilité, sa nature "low-code" qui permet un développement rapide, et sa capacité à s'auto-héberger ou à utiliser une version cloud gratuite. Il excelle dans l'orchestration de multiples services (API, Sheets, Email).
*   **Google Sheets :** Utilisé comme "source de vérité" simple et accessible. Il fait office à la fois de base de données et de tableau de bord visuel. C'est gratuit et collaboratif.
*   **OpenAI API :** Utilisé pour l'analyse du langage naturel. Le modèle GPT (via `gpt-3.5-turbo` ou similaire) est capable de comprendre la description du besoin, d'en extraire le sujet et de justifier/ajuster la priorité de manière plus nuancée qu'une simple règle sur le budget. Le prompt est conçu pour forcer une sortie structurée (JSON) facile à traiter.
*   **Gmail :** Choisi pour sa fiabilité et sa gratuité pour l'envoi d'emails transactionnels et de notifications.

## 4. Gestion des Erreurs (Robustesse)

*   Le nœud "OpenAI" est configuré avec un paramètre `Continue on Fail` activé. Si l'API OpenAI est indisponible, le workflow continue et le lead est tout de même enregistré avec la priorité basée sur le budget et une notification interne indiquant l'erreur.
*   Le nœud "Gmail" pour le prospect est également en `Continue on Fail` pour éviter de bloquer le workflow si l'email est invalide.
*   Un nœud "Execute Workflow" séparé pourrait être ajouté pour les notifications critiques à l'équipe, mais pour ce test, la simplicité est privilégiée.

## 5. Instructions de Configuration (pour reproduire)

1.  **n8n :** Installer n8n localement ou utiliser n8n.cloud.
2.  **Credentials :** Configurer les identifiants dans n8n pour :
    *   **Google Sheets** (via OAuth).
    *   **Gmail** (via OAuth).
    *   **OpenAI** (via une clé API, à obtenir sur platform.openai.com).
3.  **Importer le Workflow :** Créer un nouveau workflow dans n8n, importer le fichier `lead_manager_workflow.json`.
4.  **Ajuster les IDs :** Modifier l'ID de la feuille Google Sheets dans les nœuds Google Sheets pour pointer vers VOTRE feuille.
5.  **Activer :** Activer le workflow. Le Webhook est maintenant actif.

**Exemple de payload pour tester le Webhook :**
```json
[
  {
    "name": "Darlin Kuajo",
    "email": "darlin.k@email.com",
    "company": "Inperfect",
    "budget": "15000000",
    "description": "Nous cherchons à automatiser le suivi de nos leads avec une solution IA et à intégrer cela à notre CRM interne."
  }
]
```

## 6. Lien et Fichier
Le workflow exporté est disponible dans ce même dossier : lead_manager_workflow.json