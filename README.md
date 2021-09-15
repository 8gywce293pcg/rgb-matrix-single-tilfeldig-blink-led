### @explicitHints false

## Introduksjon @unplugged
Her vil du lære å kode våre kule LED displayer. 
Målet er å få en tilfeldig LED til å blinke ved bruk av en variabel


## Steg 1: Definer noen neopixler @fullscreen
 Trykk på ``||Neopixel:Neopixel||`` fra blokkmenyen.
 Klikk og dra inn blokken ``||Neopixel:sett strip til||`` og slipp den inn i ``||basic:ved start||`` blokken.
 Velg pinne ``||Neopixel:P0||`` og antall LED til ``||Neopixel:768||`` la format stå som ``||Neopixel:RGB (GRB)||``.
 Denne blokken brukes for å velge hvilken pinne som er koblet til LED, hvor mange LED det er og hvilken type LED. 

```blocks

let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)

```
## Steg 2: Slette minne i LED
Trykk på ``||Neopixel:Neopixel||`` fra blokkmenyen.
Klikk og dra inn blokken ``||Neopixel:strip.clear||`` plasser den under forrige blokk.
Denne blokken sletter tidligere data inni lysdidodene.

```blocks

let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()

```
## Steg 3: Lage en variabel for å få en tilfeldig verdi
Trykk på ``||Variabler: variabel||`` fra blokkmenyen og klikk deretter ``||Variabler:lag en variabel||`` og gi variabelen navnet ``||Variabler:TILFELDIG LED||``.
Trykk på ``||Variabler: variabel||``, klikk og dra blokken ``||Variabler: Sett TILFELDIG LED||`` inn i ``||basic:gjenta for alltid||``.
Trykk på ``||Math: Matematikk||`` og sett denne inni blokken ``||Variabler: Sett TILFELDIG LED||`` i verdien 0.
Sett Verdiene ``||Math:0 til 767||``.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
   TILFELDIG_LED = randint(0, 767)
})
```

## Steg 4: Sette opp tilfeldig LED med en farge
Trykk på ``||Neopixel: Neopixel||`` fra blokkmenyen og klikk deretter ``||Neopixel: mer||``.
Klikk og dra inn blokken ``||Neopixel:strip set_Pixel_Color at 0 to Red||`` plasser nederst i ``||basic: gjenta for alltid||``. 
Trykk på ``||Variabler:Variabler||`` deretter klikk og dra inn blokken ``||Variabler:TILFELDIG LED||`` inn i  blokken ``||Neopixel:strip set_Pixel_Color at 0 to Red||`` i verdien 0.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    TILFELDIG_LED = randint(0, 767)
    strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Red))
    
})
```

## Steg 5: Send informasjon til Neopixlene
Trykk på ``||Neopixel:Neopixel||`` fra blokkmenyen.
Klikk og dra inn blokken ``||Neopixel:strip.show||`` plasser den under forrige blokk.
Denne blokken sender hvilken LED nummer og farge til LEDène som skal lyse.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    TILFELDIG_LED = randint(0, 767)
    strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Red))
    strip.show()
   
})
```
## Steg 6: Hvor lenge skal lysdidoen lyse
Trykk på ``||basic:Basis||`` fra blokkmenyen.

Velg ``||basic.pause||`` og plaser denne under forrige blokk i ``||basic: gjenta for alltid||``.

Sett pausen verdien til 1000 millisekunder som er 1 sekund.

```blocks

let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    TILFELDIG_LED = randint(0, 767)
    strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(1000)
   
})
```
## Steg 7: Hvor lenge skal lysdidoen lyse
Trykk på ``||Neopixel:Neopixel||`` fra blokkmenyen og klikk deretter ``||Neopixel:mer||``.
Klikk og dra inn blokken ``||Neopixel:strip set_Pixel_Color at 0 to Red||`` plasser den nederst i ``||basic: gjenta for alltid||``. 
Trykk på ``||Variabler:Variabler||`` deretter klikk og dra inn blokken ``||Variabler:TILFELDIG LED||`` inn i  blokken ``||Neopixel:strip set_Pixel_Color at 0 to Red||``.
Sett fargen til Black. Det er viktig å ha samme LED nummer på begge for å kunne slå av og på LED eller å skifte farge.

```blocks

let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    TILFELDIG_LED = randint(0, 767)
    strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(1000)
    strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Black))
    
})
```
## Steg 8: Send informasjon til Neopixlene
Trykk på ``||Neopixel:Neopixel||`` fra blokkmenyen.Klikk og dra inn blokken ``||Neopixel:strip.show||`` plasser den under forrige blokk.
Denne blokken sender hvilken LED nummer og farge til LEDène som skal skiftes.

```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    TILFELDIG_LED = randint(0, 767)
    strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(1000)
    strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Black))
    strip.show()
})
```
## Steg 9: Send informasjon til Neopixlene
Trykk på ``||basic:Basis||`` fra blokkmenyen.
Velg ``||basic.pause||`` og plaser denne under forrige blokk i ``||basic: gjenta for alltid||``.
Sett pausen verdien til 1000 millisekunder som er 1 sekund.


```blocks
let strip = neopixel.create(DigitalPin.P0, 768, NeoPixelMode.RGB)
strip.clear()
basic.forever(function () {
    TILFELDIG_LED = randint(0, 767)
    strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Red))
    strip.show()
    basic.pause(1000)
    strip.setPixelColor(TILFELDIG_LED, neopixel.colors(NeoPixelColors.Black))
    strip.show()
    basic.pause(1000)
})
```

## Steg 10: Leste ned på microbiten

hvis du har en @boardname@ tilkoblet, trykk ``|last ned|``!   Prøv å endre ``||basic:pause(1000)||`` for å endre hastighet på blinkingen og ``|last ned|`` igjen.
Husk at LED nummer må være lik for å blinke av eller på. 
For hver endring vi gjør i koden må det lastes ned på nytt til @boardname@.
