# Script vidéo - SPEC-1

## Alignement avec `New_training_content.md`

"Il n'y a pas de section `Script —` dédiée à cet exercice dans le contenu source. Ce script est donc aligné sur la section Hands On Specification & Architecture, en particulier l'exercice `Writing Specifications with AI`."

## Concept couvert

"Ce Hands On illustre la phase Specification de l'AIDLC. L'idée clé est que l'IA produit de meilleurs résultats quand le besoin est formulé comme un contrat clair."

"Avant de demander du code à un agent, il faut transformer une demande métier ou une user story en exigences structurées, testables et non ambiguës. Copilot est utilisé ici comme assistant de clarification, pas comme générateur de code."

"Le message pédagogique à faire passer est important : une mauvaise specification donne souvent un mauvais résultat, même avec un très bon modèle. L'agent peut accélérer la rédaction, mais il ne peut pas deviner les règles métier qui n'ont pas été exprimées. Notre rôle est donc de cadrer, préciser, challenger et valider."

"Dans la logique AIDLC, cette étape évite de déplacer l'ambiguïté vers les phases suivantes. Une ambiguïté dans une user story devient un choix d'architecture incertain, puis du code fragile, puis des tests incomplets. C'est pour cela que l'on investit du temps ici."

## Mise en situation

"Nous partons d'une user story très simple : créer une API REST de gestion de tâches. Le besoin est volontairement incomplet : il manque les statuts HTTP, les règles de validation, les formats attendus et les erreurs."

"À l'écran, montrez le fichier `user-story.md`. Prenez quelques secondes pour lire les éléments disponibles : title, description, priority, status, due date, opérations CRUD et filtres. Expliquez que c'est une base acceptable pour discuter, mais insuffisante pour développer ou tester."

"Soulignez les questions ouvertes : que se passe-t-il si le title est vide ? quels codes HTTP doit-on retourner ? le filtrage par status et priority est-il combiné en AND ou en OR ? le due date accepte-t-il n'importe quelle chaîne ou seulement un format précis ?"

## Démonstration du début

"Je commence par ouvrir `user-story.md`. Je le copie dans Copilot Chat en Plan Mode, puis je demande à Copilot de le transformer en exigences fonctionnelles organisées par endpoint."

"Je ne m'arrête pas à la première réponse. Je demande ensuite d'ajouter les contraintes REST, les formats JSON, les codes HTTP et les critères d'acceptation."

"Pendant la démonstration, insistez sur la formulation du prompt. On ne dit pas seulement : 'write a spec'. On précise la structure attendue : Overview, Data model, Endpoints, Error handling, Constraints. Cette structure aide Copilot à produire un document exploitable."

"Après la première génération, montrez comment relire. Cherchez les exigences vagues, par exemple 'handle errors correctly'. Expliquez qu'une bonne exigence doit pouvoir être transformée en test. Si elle ne peut pas être testée, elle doit être réécrite."

"Montrez aussi comment itérer : demandez à Copilot de clarifier les champs obligatoires, les valeurs autorisées pour `priority` et `status`, les erreurs 400 et 404, et les réponses attendues pour chaque endpoint."

## Consignes pour l'exercice

"Votre objectif est de produire `spec.md`. La specification doit être claire, testable et suffisamment précise pour servir d'entrée à l'exercice suivant, qui portera sur le design technique."

"À la fin de l'exercice, relisez votre specification comme si vous étiez un développeur qui doit implémenter sans poser de question. Si vous hésitez, c'est que la specification doit encore être améliorée."

"Relisez-la aussi comme si vous étiez QA. Pour chaque exigence, demandez-vous : quel test permet de prouver que cette règle est respectée ? Si aucun test évident n'existe, demandez à Copilot de reformuler l'exigence."

## Points d'attention à montrer à l'écran

"Montrez les différences entre la user story initiale et la specification finale. La valeur de l'exercice se voit dans cette transformation : on passe d'un besoin court et ouvert à un document structuré."

"Montrez au moins un exemple d'ambiguïté corrigée. Par exemple : 'list tasks with filters' devient 'GET /tasks accepts optional query parameters status and priority; when both are present, filters are combined with AND'."

"Montrez enfin que le fichier `spec.md` est sauvegardé dans le repo. Ce fichier devient l'entrée du Hands On suivant."

## Conclusion

"Ce premier Hands On pose la base de tout le reste. Dans un workflow agentique, la specification est le premier garde-fou. Plus elle est claire, plus l'agent pourra produire un design, du code et des tests cohérents."

"Le réflexe à retenir : avant de demander à l'IA de construire, demandez-lui d'abord d'aider à clarifier ce qui doit être construit."
