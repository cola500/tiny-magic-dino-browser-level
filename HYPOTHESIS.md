---
title: Tiny Magic Dino — Browser Level
description: Validera om vi kan bygga en charmig, spelbar mini-bana i webbläsaren utan build-verktyg, på under 20 minuter
category: ux-validation
status: confirmed
last_updated: 2026-05-21
sections: [Hypothesis, Test, Success Criteria, Time Budget, What is Intentionally Fake, Manual Verification, Result, Next Iteration]
---

# Tiny Magic Dino — Browser Level (LINDENGARD)

## Hypothesis
Vi kan använda AI-assisterad rapid prototyping för att skapa en liten, känslomässigt engagerande mini-bana i webbläsaren — på under 20 minuter, utan Unity, utan build-steg, utan dependencies — som duger som demo-snutt för en LinkedIn-video.

## Test
En enda HTML-fil (`index.html`) som innehåller:
- En side-scrolling dinosaurie-spelloop på Canvas
- Spelare som hoppar med `Space`/`↑` och rör sig med `←`/`→`
- Tio bokstäver `L I N D E N G A R D` utplacerade i banan
- Två chasms att hoppa över
- Plattformar för att nå bokstäver i luften
- En mål-flagga
- Win-state som visar **"Du klarade banan!"** + ordet `LINDENGARD` + konfetti

Visuellt enkelt men varmt: solgul HUD, glada färger, runda former, mjuk gradient.

## Success Criteria
- [ ] Spelet startar direkt när man öppnar `index.html` (ingen server, ingen build)
- [ ] Kärnmekaniken funkar (hopp, gravity, kollision med mark/plattform)
- [ ] Det går att samla alla 10 bokstäver
- [ ] Det går att nå flaggan
- [ ] Win-state visas korrekt med rätt ord + en celebration-effekt
- [ ] Helhetsintrycket är charmigt nog att visa i en kort demo-video (subjektiv bedömning)

## Time Budget
20 minuter total bygg-tid. Om vi närmar oss 20 min, stoppa och utvärdera vad vi har — visuell polish är OK att kapa först.

## What is Intentionally Fake / Simple
- **Grafik**: Enkla geometriska former i Canvas (inga sprites, inga bilder)
- **Fysik**: Konstant gravity, en jump-impuls. Ingen variable jump height.
- **Kollision**: Axis-aligned bounding boxes, top-only landing detection
- **Ljud**: Inget alls
- **Liv/score/timer**: Inget. Om man trillar i en chasm spawnar man bara om i början
- **Mobile/touch**: Inget. Endast tangentbord
- **Responsiv design**: Fix canvas 800x400
- **Bana 1**: Existerar inte. Vi bygger bara "Bana 2".
- **Persistens**: Ingen save/state mellan reloads

## Manual Verification
1. Öppna `experiments/tiny-magic-dino-browser-level/index.html` direkt i webbläsare (dubbelklick, eller `open index.html`)
2. Kontrollera att HUD visar 10 tomma bokstavs-platser längst upp
3. Tryck `→` för att springa höger
4. Tryck `Space` för att hoppa — verifiera att dino landar igen
5. Samla bokstaven `L`, kontrollera att HUD fylls i
6. Hoppa över första chasmet — verifiera att man kan dö och spawna om vid kant-fall
7. Hoppa upp på första plattformen och plocka bokstaven där
8. Fortsätt genom hela banan, samla alla 10 bokstäver
9. Hoppa över andra chasmet
10. Nå flaggan
11. Verifiera att overlay visar **"Du klarade banan!"** + ordet `LINDENGARD` + konfetti

## Success / Failure
- **Confirmed** om alla success criteria är ✅ och helheten känns charmig
- **Denied** om vi inte hinner inom 20 min ELLER om resultatet känns för platt för demo-video
- **Needs iteration** om mekaniken funkar men charm/polish-nivån är otillräcklig

## Result
- **Status**: Confirmed
- **Build-tid**: ~10 minuter (väl under 20-min-budgeten)
- **What we learned**:
  - En enda HTML-fil med Canvas + lite CSS räcker långt för att bygga en spelbar, charmig demo
  - "Tillräckligt bra" visuellt nås snabbt med geometriska former + parallax + en glad färgpalett — inga sprites behövs
  - Snäll respawn (behåll samlade bokstäver) tar bort frustration utan att förstöra utmaningen
  - För syftet *visa processen i en LinkedIn-demo* behövdes ingen ljud/animation/polish — själva hastigheten ÄR poängen
- **Decision**: Keep — som demo-artefakt och som proof-point för AI-assisterad rapid prototyping

## Next Iteration
Möjliga uppföljnings-experiment (varsin ny HYPOTHESIS):
- Lägga till ljudeffekter (jump-blip, letter-pickup-chime, win-fanfare) → testa om ljud lyfter "charm-faktor" markant
- Lägga till en fiende eller hazard → testa om det blir mer spännande utan att tappa barn-vänligheten
- Bygga "Bana 1" som intro, eller en level-select-skärm
- Spelar in faktisk LinkedIn-demo-snutt och utvärdera mottagandet
