# PRG08 Week 5 Oefening 1

## Chickens versus Zombies

![Chickens](docs/images/runchickenrun.png?raw=true "Run chicken, run")

## Startcode

- Er is een game met zombies en een kip
- De zombies bewegen richting de kip
- Als je in het scherm klikt beweegt de kip naar die locatie
- De collision detection functie kijkt of een kip een zombie raakt
- Als je op de kip klikt pakt hij zijn telefoontje

## Opdracht 1

- Maak van de chicken een Subject, zie UML
- Maak van de zombies Observers, zie UML
- De zombies abbonneren zich op de chicken zodra ze aangemaakt worden
- Als je op de kip klikt stuurt hij een notificatie naar alle zombies
- Als de zombies een notificatie krijgen stoppen ze met bewegen en krijgen ze de andere zombie texture

## Opdracht 2

- De zombies gaan na een pauze weer bewegen, en krijgen dan ook weer de beweging texture

## Opdracht 3

- Voeg graan en telefoontjes toe aan het scherm
- Gebruik de collision detection functie om te zien of je graan of telefoontjes raakt
- Als de kip graankorrels oppakt krijg je punten
- Het aantal telefoontjes dat je hebt opgepakt, bepaalt hoe vaak je op de kip mag klikken om de zombies een berichtje te sturen
- Gebruik de 'removeFromGame' functie in util om graan en telefoons uit de game te verwijderen

## Observer Pattern

Dit code voorbeeld toont een Observer Pattern met een Shop en een User.

Een User krijgt als argument de shop binnen, zodat de user zich kan subscriben op de shop.
De Shop houdt een lijst van Users bij. Als er iets verandert in de Shop, dan krijgen alle users een notificatie.

```
interface Observer {
    notify():void
}

interface Subject {
    observers:Observer[]
    subscribe(o:Observer):void
    unsubscribe(o:Observer):void
}

class User implements Observer {
    constructor(s:Subject){
        s.subscribe(this)
    }
    notify(){
        console.log("I got an update from the shop!")
    }
}

class Shop implements Subject {
    private observers:Observer[]
    public subscribe(o:Observer):void {
        this.observers.push(o)
    }
    public unsubscribe(o:Observer):void {
        // remove o from this.observers
    }
    
}
```
## UML Observer pattern

![UML](docs/images/observer.png?raw=true "UML")


### Texture veranderen

```
this.div.style.backgroundImage = "url('images/zombie.png')";
```
