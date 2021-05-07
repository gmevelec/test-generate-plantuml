---
marp: true
---

## Configuration système

### Processus

#### Configuration

* Au chargement les _**données standards initiales**_ sont récupérées depuis le référentiel _**settings**_
* Les _**données standards initiales**_ appartiennent à _**account_id = 0**_
* Lors des événements de connexion et déconnexion les _**données standards initiales**_ sont chargées.
* Si des données de configurations spécifiques au compte utilisateur doivent être stockées seuls les deltas seront pris en compte dans le payload.
* Par principe, les données propres à un compte utilisateur ont un _**poids supérieur**_ aux _**données standards initiales**_.

---
## Slide encore

---

## Slide après

||
| * point 1 | * point 2 |
| * point 1 | * point 2 |
| * point 1 | * point 2 |
| * point 1 | * point 2 |
| * point 1 | * point 2 |
| * point 1 | * point 2 |