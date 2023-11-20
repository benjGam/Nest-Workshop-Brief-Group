# API interne pour une Médiathéque

Vous devez créer une API pour les employés d'une médiathèque, ces employés doivent référencés chaque livre sur le site de la médiathèque pour examiner les disponibilités des livres.

## Spécifications fonctionnelles

## Employés

- Les employés doivent être composés des champs :
  - UUID (De type VARCHAR et de longueur 36 (minimale et maximale))
  - Un prénon (De type VARCHAR et de longueur 20 (maximale))
  - Un nom de famille (De type VARCHAR et de longueur 30 (maximale))

## Livres

- Les livres doivent être composés des champs :
  - UUID (De type VARCHAR et de longueur 36 (minimale et maximale))
  - Un nom (De type VARCHAR et de longueur 40 (maximale))
  - Une description (De type TEXT et de longueur 500 (maximale))
  - L'UUID d'un autheur

## Autheurs

- Les autheurs doivent être composés des champs :
  - UUID (De type VARCHAR et de longueur 36 (minimale et maximale))
  - Un prénon (De type VARCHAR et de longueur 20 (maximale))
  - Un nom de famille (De type VARCHAR et de longueur 30 (maximale))

## Emprunteurs

- Les emprunteurs doivent être composés des champs : 
  - UUID (De type VARCHAR et de longueur 36 (minimale et maximale))
  - Un prénon (De type VARCHAR et de longueur 20 (maximale))
  - Un nom de famille (De type VARCHAR et de longueur 30 (maximale))
  
## Emprunts

- Les emprunts doivent être composés des champs :
  - UUID (De type VARCHAR et de longueur 36 (minimale et maximale))
  - L'UUID d'un livre (De type VARCHAR et de longueur 36 (minimale et maximale))
  - L'UUID d'un emprunteur (De type VARCHAR et de longueur 36 (minimale et maximale))
  - Une date de début (De type DATE)
  - Une date de fin (De type DATE)

## Spécifications techniques

- Les erreurs d'accession aux données via `Prisma` doivent être automatiquement gérées et renvoyées des réponses claires expliquant la raison de l'erreur sans encombrer les logs de l'API en plus, le code de status de la réponse doit être celui correspondant à l'erreur survenue. Vous devez coder ce système grâce à un intercepteur.