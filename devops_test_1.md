# DevOps – Ispitna pitanja i odgovori

Ova skripta sadrži pitanja i odgovore za predmet **DevOps**, sa kratkim objašnjenjima i primerima iz stvarnog sveta.  
Pitanja su grupisana po sekcijama koje prate glavne principe i prakse DevOps-a.  

<br></br>

# Uvod u DevOps

**1. Koje tri komponente se smatraju ključnim za uspeh DevOps koncepta?**  
Ljudi, procesi i tehnologije  
- **Obrazloženje:** DevOps nije samo alat ili tehnologija – radi se o kulturi saradnje (ljudi), jasnim procesima (CI/CD, monitoring, incident management) i tehnologijama koje omogućavaju brzinu i stabilnost (cloud, kontejneri, orkestracija).  
- **Primer:** Netflix ne bi mogao da isporučuje stotine deploy-a dnevno da nije uklonio barijere između timova (ljudi), definisao jasan pipeline (procesi) i uveo mikroservise i cloud (tehnologije).  

**2. Da li se u DevOps pristupu potencira distinkcija između timova koji rade razvoj i timova koji operativno upravljaju softverom, ili se teži da barijera između ovih timova iščezne?**  
Teži se da barijera iščezne  
- **Obrazloženje:** DevOps je nastao upravo zbog problema „baca se kod preko zida“ (dev → ops). Cilj je da oba tima rade kao jedan, dele odgovornost i imaju zajedničke ciljeve.  
- **Primer:** U praksi, to znači da isti tim koji razvija aplikaciju piše i deployment skripte (npr. Helm chart za Kubernetes), a takođe je odgovoran za monitoring i reagovanje na incidente.  

**3. DevOps procesi teže da maksimalno koriste koji princip?**  
Princip automatizacije i princip toka (flow)  
- **Obrazloženje:** Automatizacija eliminiše ručne korake i ubrzava tok vrednosti od koda do produkcije. Princip toka znači da promena brzo prolazi kroz pipeline, uz ranu validaciju i povratne informacije.  
- **Primer:** Kada developer gurne commit na GitHub, GitHub Actions automatski pokreće build, testove i deployment – sve bez ručnog rada.  

**4. Koje tehnologije obezbeđuju dovoljno brzu i fleksibilnu platformu za DevOps?**  
Cloud, kontejneri (Docker), orkestratori (Kubernetes), sistemi za verzionisanje (Git), CI/CD alati (Jenkins, GitLab CI, GitHub Actions)  
- **Obrazloženje:** DevOps zahteva brzinu i ponovljivost – kontejneri omogućavaju isto okruženje svuda, cloud daje skalabilnost, a CI/CD alati obezbeđuju automatizovan put do produkcije.  
- **Primer:** Startapi često koriste AWS + Docker + GitHub Actions da bi za par minuta mogli da testiraju i puste novu verziju aplikacije bez skupih servera i manualnog setup-a.  

**5. Koji su problemi često pratili razvoj softvera i doveli do stvaranja koncepta DevOps-a?**  
Spora isporuka, odvojeni timovi (dev vs ops), kasno otkrivanje bugova, „works on my machine“ problem, ručni i nepouzdani deployment-i  
- **Obrazloženje:** Tradicionalni waterfall razvoj značio je da se mesecima radi na kodu, a problemi isplivaju tek na kraju – što je kasno, skupo i rizično.  
- **Primer:** Pre DevOps-a, Microsoft je imao ogromne release cikluse za Windows (godinama), dok je danas moguće da cloud aplikacije imaju i po 50 deploy-a dnevno.  


<br></br>
# Princip toka

**6. Koji ključni koncepti čine suštinu funkcionisanja DevOps-a?**  
Princip toka, princip povratnih informacija, princip konstantnog učenja i eksperimentisanja  
- **Obrazloženje:** Ovo su tri osnovna stuba DevOps filozofije. Tok optimizuje protok rada, povratne informacije omogućavaju rano otkrivanje problema, a učenje stvara kulturu poboljšanja.  
- **Primer:** Toyota je uvela lean principe (tok i učenje), dok su IT kompanije poput Google-a dodale automatizaciju i feedback kroz monitoring.  

