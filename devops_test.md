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

<br></br>
# Arhitektura i tehničke prakse povratnih informacija

**12. Koje tipove arhitektura razlikujemo i koje vrste arhitektura obezbeđuju visoku produktivnost, dobre mogućnosti testiranja i bezbednost isporučene aplikacije?**  
Monolitne, slojevite, mikroservisne, event-driven i serverless arhitekture; visoku produktivnost i testabilnost najčešće daju **mikroservisi** i **serverless**, jer omogućavaju nezavisno razvijanje, testiranje i deployment.

-   **Obrazloženje:** Monolit je jednostavan za start, ali se teško održava; mikroservisi omogućavaju skaliranje i agilnost; serverless daje fokus na biznis logiku bez održavanja infrastrukture.
    
-   **Primer:** Netflix koristi mikroservisnu arhitekturu za hiljade servisa koji rade nezavisno i omogućavaju brze promene.
    

**13. Koje su tehničke prakse koje omogućavaju uspostavljanje kvalitetnih povratnih informacija?**  
Automatizovani testovi, CI/CD pipeline, monitoring, logovanje, code review, A/B testovi.

-   **Obrazloženje:** Povratne informacije moraju biti brze i tačne da bi tim mogao reagovati odmah.
    
-   **Primer:** GitHub Actions pipeline odmah prijavljuje developeru ako unit test padne nakon commita.
    

**14. Šta je ključna ideja obezbeđivanja odgovarajuće telemetrije – šta se time postiže u smislu razvoja i isporuke aplikacija?**  
Cilj telemetrije je prikupljanje podataka o radu aplikacije da bi se obezbedilo praćenje performansi, stabilnosti i korisničkog iskustva.

-   **Obrazloženje:** Bez telemetrije, tim razvija „na slepo“ i ne zna kako se aplikacija ponaša u realnom svetu.
    
-   **Primer:** Prometheus i Grafana prikupljaju i prikazuju metrike kao što su latency i CPU usage.
    

**15. Kako se postojanje dobrih telemetrijskih podataka odražava na sposobnost organizacije da uoči i razreši nastale probleme?**  
Brže otkrivanje i rešavanje problema, proaktivno reagovanje umesto čekanja da korisnici prijave grešku.

-   **Obrazloženje:** Kada sistem ima dobre metrike i logove, incidenti se rešavaju u minutima, a ne satima ili danima.
    
-   **Primer:** AWS CloudWatch alarmi obaveste tim pre nego što korisnici primete pad performansi.
    

**16. Koje sve podatke treba obuhvatiti telemetrijom?**  
Performanse (latency, throughput), resurse (CPU, memorija), logove, greške, korisničko ponašanje, sigurnosne događaje.

-   **Obrazloženje:** Što je širi spektar podataka, tim ima bolji uvid u zdravlje sistema.
    
-   **Primer:** E-commerce aplikacija meri koliko korisnika napusti checkout stranicu i zašto.
    

**17. Da li je samo prikupljanje telemetrijskih podataka dovoljno? Ako nije, šta je još potrebno obezbediti?**  
Nije dovoljno – potrebno je obezbediti analizu, vizualizaciju i reagovanje (alarme).

-   **Obrazloženje:** Podaci bez obrade su beskorisni – mora postojati sistem koji ih pretvara u akcione informacije.
    
-   **Primer:** Kibana dashboard omogućava analizu logova i brzo otkrivanje anomalija.
    

**18. Šta označava pojam “instrumentalizacije funkcionalnosti” u vašim aplikacijama?**  
Dodavanje koda i alata za merenje rada aplikacije i korisničkog iskustva.

-   **Obrazloženje:** Instrumentalizacija znači da aplikacija sama daje podatke o svom zdravlju i ponašanju.
    
-   **Primer:** Google Analytics integrisan u aplikaciju meri broj klikova i vreme provedeno na stranici.
    

**19. Kako se u smislu telemetrije mogu koristiti logovi?**  
Logovi služe za praćenje toka izvršavanja, otkrivanje grešaka i analizu ponašanja sistema.

-   **Obrazloženje:** Logovi su osnovni izvor istine – bez njih je teško razumeti šta se desilo u sistemu.
    
-   **Primer:** ELK stack (Elasticsearch, Logstash, Kibana) koristi se za centralizovano prikupljanje i pretragu logova.

<br></br>
# Telemetrija i analiza podataka

**20. Sa kojih sve nivoa okruženja/aplikacije treba prikupljati telemetrijske podatke?**  
Sa infrastrukture, aplikacije, baze podataka, mreže i korisničkog interfejsa.

