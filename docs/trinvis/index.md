---
title: "Trin | samlet"
layout: default
nav_order: 2
---

Nu til den egentlige vejledning, som er en skalerbar skabelon, der er sat op til at hjælpe OS2 projekter og produkter med at bygge gode overskuelige dokumentationssider.
Skabelonen hjælper med en hurtig opstart og understøtter en stabil struktur.

<br><br><br><br>

### Trin for trin

<br>
<details>
  <summary><strong>Trin 1: OS2 hovedorganisation på GitHub</strong></summary>
  <p>Her finder du flere repository:</p>
  <ol>
    <li>OS2 Handbook</li>
    <li>Governance Report</li>
    <li>Documentation template</li>
  </ol>
  <br>
  <p>Den sidste er den, vi bruger i denne vejledning.</p>
 <a href="https://github.com/OS2offdig">Gå til OS2s hovedorganisation</a>
</details><br>

<details>
  <summary><strong>Trin 2: Vælg den rigtige skabelon</strong></summary>
  <p>Scroll ned (helt ned på siden) og vælg/tryk OS2-docs-template repository’et.</p>
  <br>
  <img src="../images/01_Vaelg_repo.png" alt="Vælg repository"><br><br>
  
</details><br>

<details>
  <summary><strong>Trin 3: Opret repository</strong></summary>
  <p>Når du er kommet ind på repository’et:</p>
  <p>Tryk på [Use this template] i øverste højre hjørne og vælg: Create a new repository</p>
  <br>
  <img src="../images/02_Use_this_template.png" alt="Vælg skabelon"><br><br>
  
</details><br>

<details>
  <summary><strong>Trin 4: Vælg ejer til repository'et</strong></summary>

  <p>Der skal vælges en owner til det nye repository – det kan være din produktorganisation. I nedenstående eksempel er det OS2valghalla.</p>
  <p>Giv et navn – det kan være produktnavnet efterfulgt af navnet. Navnet skal være uden mellemrum, brug i stedet ’–’</p>
  <p>Der kan også tilføjes en beskrivelse, men det er ikke obligatorisk, og kan gøres senere.</p>
  <p>Vælg ’Public under Configuration, det kan også gøres senere, men er nemmest at gøre med det samme.</p>
  <p>Sitet skal være konfigureret som ’Public’ for at kunne udgives og være synligt.</p>
  <br>
  <img src="../images/03-01_owner_navn_public.png" alt="Vælg ejer til repository'et"><br><br>
  
</details><br>

<details>
  <summary><strong>Trin 5: Byg repository'et</strong></summary>

  <p>Klik på: Create Repository – efter et lille stykke tid er der oprettet et repository under den valgte ’owner’ (i dette eksem OS2valghalla).</p>
  <br>
  <img src="../images/04_navn_beskrivelse.png" alt="Vælg ejer til repository'et"><br><br>
  <p>Der kommer muligvis en fejlbesked på mail:</p>
  <p>’[OS2Valghalla/OS2valghalla-3-pixi] Run failed: Deploy Jekyll site to Pages’</p>
  <p><strong>Se bort fra den for nu.</strong></p>
  
</details><br>

<details>
  <summary><strong>Trin 6: Open Source licens</strong></summary>

  <p>Nedenfor ses det ’rå’ repository, tryk på LICENSE filen, for at tjekke, at det er den rigtige.</p>
  <p>Det skal være: <strong>Creative Commons Attribution Share Alike 4.0 International</strong></p>
  <br>
  <img src="../images/05_tjek_licens.png" alt="Tjek licencen"><br><br>
  <img src="../images/05_01_tjek_licens.png" alt="Tjek licencen"><br><br>

</details><br>

<details>
  <summary><strong>Trin 7: Klargør Pages</strong></summary>

  <p>Klik på Settings og vælg Pages i sidemenuen.</p><br>

  <img src="../images/06_settings.png" alt="Vælg Settings og efterfølgende Pages"><br><br>
  <p>Under ’Build and deploy’ vælges GitHub Actions:</p><br>
  <img src="../images/07_build_deploy.png" alt="Byg siderne"><br><br>
  <p>Nu er opsætningen blevet klargjort til at bygge siderne gennem GitHub Actions. Siderne bliver ikke bygget endnu - der skal laves en tilføjelse til _config.yml filen, se trin 8.</p>

</details><br>

<details>
  <summary><strong>Trin 8: Færdiggør bygning af siden</strong></summary>

  <p>Tryk på <> Code i topmenuen:</p><br>

  <img src="../images/08-01_config.png" alt="Vælg Code i topmenuen"><br><br>
  <p>Vælg herefter _config.yml filen i repository'ets rod/root directory:</p><br>
  <img src="../images/08-02_config.png" alt="Vælg config-filen"><br><br>
  <p>Der skal laves en tilføjelse til standard filen, så siderne bygges. Her kan titel og beskrivelse også ændres.</p>
  <img src="../images/08-03_config.png" alt="Sådan ser filen ud. Der skal laves en tilføjelse"><br><br>

  <p>Tilføjelse (tryk på blyanten i fil-headeren for at redigere):    
  <img src="../images/08-06_config-edit.png" alt="Tryk på blyant for at redigere">
  </p>
  <p>Indsæt følgende kode nederst i filen:</p>

  <pre><code class="language-yaml">
  defaults:
  - scope:
      path: ""         # alle filer i hele repoet
      type: "pages"    # markdown-sider
    values:
      layout: "default"
      has_toc: false # fjerner overordnet 'Table of contents'. has_toc kan sættes til true her eller i headeren på de individuelle sider
  </code></pre><br>
  <p>Det er nødvendigt at være omhyggelig med indrykningerne i .yml-filen, da disse har betydning. Det vil give fejl, hvis de ikke er korrekte.</p>
  <p>Klik på [Commit changes], når filen er ændret.</p><br>

  <img src="../images/08-04_config.png" alt="Commit changes"><br><br>
  <p>Skriv gode commit-beskrivelser, så det er muligt senere let at se hvilke ændringer, der er foretaget og evt. hvorfor.</p><br>
  <img src="../images/08-05_config.png" alt="Commit besked, fx: Tilføjelse til config-filen. Første opdatering for at kunne bygge sider "><br><br>
  <p>Vælg: Commit changes.</p>

