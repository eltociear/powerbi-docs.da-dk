## <a name="validating-the-role-within-power-bi-desktop"></a>Valider rolle i Power BI Desktop
Når du har oprettet din rolle, kan du teste resultaterne for rollen i Power BI Desktop. Det gør du ved at vælge **Vis som roller**.

![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)

I dialogboksen **Vis som roller** kan du ændre visningen for det, der vises for den bestemte bruger eller rolle. Du kan se de roller, du har oprettet.

![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)

Vælg den rolle, du har oprettet, og vælg derefter **OK** for at anvende rollen på det, du får vist. Rapporterne gengiver kun de data, der er relevante for rollen.

Du kan også vælge **Anden bruger** og angive en specifik bruger. Det er bedst at angive UPN (User Principal Name), da det er det navn, som Power BI-tjenesten bruger. Vælg **OK** for at få gengivet rapporterne baseret på det, som brugeren kan se. 

![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)

> [!NOTE]
> I Power BI Desktop vil dette kun vise forskellige resultater, hvis du bruger dynamisk sikkerhed baseret på dine DAX-udtryk.
> 
> 

