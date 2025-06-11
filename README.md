🧾 Extracteur Automatisé de Factures
Ce projet a pour objectif de recevoir une facture via un formulaire web, extraire les données clés automatiquement grâce à un workflow n8n intégrant l'IA d'OpenAI, puis envoyer un résumé structuré par email.

🚀 Fonctionnalités
Upload de facture via un formulaire web

Analyse automatique (résumé et structuration)

Extraction des éléments clés (client, montant, date, contrat, etc.)

Envoi par mail formaté (HTML) au client

Historisation simple via Simple Memory dans n8n

🧰 Technologies utilisées
Technologie	Rôle
n8n	Orchestration du workflow
OpenAI API	Résumés & extraction intelligente
Gmail API	Envoi de l'email contenant le résumé
Webhook HTTP	Réception du fichier depuis le site web
Formulaire Web (React ou autre)	Interface utilisateur de dépôt de facture

🔁 Fonctionnement du Workflow

Webhook : Réception du fichier (PDF, image) et des métadonnées utilisateur.

HTTP Request : Transmission vers un service OCR si nécessaire (optionnel).

Split Out : Nettoyage ou prétraitement des données.

Summarize : Création d'un résumé global par GPT.

Basic LLM Chain : Extraction de champs spécifiques (client, date, produits, etc.)

AI Agent : Orchestration et gestion des tâches multiples avec mémoire.

Gmail : Envoi du mail résumé structuré au format HTML.

📥 Interface utilisateur

L'utilisateur :

Renseigne son nom et email

Dépose la facture

Reçoit un email automatique contenant le résumé structuré

✉️ Exemple d’e-mail généré
html
Copier
Modifier
Objet : Résumé de votre facture

Bonjour [Prénom],

Voici un résumé de votre facture :

<table>
  <tr><th>Client</th><td>Entreprise X</td></tr>
  <tr><th>Date</th><td>10/06/2025</td></tr>
  <tr><th>Montant</th><td>1 240 €</td></tr>
  <tr><th>Produits</th><td>...</td></tr>
</table>

Cordialement,<br>
HDAutomatisation.
🔒 Sécurité & RGPD
Aucune donnée n'est stockée au-delà du traitement.

Autorisation explicite requise dans le formulaire.

Données envoyées uniquement par email sécurisé.

✅ Prérequis
Un compte n8n avec accès à l’éditeur

Clé API OpenAI

Compte Gmail configuré avec OAuth 2.0

Hébergement d'un formulaire HTML

📦 Installation (dev)
bash
Copier
Modifier
# Clone le repo
git clone https://github.com/YassineElabdaoui/Agent_ia_GD.git
cd Agent_ia_GD

# (optionnel) Démarrer n8n en local
n8n start
🤖 Pour contribuer
Fork le projet

Crée une branche feature/...

Commit et push

Ouvre une pull request !
