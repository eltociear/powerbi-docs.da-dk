## <a name="limitations"></a>Begrænsninger
Her følger en liste over de aktuelle begrænsninger for sikkerhed på rækkeniveau i cloudmodeller.

* Hvis du tidligere har haft roller og regler, der er defineret i Power BI-tjenesten, skal du gendanne dem i Power BI Desktop.
* Du kan kun angive RLS for de datasæt, der er oprettet ved hjælp af Power BI Desktop-klienten. Hvis du vil aktivere RLS for de datasæt, der er oprettet i Excel, skal du først konvertere dine filer til PBIX-filer. [Få mere at vide](../desktop-import-excel-workbooks.md)
* Det er kun ETL- og DirectQuery-forbindelser, der understøttes. Dynamiske forbindelser til Analysis Services skal håndteres i modellen i det lokale miljø.
* Spørgsmål og svar og Cortana understøttes ikke med RLS på nuværende tidspunkt. Du kan ikke se inputfeltet til spørgsmål og svar i dashboards, hvis RLS er konfigureret for alle modeller. Dette problem er sat på vores roadmap, men vi har endnu ikke udarbejdet en tidsplan for det.
* Ekstern deling understøttes ikke i øjeblikket med de datasæt, der bruger RLS.
* For en given model kan der maksimalt tildeles 1.000 Azure AD-sikkerhedskonti (dvs. individuelle brugere eller sikkerhedsgrupper) til sikkerhedsroller. Hvis du vil tildele et stort antal brugere til roller, skal du tildele sikkerhedsgrupper i stedet for individuelle brugere.

## <a name="known-issues"></a>Kendte problemer
Der er et kendt problem, hvor der vises en fejlmeddelelse, når du forsøger at udgive noget fra Power BI Desktop, som allerede er udgivet. Scenariet er som følger.

1. Anna har et datasæt, der er udgivet til Power BI-tjenesten, og hvor RLS er konfigureret.
2. Anna opdaterer rapporten i Power BI Desktop og udgiver den igen.
3. Anna modtager en fejl.

**Løsning:** Udgiv Power BI Desktop-filen igen fra Power BI-tjenesten, indtil problemet er løst. Det kan du gøre ved at vælge **Hent data** > **Filer**. 