**7. Koja su tri osnovna principa DevOps-a?**  
Princip toka, princip povratnih informacija, princip konstantnog učenja i eksperimentisanja  
- **Obrazloženje:** Isti odgovor kao prethodno, ali ovde se naglašava da su ova tri principa temelj DevOps metodologije.  
- **Primer:** Amazon koristi principe toka (brzi deploy), feedback-a (monitoring i alarmi) i eksperimentisanja (A/B testiranje) za stalno unapređenje.  

**8. Šta je value stream / technology value stream?**  
Lanac aktivnosti kroz koji prolazi ideja do isporuke korisniku, sa svim fazama razvoja i operacija  
- **Obrazloženje:** Value stream prikazuje tok vrednosti kroz organizaciju – koliko vremena ide na stvaranje vrednosti, a koliko na otpad.  
- **Primer:** U banci, value stream za mobilnu aplikaciju obuhvata: ideju → razvoj → testiranje → security provere → deployment u produkciju.  

**9. Koje mere pokazuju efikasnost organizacije u izvršavanju poslovnog procesa?**  
Lead time, cycle time, throughput, C/A (completed vs active), kvalitet isporuke  
- **Obrazloženje:** Ove metrike mere koliko brzo i kvalitetno organizacija isporučuje vrednost.  
- **Primer:** Ako firma isporučuje nove verzije aplikacije na svake 2 nedelje umesto svaka 3 meseca, lead time je znatno skraćen.  

**10. Šta je vreme isporuke - Deployment Lead Time?**  
Vreme od trenutka kada se napravi promena do njenog deploymenta u produkciju  
- **Obrazloženje:** Što je kraći lead time, to organizacija brže reaguje na potrebe korisnika.  
- **Primer:** Facebook je smanjio lead time na par sati, dok tradicionalne firme i dalje imaju lead time od više nedelja.  

<br></br>

# Princip povratnih informacija

**11. Šta je procesno vreme?**  
Vreme koje je zaista utrošeno na rad na zadatku, bez čekanja

*   **Obrazloženje:** Procesno vreme pokazuje koliko je posla stvarno urađeno, a ne koliko je zadatak proveo u sistemu.
    
*   **Primer:** Ako feature čeka u backlogu 2 nedelje, a developer ga implementira za 1 dan, procesno vreme je 1 dan.
    

**12. Šta prikazuje mera procentualnog odnosa C/A?**  
Odnos završenih (Completed) i aktivnih (Active) zadataka

*   **Obrazloženje:** Ova metrika meri koliko je rad efikasan u odnosu na započeti rad.
    
*   **Primer:** Ako je 8 zadataka završeno a 2 aktivna, C/A = 80%.
    

**13. Koje prakse omogućavaju čine suštinu uvođenja „principa toka“ i omogućavaju optimizaciju vremena isporuke?**  
Vizualizacija rada, ograničavanje WIP-a, smanjenje veličine zadataka, automatizacija procesa

*   **Obrazloženje:** Princip toka se zasniva na brzom protoku rada bez uskih grla.
    
*   **Primer:** Kanban tabla u Jiri omogućava timu da ograniči broj zadataka u toku i da jasno vidi gde su uska grla.
    

**14. Šta se postiže praksom koja omogućava da je svaki rad vidljiv?**  
Transparentnost i rano otkrivanje problema

*   **Obrazloženje:** Kada je rad vidljiv, lakše se koordinira tim i uočavaju blokade.
    
*   **Primer:** GitHub Pull Request omogućava da svi u timu vide izmene i daju review.
    

**15. Koje tehnike možemo koristiti da učinimo rad vidljivijim?**  
Kanban table, burndown chart-ovi, task board-ovi, code review alati

*   **Obrazloženje:** Vizualni prikaz rada pomaže da tim razume status zadataka.
    
*   **Primer:** Scrum tim koristi burndown chart da prati koliko zadataka ostaje do kraja sprinta.
    

**16. Zašto je bitno ograničiti broj aktivnih zadataka?**  
Da se izbegne multitasking i usporavanje toka

*   **Obrazloženje:** Previše paralelnih zadataka vodi ka kašnjenju i lošem kvalitetu.
    
*   **Primer:** U Kanban sistemu postavlja se WIP limit, npr. max 3 zadatka po osobi.
    

**17. Zašto je pogodno smanjiti veličinu i vreme isporuke pojedinačnih zadataka?**  
Zbog brže isporuke i manjeg rizika od grešaka

