1. Un prospect remplit le **formulaire Google**
2. La réponse est stockée dans **Google Sheets**
3. **n8n détecte** automatiquement la nouvelle ligne
4. Le **budget** est analysé pour définir la priorité
5. **OpenAI** analyse la description et extrait des mots-clés
6. Les **résultats sont enregistrés** dans Google Sheets
7. **Emails envoyés** : confirmation au prospect + notification à l'équipe

---

## 🔧 Configuration requise

### Comptes nécessaires

- **Google** (Forms, Sheets, Gmail) - gratuit
- **OpenAI** (clé API avec crédits)
- **n8n** (version cloud gratuite)

### Identifiants à configurer dans n8n

- Google Sheets (trigger et update)
- Gmail (envoi des emails)
- OpenAI (via headers HTTP)

---

## 📦 Fichier du workflow

**Nom du fichier :** `lead_manager_workflow.json`

**Comment l'utiliser :**

1. Dans n8n, cliquez sur **"Import from File"**
2. Sélectionnez ce fichier JSON
3. Configurez vos propres identifiants (Google, OpenAI)
4. Activez le workflow

---

## 📝 Description des nœuds

| Nœud                            | Type                  | Rôle                                        |
| ------------------------------- | --------------------- | ------------------------------------------- |
| **📥 Détection nouveau lead**   | Google Sheets Trigger | Surveille les nouvelles réponses            |
| **⚙️ Classification budget**    | Code (JS)             | Calcule la priorité (Haute/Moyenne/Basse)   |
| **🤖 Analyse IA (OpenAI)**      | HTTP Request          | Appelle GPT-4o pour analyser la description |
| **🔧 Extraction mots-clés**     | Code (JS)             | Extrait et formate les mots-clés            |
| **📝 Enregistrement résultats** | Google Sheets Update  | Met à jour la ligne avec les résultats      |
| **📧 Email prospect**           | Gmail Send            | Accusé de réception au client               |
| **📨 Notification équipe**      | Gmail Send            | Alerte l'équipe commerciale                 |

---

## 📊 Logique de classification

| Budget                     | Priorité       |
| -------------------------- | -------------- |
| > 5 000 000 FCFA           | 🔴 **Haute**   |
| 1 000 000 - 5 000 000 FCFA | 🟠 **Moyenne** |
| < 1 000 000 FCFA           | 🟢 **Basse**   |

---

## 🧪 Exemple de fonctionnement

**Soumission :**

- Nom : Jean Dupont
- Budget : 2 500 000 FCFA
- Description : "Recherche d'un CRM pour 20 personnes"

**Résultat :**

- Priorité : **Moyenne** 🟠
- Mots-clés : "CRM, équipe 20 personnes"
- Email envoyé au prospect
- Notification envoyée à l'équipe

---

## ⚠️ Notes importantes

- Le workflow doit être **activé** pour fonctionner
- La détection se fait **toutes les minutes** (polling)
- La clé API OpenAI est à remplacer par la vôtre
- Les IDs Google Sheets sont déjà configurés

---

## 📧 Contact

**Candidat :** Darlin Kuajo  
**Test pour :** Financial House S.A  
**Date :** 23 Février 2026

---

**✅ Workflow prêt à l'emploi**