</details><br>

<details>
  <summary><strong>Trin 9: Følg med i dit commit</strong></summary>

  <p>Du kan klikke på [Actions] for at følge med i, hvor lang commit’et er kommet. Den brune prik indikerer at commit’et stadigt er i gang, grøn prik at det er gået igennem og rød prik, at der er opstået en fejl.</p><br>

  <img src="../images/09_actions_for_at_se_bygget.png" alt="Følg med i bygget/build"><br><br>
  <img src="../images/09-01_actions_for_at_se_bygget.png" alt="Status på bygget/build"><br><br>
  <p>Det tager et lille stykke tid. Hvis der opstår en fejl, er der en uddybende beskrivelse af denne, hvis man tilgår bygget (tryk på det).</p>
  <p>Nedenfor har _config-filen bygget med succes:</p><br>

  <img src="../images/09-02_actions_for_at_se_bygget.png" alt="Byg/build succes"><br><br> 

</details><br>

<details>
  <summary><strong>Trin 10: Adresselink (URL)</strong></summary>

  <p>Gå nu tilbage til: Settings og vælg Pages</p>
  <p>Siden er nu bygget og har fået en <strong>url</strong>:</p><br>

  <img src="../images/10_url_live.png" alt="URL til siden"><br><br>

  <p>Tryk på url’en og se siden.</p><br>

  <img src="../images/10-01_url_live.png" alt="Selve siden"><br><br> 

</details><br>

<details>
  <summary><strong>Trin 11: Ret indexfilen til og angiv titel</strong></summary>

  <p>En index-fil er systemets startpunkt. Den åbnes først og sørger for at vise den rigtige side eller starte den relevante funktionalitet ved at samle forbindelsen til de øvrige filer og komponenter.</p>
  <p>Tryk på <> Code i topmenuen og vælg index.md i sidemenuen.</p><br>

  <img src="../images/11_index_filen.png" alt="Index-filen"><br><br>

  <p>Vælg blyanten for at redigere filen. Egenskaber, titel og tekst mv. kan ændres her.</p><br>

  <img src="../images/11-01_index_filen_titel_tekst.png" alt="Rediger index-filen"><br><br>
  <img src="../images/11-02_index_filen_titel_tekst.png" alt="Ny titel på index-filen"><br><br> 
  <p>Tryk <strong>’Commit changes’</strong> og tilføj en beskrivende tekst.</p>
  <p>Igen kan ’bygget’ ses under Actions.</p><br>
  <img src="../images/11-03_index_filen_titel_tekst.png" alt="Tjek titel på siden"><br><br>

  <p>Udkommentering gøres med: &lt;!-- teksten der skal udkommenteres --&gt;</p>

  <p>På ’logo-pladsen’ står der stadig: Just the Docs Template. Dette ændres i _config.yml-filen.</p>
  <p>Vælg <> Code i topmenuen og åbn _config.yml</p>
  <p>Vælg blyanten for at redigere og ændr titel og beskrivelse.</p>
  <p>Det er også muligt at lægge et logo her.</p><br>

  <img src="../images/12_titel_logo.png" alt="Titel og logo på siden"><br><br>
  <p>Commit changes…</p><br>
  <img src="../images/12-01_titel_logo.png" alt="Titel og logo på siden"><br><br>

</details><br>

<details>
  <summary><strong>Trin 12: Opret filer og mapper</strong></summary>

  <p>Vælg: <> Code og tryk på mappen: docs</p>
  <p>Herfra kan der oprettes filer og mapper. En mappe kan ikke være tom på GitHub, så man opretter den første fil samtidig med mappen (se markeret tekst længere nede på siden.</p><br>

  <img src="../images/13_filer_mapper.png" alt="Opret filer og mapper"><br><br>

  <p>Tryk på: Create new file for at oprette filer.</p><br>

  <img src="../images/13-01_filer_mapper.png" alt="Opret fil"><br><br>
  <p>Skriv navnet på filen og husk .md som filtype. Består navnet af flere ord, deles de med  underscore, fx: <mark>my_first_page.md</mark></p>
  <p>Tryk ’Commit changes’ og lav en god beskrivelse.</p><br>
  <img src="../images/13-02_filer_mapper.png" alt="Opret fil"><br><br>
  <p><strong>For at lave en mappe:</strong></p>
  <p>Tryk på: Create new file for at oprette mapper.</p>
  <p>I feltet angives mappe navn, lav slash og skriv filnavnet på filen, fx: <mark>ny_mappe/fil.md</mark></p>
  <p><strong>OBS</strong>: Der skal oprettes en fil i mappen, før den kan oprettes.</p>
  <img src="../images/13-04_filer_mapper.png" alt="Opret mappe"><br><br>

</details><br>