-   **Obrazloženje:** Problemi mogu nastati bilo gde u sistemu – zato treba pratiti ceo stack.
    
-   **Primer:** Monitoring CPU i RAM-a (infrastruktura), API latency (aplikacija), slow queries (baza), packet loss (mreža), UX metrike (frontend).
    

**21. Koje tehnike se koriste za analizu telemetrijskih podataka?**  
Statistička analiza, mašinsko učenje, korelacija događaja, vizualizacija i outlier detection.

-   **Obrazloženje:** Cilj analize je otkrivanje anomalija i uzroka problema.
    
-   **Primer:** Prometheus + Grafana za vizualizaciju; ML modeli za predikciju opterećenja servera.
    

**22. Šta je “outlier detection”?**  
Otkrivanje podataka koji značajno odstupaju od normalnog obrasca.

-   **Obrazloženje:** Outlieri često ukazuju na anomalije, greške ili napade.
    
-   **Primer:** Nagli skok u broju HTTP 500 grešaka ukazuje na bug posle novog deploy-a.
    

**23. Koje se statističke mere često koriste za analizu telemetrijskih podataka? Koje je ograničenje njihove upotrebe?**  
Prosek, medijana, percentili (p95, p99); ograničenje je da prosek može sakriti anomalije.

-   **Obrazloženje:** Percentili bolje prikazuju realno korisničko iskustvo od proseka.
    
-   **Primer:** Prosek latencije API-ja je 200ms, ali p99 je 3s → mali deo korisnika ima loše iskustvo.
    

**24. Kako se obrađuju telemetrijski podaci koji po prirodi nemaju normalnu raspodelu?**  
Korišćenjem medijane, percentila i robustnih metoda, a ne proseka.

-   **Obrazloženje:** Mnoge metrike (npr. latencija) imaju „long-tail“ raspodelu, pa prosek vara.
    
-   **Primer:** Google SRE koristi p95/p99 metrika za praćenje performansi servisa.
    

**25. Kako se koriste alarmi bazirani na telemetrijskim podacima, koji nivoi alarma postoje i da li su dobri alarmi samo oni koji pokazuju da je nešto VEĆ otkazalo?**  
Postoje upozoravajući (warning) i kritični (critical) alarmi; dobri alarmi ne čekaju otkazivanje, već upozoravaju na trendove.

-   **Obrazloženje:** Preventivni alarmi omogućavaju reakciju pre nego što dođe do incidenta.
    
-   **Primer:** Alarm se pali ako CPU prelazi 80% duže od 10 minuta, pre nego što aplikacija padne.
    

**26. Kada se koriste tehnike za detekciju anomalija?**  
Kada standardni alarmi nisu dovoljni i kada postoji kompleksan obrazac ponašanja.

-   **Obrazloženje:** Anomalije mogu ukazivati na sigurnosne incidente, greške ili neobično ponašanje korisnika.
    
-   **Primer:** Detekcija nenormalno velikog broja login pokušaja može ukazivati na brute-force napad.
    

**27. Kako telemetrijski podaci mogu da pomognu u procesu isporuke (deployment-a)?**  
Pomažu pri verifikaciji nove verzije i otkrivanju problema nakon puštanja u rad.

-   **Obrazloženje:** Telemetrija pokazuje da li je sistem i dalje stabilan nakon deploy-a.
    
-   **Primer:** Canary release prati CPU usage i error rate nove verzije pre nego što se pusti svim korisnicima.
    

**28. Zašto je poželjno da članovi tima učestvuju u upravljanju aplikacijom nakon isporuke?**  
Da bi preuzeli odgovornost za kvalitet i brže rešavali probleme.

-   **Obrazloženje:** DevOps kultura traži da developeri budu uključeni i nakon deploy-a (You build it, you run it).
    
-   **Primer:** Amazon timovi dežuraju (on-call) za aplikacije koje sami razvijaju.
    

**29. Koje se tehničke prakse koriste kako bi se bolje integrisala iskustva korisnika u dalji razvoj aplikacija?**  
A/B testiranje, feature flagovi, prikupljanje korisničkih metrika, ankete, feedback sistemi.

-   **Obrazloženje:** Povratne informacije od korisnika oblikuju razvoj i prioritete.
    
-   **Primer:** Facebook pušta dve verzije UI-a i meri na kojoj korisnici provode više vremena.

<br></br>
# Kontinualno učenje, postmortem i baza znanja

