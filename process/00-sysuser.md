## Utilisateur système

- [ ] Création
- [ ] Suspension
- [ ] Attribution de rôle

### Processus

#### Création

* Un _**utilisateur système**_ est un acteur majeur du système d’information.
* Une adresse de messagerie lui est attribuée satisfaisant le modèle _**prénom.nom@[domaine]**_
* L’adresse est un _**alias**_ dirigeant le flux vers l’adresse qu’il aura communiqué.
* Le rôle _**sysuser**_ est attribué par défaut.
* Les autres rôles sont attribués en fonction des responsabilités qui lui incombent.
* Les éléments d’identité sont transmis au système.
* Le système vérifie la cohérence des chaînes de caractère selon les standards décidés, puis procède à une mise au format désiré.
* Un alias de compte e-mail est créé.
* Un compte est créé au sein du logiciel de communication (slack ou équivalent)
* Un message électronique est transmis à l’utilisateur résumant les actions menée et à réaliser.

```json
// Enregistrement type d'un nouvel utilisateur
user_record = {
  "first_name": "user first name",
  "last_name": "user last name",
  "titre": "M.,Mme,Mlle",
  "email_forwarding": "choosen destination email",
  "username": "computed user account regex lower case ",
  "email": "corporate email",
  "dob": "birthday",
  "choosen_roles": ["a", "b", "c"]
}
```
