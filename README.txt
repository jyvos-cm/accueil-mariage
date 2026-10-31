# ACCUEIL MARIAGE — Professional Edition

## Contenu
- `index.html` : application web responsive bleu nuit & or.
- `supabase_schema.sql` : tables, rôles, règles d'accès (RLS), fonctions de création d'événement et d'ajout d'agents.
- `README.txt` : ce guide.

## Fonctions incluses
- Comptes utilisateurs par e-mail et mot de passe.
- Création d'un événement de mariage.
- Tableau de bord : inscrits, présents, attendus et taux de présence.
- Gestion des invités : ajout, recherche, filtre et validation/annulation d'arrivée.
- Synchronisation temps réel des arrivées entre appareils connectés.
- Import groupé de noms copiés depuis WhatsApp ou d'un fichier CSV/TXT.
- Ajout d'agents par adresse e-mail (l'agent doit d'abord créer son compte).
- Export CSV compatible avec Excel.
- Accès séparé administrateur / agent et règles RLS dans Supabase.

## Mise en service en ligne (nécessaire pour le multi-téléphone)
1. Créez un projet sur https://supabase.com (offre gratuite possible selon les limites et conditions du service).
2. Dans le projet, ouvrez **SQL Editor** > **New query**.
3. Copiez tout le contenu de `supabase_schema.sql`, exécutez-le.
4. Dans **Project Settings > API**, copiez le **Project URL** et la clé publique **anon** (ou publishable). Ne copiez jamais la clé `service_role`.
5. Ouvrez `index.html` dans un navigateur connecté à Internet. À l'écran de configuration, collez le Project URL et la clé publique.
6. Créez le premier compte. Si la confirmation e-mail est activée dans Supabase, confirmez l'adresse avant de vous connecter.
7. Créez votre mariage depuis l'écran de première configuration.
8. Pour chaque agent : demandez-lui d'ouvrir la même application, de créer son compte, puis depuis votre compte administrateur > Équipe d'accueil, ajoutez son e-mail.
9. Hébergez `index.html` sur un hébergeur HTTPS statique (par exemple GitHub Pages, Netlify ou Vercel) et ouvrez exactement la même adresse sur les téléphones des agents.

## Import WhatsApp
- WhatsApp > conversation/groupe > menu > Plus > Exporter discussion > Sans médias, ou copiez directement les noms.
- Dans l'application, ouvrez **Importer WhatsApp**.
- Collez un nom par ligne, prévisualisez puis confirmez.
- Les lignes identiques déjà présentes sont ignorées. Vérifiez les noms avant confirmation : un export de discussion complet contient aussi des messages qui ne sont pas des noms.

## Limites et précautions
- Cette version est un socle fonctionnel prêt à connecter, pas un service déjà hébergé ni une base déjà créée pour vous.
- La synchronisation en ligne ne fonctionne qu'après configuration d'un projet Supabase et hébergement de l'application.
- Le compte administrateur doit être créé en premier. Les agents doivent créer leur compte avant d'être ajoutés.
- Les données sont hébergées dans le projet Supabase que vous contrôlez. Protégez les comptes et n'envoyez jamais votre clé `service_role`.
- Faites un test avec deux téléphones et quelques invités fictifs avant le jour du mariage.
- La version actuelle importe des noms en masse et gère le pointage; les QR codes individuels, scan caméra et SMS/WhatsApp automatiques peuvent être ajoutés dans une prochaine version.