*   **Obrazloženje:** Manji zadaci znače manje konflikata i bržu povratnu informaciju.
    
*   **Primer:** Umesto da razvija ceo modul mesec dana, tim razbija posao na male feature-e koji se završavaju za 1–2 dana.
    

**18. Zašto je pogodno smanjiti broj „primopredaja“ jedinica rada u procesu rada?**  
Da bi se smanjile greške i gubici u komunikaciji

*   **Obrazloženje:** Svaka primopredaja dodaje rizik i usporava tok.
    
*   **Primer:** Ako QA tim testira tek na kraju, greške se otkrivaju kasno. Ako testovi idu u pipeline, greške se otkrivaju odmah.
    

**19. Zašto je važno smanjiti količinu „otpada“ koja se uklanja iz procesa rada?**  
Da bi se povećala efikasnost i vrednost za korisnika

*   **Obrazloženje:** Otpad su nepotrebne aktivnosti koje ne dodaju vrednost.
    
*   **Primer:** Pisanje nepotrebne dokumentacije koja se ne koristi.
    

**20. Šta obezbeđuje princip povratnih informacija?**  
Rano otkrivanje i ispravljanje problema

*   **Obrazloženje:** Povratne informacije omogućavaju pravovremene korekcije.
    
*   **Primer:** Automatski testovi vraćaju feedback developeru u roku od par minuta.
    

**21. Problemi u kompleksnim sistemima pre ili kasnije moraju da se dese - šta sigurno radno okruženje predviđa kao prihvatljiv mehanizam rešavanja problema?**  
Otvoreno prijavljivanje problema i zajedničko rešavanje (blameless postmortem)

*   **Obrazloženje:** Fokus je na učenju, a ne na kažnjavanju.
    
*   **Primer:** Google SRE koristi postmortem kulturu bez krivljenja zaposlenih.
    

**22. Povratni tokovi omogućavaju pravovremeno otkrivanje problema, zašto je to bitno?**  
Greške su lakše i jeftinije za ispravku kada se otkriju rano

*   **Obrazloženje:** Što se problem kasnije otkrije, to je skuplji za popravku.
    
*   **Primer:** Bug otkriven na produkciji može koštati hiljade evra, dok isti bug otkriven u testu traje 5 minuta da se ispravi.
    

**23. Šta bi bili pravilni principi koji promovišu kvalitet na samom izvoru?**  
Testiranje i verifikacija što bliže mestu nastanka koda

*   **Obrazloženje:** Kvalitet se gradi u kodu, a ne dodaje na kraju procesa.
    
*   **Primer:** Code review i unit testovi koje developer piše dok razvija funkcionalnost.
    

**24. Koje su osnovne ideje principa konstantnog učenja i eksperimentisanja?**  
Greške su prilika za učenje, eksperimenti vode inovacijama

*   **Obrazloženje:** Organizacija stalno uči iz uspeha i neuspeha.
    
*   **Primer:** Spotify timovi redovno testiraju nove ideje kroz A/B testove.
    

**25. Da li se uči samo iz uspešnih pokušaja ili neuspešni pokušaji implementacije određenih rešenja takođe povećavaju nivo znanja?**  
Uči se i iz neuspeha

*   **Obrazloženje:** Neuspešni pokušaji pokazuju šta ne treba raditi i smanjuju rizik sledećih odluka.
    
*   **Primer:** Amazon Fire Phone je bio neuspeh, ali znanja stečena su iskorišćena u razvoju Alexa uređaja.
    

**26. Jedan od načina reagovanja upravljačkog tima na uočene greške je i “name, blame and shame”. Da li takav pristup trajno podstiče razvoj organizacije?**  
Ne, takav pristup blokira inovacije i otvorenost

*   **Obrazloženje:** Strah od kazne sprečava ljude da eksperimentišu i prijavljuju probleme.
    
*   **Primer:** Organizacije poput Google-a i Netflix-a praktikuju blameless postmortem.
    

**27. Organizacije koje se po načinu funkcionisanja mogu svrstati u “patološke” karakteriše kakvo radno okruženje?**  
Okruženje straha, skrivanja grešaka i krivljenja ljudi

*   **Obrazloženje:** Patološke organizacije sputavaju inovacije i saradnju.
    
*   **Primer:** Kompanije u kojima zaposleni kriju greške da ne bi bili kažnjeni.
    

