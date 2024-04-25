Zbirni LOC: 153 LOC (calculator.java + start.java) + 19 LOC (licence)

Calculator.java

LOC 134

Broj čvorova (n): 34 Broj bridova (e): 40

C=E-N+2=40-34+2=4 Ciklomatska složenost iznosi 4.

Kognitivnu slozenost, možemo primetiti da metoda evaluateExpression ima nekoliko grananja i petlji koje bi mogle otežati čitanje i razumevanje koda. Metoda Calculate ima mnogo grananja, što takođe može povećati kognitivnu složenost.

Statička analiza:

Linije 12-16: Statički finalni simboli su dobro definisani i koriste se konvencionalno.

Linije 28-58: Metoda evaluateExpression ima dugačak blok koda koji bi mogao biti refaktorisan u manje metode radi bolje čitljivosti i održavanja.

Linije 60-86: Metoda Calculate takođe ima dugačak blok koda koji bi mogao biti refaktorisan na sličan način.

Postoji potencijal za dodavanje komentara radi boljeg objašnjenja složenih delova logike.

Code Smells:

Statička promjenljiva finalResult: Statičke promenljive se često izbegavaju, posebno ako nisu potrebne. Treba koristiti lokalne promenljive unutar metoda gde je to moguće.
Korištenje Stringa za matematičke operacije: Metoda ToString u unutrašnjoj klasi Operations vraća string koji predstavlja simbole matematičkih operacija.
Dugačke metode: Metoda evaluateExpression i Calculate su relativno duge i složenešto otežava održavanje i razumevanje koda.
Nepotrebno korištenje ToSting
Nesigurna upotreba try-catch bloka: U metodi evaluateExpression koristi se try-catch blok bez preciznog navođenja izuzetaka koji se hvataju. Treba specificirati izuzetke.
Nekonzistentna upotreba zagrada u kontrolnim strukturama: U nekim delovima koda, nema zagrada oko blokova koda u if i else konstrukcijama, što može dovesti do problema sa čitljivošću i potencijalno uvođenje grešaka.
Start.java

LOC 19

Broj čvorova (n): 3
Broj bridova (e): 2

C=E-N+2=2-3+2=1
Ciklomatska složenost iznosi 1.

Program je jednostavan, sa jednom petljom i jednim grananjem što znači da će kognitivna složenost biti niska upravo zbog jednostavnosti strukture i logike.

Statička analiza:

	Linija 3: `String Expression;`Varijabla `Expression` je deklarisana, ali trenutno nema vrednosti. Može dovesti do potencijalne NullPointerException greške.

	Linije 5-10: Unutrašnja petlja `while (active) { ... }`Kod unutar ove petlje zahteva unos korisnika i obradu unosa dok korisnik ne unese "exit". Ovo deluje ispravno, sve dok korisnik ne unese nešto što nije validan izraz.

	Linija 7: Scanner scanIn;` Varijabla `scanIn` se deklariše unutar petlje. Deklaracija izvan petlje neće dovoditi do ponovnog kreiranja skenera u svakoj iteraciji petlje.
Ovaj kod djeluje ispravno i obavlja očekivane funkcionalnosti. Međutim, postoji nekoliko mesta gdje se može dodati provera kako bi se poboljšala robusnost i rukovanje potencijalnim greškama.

Code Smells:

Linije 9-19: Otvaranje novog Scanner-a unutar petlje se može izbeći kreiranjem objekta Scanner jednom izvan petlje i ponovo ga koristiti.
