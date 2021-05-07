## Comptes

- [ ] SignUp
- [ ] SignIn
- [ ] SignOut
- [ ] Statut

### Processus

#### SignUp

Un utilisateur non identifié peut créer un compte. Selon le contexte, l'application propose à l'utilisateur de choisir sa [casquette](../objects/dictionnaire.md)

Lorsque l'utilisateur se déconnecte, l'ensemble des opérations enregistrées sur le poste client sont effacées.


```plantuml
@startuml
title Diagramme de séquences "SigUp"
scale 650 width
hide footbox

actor User
User -> IHM: SignUp
Activate IHM
IHM -> User: Composant SignUp
User -> IHM: Submit
Activate IHM
IHM -> API: POST
Activate API
API -> db: save user + account
alt Registration accepted
  API <- db: save succeed
  API -> Messagerie: Send activation mail
	API -> IHM: new user + account
  IHM -> User: Afficher page profile
else Registration refused
  API <- db: save failed
	API -> IHM: res: refused + reason
  IHM -> User: Afficher erreurs
end
@enduml
```

#### SignIn

L'utilisateur saisit les données d'identification. L'identifiant de connexion est soit :
- [nom d'utilisateur](../objects/dictionnaire.md#username)
- email
- numéro de téléphone (à réaliser)
- via délégation d'identification ([oAuth](../objects/dictionnaire.md#oauth))

Lorsque que l'utilisateur se connecte, les éléments de connexion sont transmis à l'API.


```plantuml
@startuml
title Diagramme de séquences "SignIn"
scale 650 width
hide footbox

actor User
User -> IHM: SignIn
Activate IHM
IHM -> User: Composant SignIn
User -> IHM: Submit
Activate IHM
IHM -> API: Submit
Activate API
API -> db: find user
alt Connection accepted
  API <- db: user found and credentials ok
	API -> IHM: new user + account
  IHM -> User: Afficher page profile
else Connection refused
  API <- db: user not found
	API -> IHM: res: refused + reason
  IHM -> User: Afficher erreurs
end
@enduml
```

#### SignOut

La déconnexion d'un utilisateur provoque la suppression des éléments d'identification de l'utilisateur dans l'interface.

### Status