**28. Šta bi bile “generativne” organizacije?**  
Organizacije koje podstiču saradnju, eksperimentisanje i zajedničko učenje

*   **Obrazloženje:** Fokus je na poboljšanju sistema, a ne na kažnjavanju.
    
*   **Primer:** Etsy je poznat kao primer generativne organizacije u IT svetu.
    

**29. Zašto je bitno sprovesti proces pretvaranja lokalnih saznanja u globalna poboljšanja na nivou organizacije.**  
Da bi cela organizacija imala koristi od naučenih lekcija

*   **Obrazloženje:** Ako znanje ostane lokalno, greške će se ponavljati drugde.
    
*   **Primer:** Incident report iz jednog tima se deli sa celom firmom.
    

**30. Šta omogućava institucionalizacija unapređenja dnevnih aktivnosti?**  
Stalno poboljšanje i učenje kroz kulturu Kaizen-a

*   **Obrazloženje:** Poboljšanja postaju deo svakodnevnog rada, a ne izolovan proces.
    
*   **Primer:** Toyota svakodnevno traži male načine da unapredi proizvodnju.

<br></br>

# Kontinualna integracija i isporuka

**31. Zašto je bitno da deployment pipeline bude tako organizovan da obezbeđuje deployment na okruženje što sličnije krajnjem produkcionom?**  
Da bi testovi i validacija bili realni

-   **Obrazloženje:** Ako se testira u različitom okruženju, mogu promaći kritične greške.
    
-   **Primer:** Bug koji se javlja samo na Linux serverima neće biti otkriven ako se testira na Windowsu.
    

**32. Zašto je bitno da se okruženja kreiraju automatizovano i po mogućnosti “na zahtev”?**  
Zbog brzine i konzistentnosti

-   **Obrazloženje:** Automatizacija smanjuje rizik od ljudskih grešaka.
    
-   **Primer:** Terraform omogućava kreiranje okruženja jednim klikom.
    

**33. Navesti neke od operacija koje je moguće automatizovati, a koje učestvuju u procesu formiranja odgovarajućih okruženja.**  
Provisioning, konfiguracija, build, testiranje, deployment

-   **Obrazloženje:** Automatizacija ubrzava proces i smanjuje greške.
    
-   **Primer:** Ansible playbook postavlja kompletno okruženje za aplikaciju.
    

**34. Zašto je bitno da deployment pipeline počiva na upotrebi repozitorijuma za kontrolu verzija?**  
Da bi sve promene bile praćene i auditovane

-   **Obrazloženje:** Kontrola verzija omogućava vraćanje i pregled istorije.
    
-   **Primer:** Git omogućava rollback na prethodnu verziju aplikacije.
    

**35. Šta bi sve trebalo da se nalazi na sistemu za kontrolu verzija?**  
Izvorni kod, konfiguracije, deployment skripte, dokumentacija

-   **Obrazloženje:** Sve što je potrebno za build i deploy mora biti verzionisano.
    
-   **Primer:** Kubernetes manifesti u Git repozitorijumu (GitOps).
    

**36. Zašto je bitno napraviti okruženje u kome je lakše i jeftinije rebildovati infrastrukturu nego je opravljati?**  
Zbog stabilnosti i brzine oporavka

-   **Obrazloženje:** Immutable infrastruktura eliminiše rizik od “snowflake servera”.
    
-   **Primer:** AWS EC2 instance se brišu i ponovo kreiraju, umesto da se popravljaju.
    

**37. Zašto je pogodno insistirati na kratkim ciklusima razvoja?**  
Zbog bržeg feedback-a i manjeg rizika

-   **Obrazloženje:** Kratki ciklusi znače brže isporuke i lakše uočavanje problema.
    
-   **Primer:** Agile sprint od 2 nedelje umesto release na 6 meseci.
    

**38. Koji problemi nastaju ako se testiranje odlaže i tretira kao poseban deo razvojnog ciklusa koji se sprovodi povremeno?**  
Kasno otkrivanje grešaka, skuplja ispravka, kašnjenje isporuka

-   **Obrazloženje:** Odloženo testiranje povećava troškove i rizik.
    
-   **Primer:** Waterfall projekti gde se testira tek na kraju.
    

**39. Koje su ključne ideje kontinualnog testiranja?**  
Testiranje u svakoj fazi, automatski i brzo

