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
For hver endring vi gjør i koden må det lastes ned på nytt til @boardname@. Dersom du ikke har en @boardname@ tilkoblet, må du gjøre de neste stegene også.

## Steg 11: Koble til micro:biten
For å kunne laste ned koden din til micro:biten med et klikk må du først få MakeCode til å skjønne at alle filer skal lastes ned direkte til den.
Det krever bare noen få, enkle steg.

## Steg 12: Prikkene ved siden av Last Ned-knappen

Start med å sjekke at micro:biten du skal bruke er koblet til PCen. Når den er koblet til, klikker du på de tre prikkene ved siden av ``|last ned|``-knappen

![Connect](https://raw.githubusercontent.com/InspiriaSCC/Superbit/master/static/Connect1.jpg)

## Steg 13: Connect-menyen @unplugged
Når du klikker på de tre prikkene dukker det oppe en liten meny. Dersom det står "Koble Fra" eller "Disconnect" på den øverste linjen, trenger du ikke å gjøre mer.
Da kjenner PCen og MakeCode igjen micro:biten fra tidligere, og du kan klikke ved siden av menyen og laste ned koden din ved å klikke på den store ``|last ned|``-knappen.

![Connect](https://raw.githubusercontent.com/InspiriaSCC/Superbit/master/static/Connect2b.jpg)


## Steg 14: Dersom MakeCode ikke kjenner micro:biten fra før
Dersom MakeCode ikke kjenner micro:biten fra før vil det stå "Connect device" eller "Koble til" på den øverste linjen.
Klikk i så fall på den øverste linjen i menyen.

![Connect](https://raw.githubusercontent.com/InspiriaSCC/Superbit/master/static/Connect2.jpg)


## Steg 15: Veiledningsvindu

Når du klikker på den øverste linjen dukker det opp et par veiledningsvinduer som tar deg gjennom tilkoblingsprosessen. De to første kan du bare trykke "Next" eller "Fortsett" på:

![Connect](https://raw.githubusercontent.com/InspiriaSCC/Superbit/master/static/Connect3.jpg)

![Connect](https://raw.githubusercontent.com/InspiriaSCC/Superbit/master/static/Connect4.jpg)


## Steg 16: Velg micro:biten

Etter at du har klikket "Next" to ganger dukker det opp en liste over tilgjengelige micro:biter. Det skal bare være én micro:bit på lista.
Klikk først på navnet til micro:biten så det blir merket med blått, og så på "Koble til".

![Connect](https://raw.githubusercontent.com/InspiriaSCC/Superbit/master/static/Connect5.jpg)

## Steg 17: Ferdig!

I det siste veiledningsvinduet klikker du på "Done" eller "Ferdig" om det står på norsk.
Etter det kan du laste ned kode direkte til micro:biten ved å klikke på den store, lilla ``|last ned|``-knappen nederst til venstre på skjermen i MakeCode:

![Connect](https://raw.githubusercontent.com/InspiriaSCC/Superbit/master/static/Connect6.jpg)

* for PXT/microbit
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