**30. Šta su A/B testovi?**  
Eksperimenti u kojima se korisnici nasumično dele na grupe i dobijaju različite verzije aplikacije.

-   **Obrazloženje:** Cilj je da se testira koja verzija daje bolje rezultate (performanse, engagement, prodaja).
    
-   **Primer:** E-commerce sajt testira dva dizajna checkout stranice i meri konverziju.
    

**31. Šta je proces revizije koda?**  
Pregled koda od strane kolega pre nego što se spoji na glavnu granu.

-   **Obrazloženje:** Revizija povećava kvalitet, otkriva greške i deli znanje među timom.
    
-   **Primer:** Pull Request na GitHub-u gde kolega ostavlja komentare i predloge.
    

**32. Koje su prednosti revizije koda u odnosu na postupak klasičnog odobravanja softverskog rešenja?**  
Bolja detekcija grešaka, učenje, standardizacija stila, smanjenje tehničkog duga.

-   **Obrazloženje:** Revizija je stalni proces, a ne jednokratna formalnost.
    
-   **Primer:** U timu od 5 ljudi svaka promena prolazi barem kroz 2 para očiju pre spajanja.
    

**33. Koje tehničke prakse se koriste za podršku principu kontinualnog učenja?**  
Postmortem analize, retrospektive, A/B testovi, eksperimentisanje, pair programming.

-   **Obrazloženje:** Učenje se ugrađuje u svakodnevni rad, ne ostavlja se za kraj.
    
-   **Primer:** Agile tim posle svakog sprinta ima retrospektivu sa lekcijama naučenim.
    

**34. Šta je post-mortem analiza aplikacija i koje činjenice ona treba da utvrdi?**  
Analiza incidenta sa ciljem razumevanja uzroka i učenja.

-   **Obrazloženje:** Utvrđuje šta se desilo, zašto, i kako sprečiti ponavljanje – bez traženja krivca.
    
-   **Primer:** Google SRE dokumentuje incident, timeline događaja i mere prevencije.
    

**35. Zašto je bitno obezbediti objavljivanje rezultata analiza problema?**  
Da bi cela organizacija naučila iz greške, a ne samo tim pogođen incidentom.

-   **Obrazloženje:** Deljenje znanja smanjuje rizik ponavljanja istih problema.
    
-   **Primer:** Etsy javno objavljuje postmortem analize kritičnih incidenata.
    

**36. Čemu služi tehnika namernog kontrolisanog ubacivanja „otkaza“ u pred i produkciona okruženja?**  
Testira otpornost sistema na kvarove (Chaos Engineering).

-   **Obrazloženje:** Ako sistem preživi simulirane kvarove, biće spreman i za stvarne.
    
-   **Primer:** Netflix Chaos Monkey namerno gasi servere u produkciji da testira stabilnost.
    

**37. Koja je svrha „game days“ u smislu analize ponašanja sistema prilikom pojave problema?**  
Organizovani treninzi za timove da reaguju na simulirane incidente.

-   **Obrazloženje:** Priprema tim na realne krize i jača timsku koordinaciju.
    
-   **Primer:** Amazon organizuje „game day“ gde tim rešava simulirani pad servisa.
    

**38. Kako se mogu lokalna saznanja transformisati u globalno širenje saznanja i poboljšanja sveukupnih performansi organizacije?**  
Kroz deljenje znanja (baze znanja, dokumentacija, interne radionice).

-   **Obrazloženje:** Znanje mora da se multiplicira kroz celu organizaciju.
    
-   **Primer:** Incident report iz jednog tima se deli celom DevOps odeljenju.
    

**39. Kako je moguće oformiti „bazu znanja“ unutar organizacije i zašto je bitno da ona bude dostupna širokom krugu korisnika?**  
Kreiranjem wiki sistema, Confluence-a, ili interne dokumentacije.

-   **Obrazloženje:** Baza znanja smanjuje dupliranje rada i ubrzava rešavanje problema.
    
-   **Primer:** Atlassian Confluence sadrži vodiče, best practices i postmortem analize dostupne svima.
    

**40. Kako se analizira da li primenjena tehnologija predstavlja dobro rešenje za postavljeni zadatak? Koji su indikatori da to nije tako?**  
Analizira se skalabilnost, performanse, trošak i održavanje; loši indikatori su česti kvarovi, teško testiranje i spor razvoj.

-   **Obrazloženje:** Tehnologija mora podržati ciljeve biznisa, ne usporavati ih.
    
