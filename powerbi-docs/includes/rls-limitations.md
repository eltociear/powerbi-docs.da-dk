## <a name="limitations"></a>Begrænsninger

Her følger en liste over de aktuelle begrænsninger for sikkerhed på rækkeniveau i cloudmodeller.

* Hvis du tidligere har defineret roller og regler i Power BI-tjenesten, skal du genoprette dem i Power BI Desktop.

* Du kan kun definere RLS for de datasæt, der er oprettet ved hjælp af Power BI Desktop. Hvis du vil aktivere RLS for de datasæt, der er oprettet i Excel, skal du først konvertere dine filer til PBIX-filer (Power BI Desktop). [Få mere at vide](../desktop-import-excel-workbooks.md)

* Det er kun ETL- og DirectQuery-forbindelser, der understøttes. Dynamiske forbindelser til Analysis Services skal håndteres i modellen i det lokale miljø.

* Spørgsmål og svar samt Cortana understøttes ikke med RLS på nuværende tidspunkt. Du kan ikke se inputfeltet til spørgsmål og svar i dashboards, hvis RLS er konfigureret for alle modeller. Dette problem er sat på vores roadmap, men vi har endnu ikke udarbejdet en tidsplan for det.

## <a name="known-issues"></a>Kendte problemer

Der er et kendt problem, hvor der vises en fejlmeddelelse, når du forsøger at publicere en Power BI Desktop-rapport, som allerede er publiceret. Scenariet er som følger.

1. Anna har et datasæt, der er publiceret i Power BI-tjenesten, og hvor RLS er konfigureret.

1. Anna opdaterer rapporten i Power BI Desktop og publicerer den igen.

1. Anna modtager en fejl.

**Midlertidig løsning:** Publicer Power BI Desktop-filen igen vha. Power BI-tjenesten, indtil problemet er løst. Det kan du gøre ved at vælge **Hent data** > **Filer**.
