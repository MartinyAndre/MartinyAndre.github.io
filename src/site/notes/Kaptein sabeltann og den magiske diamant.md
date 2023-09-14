---
Date: 2023.08.29
Status: "#draft"
Links:
  - "[[../Litteratur/BTC/Høyt engasjerende oppgaver - MOC|Høyt engasjerende oppgaver - MOC]]"
  - "[[../Litteratur/BTC/BTC - MOC|BTC - MOC]]"
tags:
  - "#highlyengaging"
alder: alle
dg-publish: true
---
# Aktivitet: «Kaptein Sabeltanns store diamant»

Kongen på havet, selveste kaptein Sabeltann, og hans åtte pirater har tenkt å splitte seg og bli landkrabber alle mann. De har fordelt alt gullet likt mellom seg, men de sitter igjen med en gigantisk diamant som ikke kan deles. For å avgjøre hvem som skal få den, plassere Kaptein sabeltann alle piratene (inkludert ham selv) i en sirkel. Deretter peker han på en person som skal begynne. Denne personen trer ut av sirkelen, tar alt gullet sitt og drar. Person på hans venstre side blir værende, men den neste person til venstre må gå ut. Dette fortsetter, med at hver andre pirat forlater med sitt gull, helt til det kun er én person igjen. Hvem burde kapteinen peke på hvis han skal være den som får diamanten for seg selv?

Hva hvis kaptein Sabeltann hadde 9 menn? Hva med 10 menn? N menn?

![Piratproblem](https://raw.githubusercontent.com/Andremartiny/MA-173/main/img/Piratproblem.svg)

## Løsninger

### Se etter mønster i tabell

La oss først tenke at vi sier at kaptein Sabeltann alltid står på posisjon 1, så teller vi med klokken. Vi kan nå se at hvis det var kaptein Sabeltann og én pirat til, så ville Sabeltann stå igjen med diamanten hvis vi startet på nummer 2. Hvis vi var tre personer, måtte vi startet på posisjon 3 for at sabeltann skulle vinne. Fortsetter vi det slik får vi følgende tabell.

| Personer | Startposisjon |
| -------- | ------------- |
| 2        | 2             |
| 3        | 3             |
| 4        | 2             |
| 5        | 5             |
| 6        | 4             |
| 7        | 3             |
| 8        | 2             |
| 9        | 9             |
| 10       | 8             |
| 11       | 7             |
| 12       | 6             |
| 13       | 5             |
| 14       | 4             |
| 15       | 3             |
| 16       | 2             |
| $\vdots$ | $\vdots$      | 

Mønsteret er nå tydelig. Men hvordan kan vi enkelt finne ut hvor vi bør starte? Et triks kan være å legge merke til toer-potensene og at det er alltid rett etter de at vi begynner tellingen på nytt. Legger vi sammen antall personer og gunstig startposisjon for Sabeltann, ser vi at følgen blir slik; $4, 6, 6, 10, 10, 10, 10, 18, 18, 18, 18, 18, 18, 18, 18, 34, \ldots$ 

Vi kan altså se at hvis vi skriver antall personer som $n = 2^k+m$, der $m < 2^k$, så trenger vi å starte på posisjon $P$ slik at $n+P = 2\cdot 2^k +2$. En _bør_ gjerne lese dette som. Finn høyeste toerpotens mindre enn $n$. Startposisjonen er nå det tallet du må legge til $n$ slik at du kommer 2 forbi neste toerpotens.

La oss bryte dette ned i noen eksempler: 
- Hvis antall personer er $15$, så er $8$ høyeste toerpotens mindre enn $15$. Jeg må legge til $3$ for å komme til $8\cdot 2 + 2 = 18$. Dermed er startposisjonen $3$. 
- Hvis antall personer er $24$, er høyeste toerpotens  mindre enn $24$ nemlig 16. For å komme til $16\cdot 2 +2 = 34$ må vi legge til 10. Dermed er startposisjonen 10. 
- Hvis vi er 55 pirater, vil 32 være toerpotensen vi tar utgangspunkt i. Vi må altså opp til $66$ og ser at vi mangler 11. Dermed er startposisjonen 11.

**Merk:** Det er også mulig å bare tenke rett til neste toerpotens og se hva som mangler for å komme to over. Da ser vi i eksemplene over at vi må fra 15 til 18 og mangler 3, vi må fra 24 til 34 og mangler 10, vi må fra 55 til 66 og mangler 11. Denne metoden er kanskje enda raskere.
# References