-   **Primer:** Monolitna arhitektura postaje problem kad tim ima 100+ developera i release traje satima.
    

**41. Zašto je bitno rezervisanje vremena za organizaciono učenje?**  
Jer učenje ne nastaje samo od sebe – mora biti planirano.

-   **Obrazloženje:** Ako nema vremena, tim ostaje zarobljen u firefighting-u i ne napreduje.
    
-   **Primer:** Google ima “20% time” politiku za istraživanje i eksperimentisanje.
    

**42. Šta je „tehnički dug“ i kako se rešava?**  
Kompromisi u razvoju koji ubrzavaju kratkoročno, ali otežavaju dugoročno održavanje.

-   **Obrazloženje:** Rešava se refaktoringom, boljom dokumentacijom i planiranjem.
    
-   **Primer:** “Brzo zakucan” kod koji posle mesec dana niko ne razume i mora da se prepravlja.
    

**43. Koji oblici učenja se koriste za širenje znanja o samim softverskim proizvodima na kojima zaposleni rade, tako i unapređenje opšteg znanja?**  
Formalne obuke, interne radionice, code review, par programming, zajednice prakse.

-   **Obrazloženje:** Kombinacija formalnog i neformalnog učenja stvara balans.
    
-   **Primer:** Tim organizuje “tech talks” jednom mesečno za razmenu znanja.

<br></br>
# Bezbednost u DevOps-u

**44. Da li se informaciona bezbednost može smatrati integralnim delom DevOps ciklusa? Ili je ona posao koji dolazi na samom kraju razvojnog ciklusa?**  
Bezbednost je integralni deo DevOps ciklusa (**DevSecOps**).

-   **Obrazloženje:** Ako se ostavi za kraj, problemi se kasno otkrivaju i teško rešavaju.
    
-   **Primer:** Automatsko skeniranje koda na ranjivosti u CI pipeline-u.
    

**45. Šta obezbeđuje integracija preventivne bezbednosne kontrole na repozitorijume izvornog koda i kontrolu deljenih biblioteka?**  
Rano otkrivanje ranjivosti i zaštitu od kompromitovanih dependencija.

-   **Obrazloženje:** Većina aplikacija koristi open-source biblioteke koje mogu imati sigurnosne propuste.
    
-   **Primer:** GitHub Dependabot automatski prijavljuje ranjive verzije paketa.
    

**46. Zašto je bitno integrisati poslove bezbednosti u sam pipeline?**  
Zato što bezbednost mora biti stalna i automatizovana, a ne povremena aktivnost.

-   **Obrazloženje:** Kontinuirana bezbednost štedi vreme i smanjuje rizik.
    
-   **Primer:** Jenkins pokreće statičku analizu koda (SAST) pri svakom buildu.
    

**47. Šta treba da obuhvataju bezbednosni testovi aplikacije?**  
Testiranje ranjivosti (SQL injection, XSS), autentikacije, autorizacije, enkripcije i performansi pod opterećenjem.

-   **Obrazloženje:** Bezbednost se ne svodi samo na aplikaciju već i na podatke i korisnički pristup.
    
-   **Primer:** OWASP ZAP koristi se za automatsko testiranje web ranjivosti.
    

**48. Zašto je osim same aplikacije bitno zaštiti i razvojna i izvršna okruženja?**  
Zato što napad može doći kroz CI/CD sistem ili infrastrukturu.

-   **Obrazloženje:** Ako napadač upadne u build server, može ubaciti maliciozan kod u produkciju.
    
-   **Primer:** Zaštita Jenkins servera, Kubernetes clustera i cloud naloga.
    

**49. Kako se može iskoristiti telemetrija da pojača bezbednost aplikacija?**  
Praćenjem anomalija i sumnjivog ponašanja.

-   **Obrazloženje:** Telemetrija pomaže da se detektuju napadi ili pokušaji zloupotrebe.
    
-   **Primer:** Monitoring login pokušaja i blokiranje IP adrese posle više neuspešnih login-a.
    

**50. Koji telemetrijski podaci mogu biti od interesa sa bezbednosnog aspekta?**  
Prijave i odjave korisnika, pokušaji neuspešnog pristupa, promene konfiguracija, mrežni saobraćaj, integritet fajlova.

-   **Obrazloženje:** Ovi podaci pomažu da se identifikuju sigurnosni incidenti i pokušaji napada.
    
-   **Primer:** SIEM sistemi (npr. Splunk) koriste logove za detekciju upada i maliciozne aktivnosti.