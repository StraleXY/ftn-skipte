# 1: Petri mreže i njihove vrste

Petri mreže predstavljaju formalni model za specifikaciju i analizu poslovnih procesa. Osnovne komponente su mesta (krugovi), prelazi (pravougaonici) i lukovi (strelice). Moguće je pratiti tok izvršavanja procesa pomoću tokena.

**Primer:**  
Zamislimo proces naručivanja proizvoda: korisnik (mesto) izvršava narudžbinu (prelaz) i stanje se menja u "narudžbina poslata" (novo mesto). Token se pomera kroz mrežu kako bi označio progres.

---

**1. Šta su Petri mreže?**  
Petri mreže su formalna i apstraktna tehnika za modelovanje poslovnih procesa sa matematičkom osnovom.

**2. Koji gradivni elementi čine Petri mreže?**  
• Mesta – krugovi  
• Prelazi – kvadrati  
• Usmereni lukovi – linije sa strelicama između mesta i prelaza

**3. Kako se u Petri mrežama može pratiti stanje mreže tj. progres izvršavanja procesa?**  
Pomoću tokena koji se nalaze u mestima mreže.

**4. Šta izdvaja Petri mreže od drugih manje formalnih modela?**  
Matematička formalizacija.

**5. Klasifikacija Petri mreža:**  
• Mreže uslovnih događaja  
• Mreže tranzicije mesta  
• Kolor Petri mreže

**6. Koji su uslovi za okidanje tranzicija u osnovnoj klasi Petri mreža?**  
Tranzicija je omogućena kada su ulazna mesta popunjena, a izlazna prazna.

**7. Šta su mreže tranzicije mesta?**  
Proširenje osnovnih Petri mreža koje dozvoljava više tokena u jednom mestu i koristi težine grana.

**8. Šta su Kolor Petri mreže?**  
Omogućavaju tokenima da imaju strukturu, identitet i vrednost pomoću "boja".

---

### Rezime sekcije 1:
- Petri mreže se koriste za formalno modelovanje toka procesa.
- Tokeni prate stanje.
- Postoje varijante koje dodaju složenost: tranzicije mesta i boje.
- **Primer zbunjujućeg pitanja (br. 6):** Ako su ulazna mesta puna a izlazna takođe, tranzicija se neće izvršiti.

# 2: ARIS, Workflow i notacije

Ova sekcija pokriva različite notacije i alate za modelovanje, uključujući ARIS, Workflow mreže i EPK.

**Primer:**  
ARIS "kuća" objašnjava kako IS treba da ima podatke, funkcije i kontrole, kao i više nivoa apstrakcije.

---
**9. Šta je ARIS House?**  
• ARIS House kaže da svaki informacioni sistem počiva na tri stuba (podaci, kontrole i funkcije), a krov predstavlja celu organizaciju.  
• U svakoj zoni postoje tri nivoa apstrakcije: konceptualni, arhitektura i implementacioni.

**10. Šta su procesni lanci upravljani događajima?**  
Neformalna notacija za predstavljanje specifičnih koncepata i procesa u određenom domenu, deo ARIS metodologije.

**11. Šta su Workflow mreže? Koja dodatna ograničenja uvode?**  
Workflow mreže su Petri mreže sa dodatnim pravilima: imaju početno i krajnje mesto, sve ostale komponente su povezane putem između njih.

**12. Šta se postiže „sintaksnim zaslađivanjem“ notacije Petri mreža?**  
Olakšava se čitanje modela tako što se grananja dodatno vizuelno obeleže.

---

### Rezime sekcije 2:
- ARIS definiše informacione sisteme kroz stubove i nivoe apstrakcije.
- Workflow mreže su specijalni slučaj Petri mreža sa jasno definisanim početkom i krajem.
- EPK i "zaslađivanje" olakšavaju čitanje i interpretaciju.
- **Primer:** Ako model ima više krajnjih mesta – to krši workflow pravilo.

# 3: Koreografije i interakcije

Koreografije opisuju saradnju između više učesnika (npr. kompanija) u poslovnim procesima. Fokus nije na unutrašnjem izvršavanju već na porukama koje razmenjuju.

**13. Šta su i šta modeluju koreografije?**  
Modeluju konverzaciju procesa – omogućavaju interoperabilnost između orkestracija različitih učesnika.


**14. Šta je model interakcije?**  
Modeli interakcije čine koreografiju procesa. Svaki model je povezan sa dva modela komunikacionih aktivnosti.

