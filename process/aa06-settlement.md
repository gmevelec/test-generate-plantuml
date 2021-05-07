## Réglement

- [] Create réglement
- [] Modify réglement
- [] Delete réglement
- [] Statuts réglement

### Processus

#### Create réglement


#### Modify réglement


#### Delete réglement



```plantuml
@startuml
scale 650 width
title Diagramme de séquences ""
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
  API -> Messagerie: Send activation "mail"
  API -> IHM: new user + account
  IHM -> User: Afficher page profile
else Registration refused
  API <- db: save failed
  API -> IHM: res: refused + reason
  IHM -> User: Afficher erreurs
end
@enduml
```

### Status

Les status de l'objet
