# Exercices JavaScript — HTML et JavaScript interactifs

## Exercice 1 — Vérificateur de palindrome (basique)
**Énoncé**  
Créer une page HTML avec :  
- Un `<input>` pour saisir la chaîne.  
- Un `<button>` pour lancer la vérification.  
- Un `<p>` pour afficher le résultat : "Palindrome" ou "Pas un palindrome".  
Écrire la fonction `isPalindrome(str)` en JavaScript qui retourne true si str est un palindrome exact, false sinon.

**Logique étape par étape (HTML + JS)**  
1. Créer la structure HTML : `<input id="palindromeInput">`, `<button id="checkBtn">`, `<p id="result">`.  
2. Récupérer les éléments dans JS avec `document.getElementById()`.  
3. Ajouter un événement `click` sur le bouton.  
4. Dans la fonction de vérification :  
   - Récupérer la valeur de l’input.  
   - Transformer en tableau (`split('')`), inverser (`reverse()`), reformer une chaîne (`join('')`).  
   - Comparer avec la chaîne originale.  
5. Mettre à jour le `<p>` avec le résultat.  
6. Gérer les cas où l’input est vide.

---

## Exercice 2 — Vérificateur de palindrome (normalisé)
**Énoncé**  
Créer une page HTML similaire à l’Exercice 1.  
Écrire `isPalindromeNormalized(str)` qui ignore la casse, les espaces et la ponctuation.

**Logique étape par étape (HTML + JS)**  
1. Même structure HTML que l’Exercice 1.  
2. Récupérer la valeur de l’input.  
3. Normaliser la chaîne : `toLowerCase()`.  
4. Supprimer caractères non alphanumériques via regex.  
5. Inverser la chaîne nettoyée et comparer avec l’original.  
6. Afficher le résultat dans un `<p>`.

---

## Exercice 3 — Manipulations de chaîne
### 3.1 Inversion des mots
**Énoncé**  
Créer une page HTML avec un `<input>` et un `<p>` pour afficher le résultat.  
Écrire `reverseWords(sentence)` pour inverser l’ordre des mots.

**Logique HTML + JS**  
1. Split par espace (`split(/\s+/)`).  
2. Inverser le tableau (`reverse()`).  
3. Rejoindre en chaîne (`join(' ')`).  
4. Afficher le résultat.

### 3.2 Comptage des voyelles
**Énoncé**  
Créer un `<input>` et `<p>` pour afficher le nombre de voyelles avec `countVowels(str)`.

**Logique HTML + JS**  
1. Passer la chaîne en minuscules (`toLowerCase()`).  
2. Trouver les voyelles avec regex (`match(/[aeiouy]/g)`).  
3. Retourner le nombre de correspondances ou 0.  
4. Afficher le résultat dans le `<p>`.

---

## Exercice 4 — Nombres impairs
### 4.1 Extraction d’impairs
**Énoncé**  
Créer un `<input>` ou `<textarea>` pour entrer un tableau, `<p>` pour afficher le résultat.  
Écrire `filterOdds(arr)`.

**Logique HTML + JS**  
1. Récupérer la saisie et transformer en tableau.  
2. Filtrer les impairs (`num % 2 !== 0`).  
3. Afficher le résultat.

### 4.2 Génération d’impairs
**Énoncé**  
Créer un `<input>` pour le nombre d’éléments `n` et `<p>` pour le résultat.  
Écrire `generateOdds(n, start = 1)`.

**Logique HTML + JS**  
1. Initialiser tableau vide et variable `current = start`.  
2. Tant que tableau < n : push si impair, incrémenter `current`.  
3. Afficher le résultat.

---

## Exercice 5 — Nombres aléatoires
### 5.1 Entier aléatoire
**Énoncé**  
Page HTML avec `<input>` pour min/max, `<p>` pour résultat.  
Écrire `randomInt(min, max)`.

**Logique HTML + JS**  
1. Récupérer min et max.  
2. `Math.random() * (max - min + 1)` + `Math.floor() + min`.  
3. Afficher le résultat.

### 5.2 Tirage sans répétition
**Énoncé**  
Même structure HTML.  
Écrire `uniqueRandoms(count, min, max)`.

**Logique HTML + JS**  
1. Vérifier que count <= max-min+1.  
2. Créer Set vide.  
3. Boucler et ajouter nombres aléatoires au Set jusqu’à count.  
4. Convertir en tableau et afficher.

---

## Exercice 6 — Incrémentation panier (localStorage / cookies)
**Énoncé**  
Créer une page HTML avec `<button>` pour incrémenter un produit et `<p>` pour afficher le panier.  
Écrire `incrementCartItem(productId)` avec support **localStorage** et **cookies**.

**Logique HTML + JS**  
1. Récupérer panier depuis localStorage ou cookies.  
2. Si inexistant → {}.  
3. Si productId existe : incrémenter, sinon mettre 1.  
4. Sauvegarder dans localStorage ou cookies.  
5. Afficher le panier mis à jour.  
6. Gérer exceptions JSON, max-age et synchronisation multi-onglets.