**15. Šta je model komunikacionih aktivnosti?**  
To je model aktivnosti u procesu koji ima sposobnost komunikacije – slanje ili prijem poruka.

**16. Šta je konverzacija u kontekstu koreografija?**  
Konverzacija je instanca modela koreografije procesa.

**17. Koje su dve glavne faze razvoja koreografija?**  
• Dizajn faza  
• Implementacija

**18. Koje su ključne aktivnosti u dizajn fazi koreografija?**  
• Domain scoping  
• Participation identification  
• Scenario modeling  
• Milestone definition

**19. Koje su ključne aktivnosti u fazi implementacije koreografije?**  
• Behavioural Interfaces  
• Process orchestration

**20. Koje aktivnosti se nalaze u graničnoj zoni dizajna i implementacije i zašto?**  
• Message identification  
• Choreography definition  
Ove aktivnosti uzimaju u obzir i poslovne i tehničke aspekte.
  
• Definisanje učesnika, scenarija, poruka i tačaka sinhronizacije (milestone).  
• Ključne faze: dizajn, implementacija, identifikacija poruka, definicija ponašanja.

**Primer:**  
Kompanija A naručuje robu od B, a B koristi logistiku od C. Koreografija opisuje redosled i format poruka između A, B i C.

**21. Šta je rezultat identifikacije učesnika u koreografiji?**  
Rezultat su definisane uloge učesnika (organizacija) u koreografiji.

**22. Šta je rezultat definicije kritičnih tačaka?**  
Definisana su stanja u koreografiji u kojima su saradnjom učesnika postignuti određeni rezultati.

**23. Šta je smisao kritičnih tačaka koreografije?**  
Definišu ponašanje učesnika u koreografiji i redosled događaja.

**24. Šta se obavlja u identifikaciji poruka?**  
Definišu se poruke i njihov format koje se razmenjuju u interakcijama.

**25. Šta se obavlja tokom definicije koreografije?**  
Kombinuju se podaci iz prethodnih faza da bi se formirao model ponašanja.

**26. Šta predstavljaju interfejsi ponašanja?**  
Definišu interfejse za svaku ulogu u koreografiji i služe kao osnova za orkestraciju procesa.

**27. Da li i kako interfejsi ponašanja mogu uticati na orkestraciju procesa?**  
Da, određuju kada se interfejsi pozivaju u internim orkestracijama procesa.

**28. Šta su scenariji saradnje?**  
Scenariji saradnje su interakcije između učesnika koje omogućavaju napredovanje koreografije od jedne do druge kritične tačke.

**29. Kako se može predstaviti dizajn ponašanja sistema pri dizajniranju koreografije?**  
Može se predstaviti BPMN notacijom, gde su kritične tačke predstavljene kao događaji.

**30. Šta je kompatibilnost u kontekstu koreografija i šta ona obezbeđuje?
Kompatibilnost označava sposobnost učesnika da uspešno sarađuju po pravilima koreografije.**  
Obezbeđuje izbegavanje nesporazuma i neusaglašenosti tokom komunikacije.

---

### Rezime sekcije 3:
- Koreografije služe za međusobnu komunikaciju između procesa.
- Mora se znati ko, kada i kako komunicira.
- **Primer zbunjujućeg pitanja (br. 30):** Kompatibilnost nije samo da svi mogu pričati, već i da razumeju poruke.

# 4: BPMN, adaptacije i provera korektnosti

BPMN se koristi za vizualizaciju procesa, a korektnost se proverava pomoću Petri mreža i posebnih pravila.

**31. Šta je strukturna kompatibilnost?**  
Kompatibilnost procesa gledana kroz strukturu komunikacije.

**32. Koje tipove strukturne kompatibilnosti razlikujemo?**  
• Jaka – za svaku poruku postoji pošiljalac i primalac  
• Slaba – nije neophodno da sve poruke dobiju odgovor

**33. Šta je kompatibilnost ponašanja?**  
Uzima u obzir redosled izvršavanja – kako učesnici međusobno aktiviraju procese.

**34. Kojom adaptacijom Petri mreža se može proveriti kompatibilnost ponašanja?**  
Pomoću workflow modula.

**35. Šta su workflow moduli?**  
Workflow mreže koje sadrže komunikaciona mesta – šalju i primaju poruke između učesnika.

**36. Da li spajanjem workflow modula može nastati model čija kompozicija nije korektna?**  
Može – ako komunikacija nije dosledna, moguće je da proces ne funkcioniše kako je zamišljeno.