-   **Obrazloženje:** Testiranje mora biti integrisano u CI/CD pipeline.
    
-   **Primer:** Svaki commit pokreće unit, integration i end-to-end testove.
    

**40. Kakva je uloga automatizovanog testiranja u kontinualnom testiranju?**  
Ključna – omogućava brzinu i konzistentnost

-   **Obrazloženje:** Bez automatizacije testiranje bi bilo presporo.
    
-   **Primer:** Selenium testovi pokreću se automatski na svakom buildu.
    

**41. Kako izgleda proces funkcionisanja deployment pipeline-a?**  
Commit → Build → Testovi → Deployment na test/staging → Deployment na produkciju

-   **Obrazloženje:** Pipeline osigurava da se svaka promena validira.
    
-   **Primer:** Jenkins pipeline sa više stage-ova.
    

**42. Koje su pretpostavke za uspostavljanje prakse kontinualne integracije?**  
Česti commit-ovi, automatizovani testovi, centralna glavna grana, brzi build-ovi

-   **Obrazloženje:** Bez ovih uslova CI ne funkcioniše.
    
-   **Primer:** GitHub Actions sa pravilom da svaki PR mora proći testove pre merge-a.
    

**43. Šta je smisao rane detekcije grešaka automatizovanim testovima?**  
Manji troškovi i brže ispravke

-   **Obrazloženje:** Greške otkrivene rano su najjeftinije.
    
-   **Primer:** Unit test otkrije problem odmah, umesto da se bug pojavi u produkciji.
    

**44. Šta je idealna test piramida?**  
Puno unit testova, manje integration testova, još manje end-to-end testova

-   **Obrazloženje:** Većina testiranja treba da bude brza i automatizovana.
    
-   **Primer:** Google koristi milion unit testova koji se pokreću svakodnevno.
    

**45. Šta je koncept Test Driven Developmenta?**  
Pisanje testova pre implementacije koda

-   **Obrazloženje:** TDD osigurava da se piše samo potreban kod i da radi kako treba.
    
-   **Primer:** Developer piše test “function X vraća Y”, pa tek onda implementira funkciju.
    

**46. Šta je koncept kontinualne integracije?**  
Stalno spajanje koda na glavnu granu uz automatizovane testove i build-ove

-   **Obrazloženje:** Sprečava integracione konflikte i ubrzava razvoj.
    
-   **Primer:** Svaki commit prolazi kroz Jenkins CI server.
    

**47. Šta su i koje prakse minimizuju integracione probleme?**  
Česti commit-ovi, rad na glavnoj grani, mali taskovi, automatizovani testovi

-   **Obrazloženje:** Integracija postaje deo svakodnevnog rada, a ne poseban događaj.
    
-   **Primer:** GitFlow sa kratkim granama i dnevnim merge-ovima.
    

**48. Zašto je potrebna automatizacija procesa isporuke?**  
Zbog brzine, ponovljivosti i pouzdanosti

-   **Obrazloženje:** Ručni deploy je spor i sklon greškama.
    
-   **Primer:** Continuous Delivery pipeline.
    

**49. Koje korake procesa isporuke se može automizovati?**  
Build, test, deployment, konfiguracija, monitoring

-   **Obrazloženje:** Svaki ponovljivi korak treba automatizovati.
    
-   **Primer:** Docker image se automatski build-uje i deploy-uje u Kubernetes.
    

**50. Zašto je bitno da razvojni timovi učestvuju u deployment-u?**  
Zbog odgovornosti i bržeg rešavanja problema

-   **Obrazloženje:** Dev i Ops dele vlasništvo nad sistemom.
    
-   **Primer:** DevOps tim deploy-uje novu verziju i prati logove.
    

**51. Koje zahteve treba da ispune alati koji potpomažu automatizaciju isporuke?**  
Brzina, pouzdanost, integracija sa drugim alatima, skalabilnost

-   **Obrazloženje:** Alati moraju podržavati moderne CI/CD procese.
    
-   **Primer:** Jenkins, GitLab CI, ArgoCD.
    

**52. Koje prednosti donosi mogućnost isporuke koda „na zahtev“?**  
Brža reakcija na potrebe korisnika, manji rizik, fleksibilnost

-   **Obrazloženje:** Deployment se vrši kada je organizaciji najpogodnije.
    
