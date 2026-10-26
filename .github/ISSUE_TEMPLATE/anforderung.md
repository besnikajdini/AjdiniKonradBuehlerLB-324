---
name: Anforderung
about: Neue Funktionalität als Anforderung erfassen
title: "[Zielsystem] muss/soll/wird [Systemaktivität] [Funktionalität]"
labels: ''
assignees: ''
---

## Anforderung
[Zielsystem] [muss | soll | wird] [selbständig | dem Benutzer die Möglichkeit bieten | fähig sein] [allf. Ergänzungen] [Funktionalität] [wenn … / falls …].

| Baustein | Inhalt |
| --- | --- |
| Zielsystem | betroffenes (Teil-)System, z.B. Tagebbbuch-Applikation |
| Priorität | **muss** = hoch, **soll** = mittel, **wird** = niedrig |
| Systemaktivität | selbständig (System handelt allein) / dem Benutzer die Möglichkeit bieten (Benutzerfunktion) / fähig sein (Schnittstelle) |
| Ergänzungen | (optional) |
| Funktionalität | was genau gemacht wird |
| Bedingungen | **wenn** = zeitlich, **falls** = logisch |

**Beispiel:** Die Tagebbbuch-Applikation muss dem Benutzer die Möglichkeit bieten, einem Tagebucheintrag eine Stimmung als Emoji zuzuordnen, falls der Benutzer eingeloggt ist.

## Akzeptanzkriterien
| Given | When | Then |
| :---: | :---: | :---: |
| Ausgangslage | Aktion | erwartetes Resultat |

## Typ
Bitte manuell ein Label setzen: `type: funktionale Anforderung`, `type: Qualitätsanforderung` oder `type: Randanforderung`.