**37. Koje transformacije Petri mreža su dozvoljene, a da ne narušavaju ponašanje mreže?**  
• Petlja  
• Obilazak  
• Konkurentna grana

**38. Koji su šabloni interakcije?**  
• Po broju učesnika: bilateralni i multilateralni  
• Po broju poruka: jedna ili više transmisija  
• Varijacije u prijemu poruka: round trip, routed interaction

**39. Šta predstavlja obrazac zahteva preko posrednika (Request with referral)?**  
A šalje poruku B-u, ali referiše na C. B na osnovu toga dalje komunicira sa C.

**40. Šta je obrazac prosleđenog zahteva (Relaying request)?**  
A šalje B-u koji prosleđuje C-u, a C komunicira nazad sa A.

**41. Koji su osnovni elementi BPMN konverzacionih dijagrama?**  
• Pool  
• Multiple Instances Pool  
• Conversation  
• Sub-Conversation  
• Call Conversation  
• Conversation Link

**42. Koji je ključni element BPMN dijagrama koreografije?**  
Zadržavanje linije učesnika u razmeni poruka – ako se izgubi, koreografija je nesprovediva.

**43. U kom slučaju se koreografija može označiti kao nesprovediva?**  
Ako učesnici nemaju informacije o prethodnim aktivnostima koje su uslov za sledeće.

**44. Šta je neophodno da bi koreografija bila sprovediva (enforceable)?**  
Inicijator mora imati uvid u to da li su prethodne komunikacije uspešno završene.

**45. O kojim specifičnim situacijama se mora voditi računa pri grananjima u koreografijama?**  
Svi učesnici na koje utiče izbor moraju imati informacije o uslovima izbora.

**46. Kakva može biti međuzavisnost podataka između različitih aktivnosti u procesu?**  
Može biti direktna (deljenje podataka) ili implicitna (preko tokova). Podaci opisuju konkretan slučaj obrade.

**47. Šta je strukturna ispravnost?**  
Postoji tačno jedan početni i jedan krajnji čvor, a svi ostali su povezani putem između njih.

**48. Šta je teorema korektnosti?**  
Workflow mreža se zatvara dodatnom tranzicijom t* od kraja ka početku. Ako tako zatvorena mreža ostane živa i ograničena, model je korektan.

**49. Šta su mreže slobodnog izbora?**  
Podskup Petri mreža kod kojih je moguće polinomijalno odrediti validnost modela.

**50. Šta je relaksirani kriterijum korektnosti?**  
Model je prihvatljiv ako postoje putevi koji vode ka željenom ishodu – čak i ako nije sve precizno definisano.

**51. Šta je slabi kriterijum korektnosti?**  
Važno je da se može doći do cilja iz svakog dostižnog stanja, čak i ako se ne koriste sve mogućnosti sistema.

---

### Rezime sekcije 4:
- Korektnost se formalno dokazuje pomoću Petri mreža.
- Postoje različiti nivoi dozvoljenih "grešaka".
- **Primer:** Ako postoji mesto koje je izolovano (nije dostupno iz početka), model je strukturno neispravan.

# 5: Sistemska arhitektura i fleksibilnost

Ova sekcija pokriva sisteme koji implementiraju sve gore navedeno.

**52. Koje komponente predviđa opšta arhitektura za upravljanje poslovnim tokovima?**  
Modelovanje, repozitorijum, izvršni sistem (engine), GUI, integracija sa drugim aplikacijama.

**53. Šta je WfMC referentni model?**  
Standardizovan model arhitekture sistema za upravljanje poslovnim procesima.

**54. Šta je ideja fleksibilnog upravljanja poslovnim procesima?**  
Izvršavanje nije fiksno – model i instanca se mogu menjati nezavisno.

**55. Šta je koncept dinamičke adaptacije modela procesa?**  
Omogućava prilagođavanje instanci procesa u realnom vremenu – kada se promene uslovi rada.

**56. Koji su aspekti međuzavisnosti podataka?**  
• Aktivnosti koriste zajedničke podatke  
• Podaci mogu uticati na tok procesa

**57. Čemu služi analiza dostupnosti?**  
Vizuelizacija svih mogućih stanja mreže, pomoću grafa dostupnosti – koristi se za proveru validnosti workflow mreže.

---

### Rezime sekcije 5:
- Sistemi moraju biti prilagodljivi i imati podršku za modelovanje i izvršavanje.
- Analiza dostupnosti proverava da li je proces validan.
- **Primer:** Ako korisnik ne može da pređe iz stanja "naručeno" u "plaćeno", model nije validan.