-   **Primer:** E-commerce platforma pušta hotfix odmah pre Black Friday prodaje.
    

**53. Zašto je dobro razdvojiti isporuku (deployment) i lansiranje nove verzije (za korisnike aplikacije)?**  
Da bi se smanjio rizik i omogućila kontrolisana aktivacija

-   **Obrazloženje:** Kod može biti deploy-ovan, ali “feature flag” određuje kada korisnici vide novu funkciju.
    
-   **Primer:** Facebook koristi feature flag-e da kontroliše postepeno lansiranje funkcionalnosti.
    

**54. Koji obrasci za lansiranje novih verzija aplikacija postoje?**  
Blue/Green, Canary release, Cluster immune system, feature flags

-   **Obrazloženje:** Svaki obrazac ima prednosti za smanjenje rizika.
    
-   **Primer:** Blue/Green omogućava instant rollback.
    

**55. Šta je plavo/zeleno obrazac lansiranja (blue/green pattern)?**  
Dve identične produkcione okoline – jedna aktivna, jedna spremna za switch

-   **Obrazloženje:** Omogućava bezbedan i brz rollback.
    
-   **Primer:** AWS Elastic Beanstalk podržava Blue/Green deployment.

**56. Šta je obrazac Canary release?**  
Postepeno lansiranje nove verzije ka manjoj grupi korisnika pre nego svima

-   **Obrazloženje:** Time se rizik ograničava, a problemi se otkrivaju na malom uzorku.
    
-   **Primer:** Twitter pusti novu funkcionalnost prvo 1% korisnika, pa ako nema problema, postepeno širi na ostale.
    

**57. Šta je Cluster immune system pattern?**  
Automatsko isključivanje ili izolovanje problematičnih delova sistema

-   **Obrazloženje:** Kao imuni sistem tela – sistem se sam brani od problema i sprečava širenje grešaka.
    
-   **Primer:** Kubernetes health check automatski isključuje pod koji ne radi ispravno.
    

**58. Koji su obrasci lansiranja koji se baziraju na samim aplikacijama?**  
Feature toggle (flags), A/B testiranje, progressive delivery

-   **Obrazloženje:** Omogućavaju aktiviranje ili testiranje novih funkcionalnosti bez kompletnog deploy-a.
    
-   **Primer:** Netflix koristi feature flags da uključi/isključi nove opcije bez restarta aplikacije.
    

**59. Koje korake procesa isporuke se može automatizovati?**  
Build, testiranje, deployment, konfiguracija, monitoring

-   **Obrazloženje:** Automatizacija omogućava brzinu i pouzdanost.
    
-   **Primer:** CI/CD pipeline automatski pokreće testove i deploy.
    

**60. Zašto je bitno da razvojni timovi učestvuju u deployment-u?**  
Da bi delili odgovornost i brže reagovali na probleme

-   **Obrazloženje:** Kada tim učestvuje u isporuci, više pazi na kvalitet.
    
-   **Primer:** DevOps tim deploy-uje novu verziju i prati metrike posle puštanja.
    

**61. Koje zahteve treba da ispune alati koji potpomažu automatizaciju isporuke?**  
Pouzdanost, brzina, skalabilnost, integracija sa drugim alatima

-   **Obrazloženje:** Alati moraju podržavati moderne prakse DevOps-a.
    
-   **Primer:** GitLab CI/CD i ArgoCD obezbeđuju integraciju sa Git-om i Kubernetes-om.
    

**62. Koje prednosti donosi mogućnost isporuke koda „na zahtev“?**  
Fleksibilnost, manji rizik, brže reagovanje na potrebe korisnika

-   **Obrazloženje:** Kod se može pustiti kada to biznisu odgovara, ne kada “pipeline završi”.
    
-   **Primer:** Online shop odmah deploy-uje hotfix pred akciju.
    

**63. Zašto je dobro razdvojiti isporuku (deployment) i lansiranje nove verzije (za korisnike aplikacije)?**  
Da bi se smanjio rizik i omogućila kontrolisana aktivacija

-   **Obrazloženje:** Kod može biti deploy-ovan, ali feature flag određuje kada korisnici dobijaju novu verziju.
    
-   **Primer:** Facebook i Google koriste feature flag-e za “silent deploy” – kod je već tu, ali se korisnicima aktivira tek kad tim proceni.