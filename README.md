# Investigating an Attachment Lab

Dans ce lab, j'ai analysé un fichier HTML malveillant attaché à un email de phishing.

---

## Question 1 — Nom du fichier

![Q1]({D0104A27-46AC-4F45-8576-55F8B33C5AB2}.png)

---

## Question 2 — SHA256 Hash

![Q2]({2CF623C5-EA05-45E2-B64D-EF8DB306C0D6}.png)

---

## Question 3 — Taille du fichier (KB)

![Q3]({A5AE15F3-2A70-4705-A8A9-E9436E47D1CE}.png)

---

## Question 4 — Quelle compagnie est imitée ?

![Q4]({A43560A1-0508-467B-8CEF-37C9591F502D}.png)

Le fichier imite la page de connexion Microsoft Outlook / Office365.

---

## Question 5 — Quelle victime est ciblée ?

![Q5]({0296BC6B-1253-4A9B-8EBD-7E8F1A4BEF87}.png)

---

## Question 6 — Nom du logo Microsoft trouvé dans le code source

![Q6]({800C9CA1-75CC-446E-84C2-5DE2F30C55A7}png)

Pour trouver ça j'ai copié le code source dans CyberChef, appliqué URL Decode, puis cherché "logo" avec CTRL+F.

---

## Question 7 — URL utilisée pour envoyer les credentials au serveur

![Q7]({C7239FD7-965D-4B1F-8FE0-2E2650C5E1EF}.png)

En ouvrant les Developer Tools sur l'onglet Network et en entrant un faux mot de passe, on peut voir l'URL complète avec l'email et le mot de passe dedans — c'est comme ça que l'attaquant récupère les infos.

---

## Outils utilisés

- PowerShell (Get-FileHash)
- Google Chrome (View Source + Developer Tools)
- CyberChef (URL Decode)

---

## Ce que j'ai appris

- Hasher un fichier suspect avec PowerShell
- Analyser le code source d'une fausse page de login
- Utiliser CyberChef pour décoder du contenu URL encodé
- Voir comment les credentials sont volés via une requête réseau
