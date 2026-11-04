# Piano nuovi servizi Italfuni (novembre 2026)

Cartella `docs/` esclusa da Jekyll (non viene pubblicata). Generatore: `C:\Users\mirco\Desktop\claudetemp\gen_servizi.py`.

## Perche' questi servizi (analisi competitor)
- EdiliziAcrobatica vende manutenzione programmata (trimestrale/semestrale/annuale), pulizia e sanificazione, restauro monumenti, fotovoltaico. Le piccole ditte su edilizia.com elencano lattoneria, trattamento ferri, ringhiere.
- Ispezioni con drone/fune di tetti e facciate: servizio a pagamento a basso costo che porta lavori di riparazione.
- Punto forte: ricorrenza (contratti annuali, verifiche periodiche) e B2B (condomini, capannoni, parrocchie).
- Concorrente grande in difficolta' finanziaria nel 2026: non scriverci contro, puntare su "preventivo chiaro, risponde chi lavora".

## I 9 servizi (pagina base + 5 province: Roma, Viterbo, Rieti, Latina, Frosinone = 54 pagine)
1. manutenzione-programmata-condomini (tema foto: manutenzione)
2. ispezione-tetti-facciate-report-fotografico (ispezione)
3. verifica-periodica-linee-vita (lineevita)
4. pulizia-guano-nidi-piccioni (guano)
5. manutenzione-coperture-capannoni (capannoni)
6. pulizia-tetti-trattamento-antimuschio (antimuschio)
7. ricerca-riparazione-infiltrazioni-tetto (infiltrazioni)
8. manutenzione-tetti-campanili-chiese (chiese)
9. lattoneria-ringhiere-trattamento-ferri (lattoneria)

## Regole (da Mirco)
- Title = nome articolo + " - Italfuni" (trattino, mai "|"); niente seo_title nei servizi.
- Description sempre con "su fune"; testi naturali, non ambigui.
- Pagine citta': permalink in root `/<slug>-a-<citta>/`, redirect_from `/servizi/...`, campo `citta`, in_home false.
- Foto a tema: tag nuovi in `_data/foto.yml`, tema per slug in `_data/foto_temi.yml`, `foto:` esplicito in ogni pagina (varia per citta').
- Nessun bordo laterale colorato. Dopo il push non aspettare la build.

## Da decidere / verificare
- Prezzi indicativi ("da X euro"): li decide Mirco, poi si aggiunge una sezione per servizio.
- Detrazioni/sconto in fattura: verificare le regole 2026 prima di scrivere una pagina.
- Amianto: non trattato (servono autorizzazioni).
- Foto mancanti: nessuna foto vera di ringhiere/ferri, guano/nidi, linee vita installate, capannoni. Usate le piu' pertinenti; vanno sostituite appena ci sono scatti reali.
- Voce di menu e in_home dei nuovi servizi: per ora non aggiunti (in_home false).
