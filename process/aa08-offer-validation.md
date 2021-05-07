## Validation d'offre

- [] Create offer validation
- [] Modify offer validation
- [] Delete offer validation
- [] Statuts offer validation

### Processus

#### Create offer validation


#### Modify offer validation


#### Delete offer validation



```plantuml
@startuml
scale 650 width
title Diagramme d'états "+-+-+-+-+-+-+-+"
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
