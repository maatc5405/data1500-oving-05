# Besvarelse: SQL-Analyse

## Oppgave 1: Grunnleggende Spørringer
1.  `SELECT * FROM Vare;`
2.  `SELECT VNr, Betegnelse FROM Vare;`
3.  `SELECT DISTINCT KatNr FROM Vare;`
4.  `SELECT Fornavn, Etternavn, Stilling AS Jobbtittel FROM Ansatt;`

1.  **Forklaring:**
    SQL-spørrinigen henter alle data inklutert NULL fra tabellen Vare tabellen.

2.  **Forklaring:**
    Henter dataene fra kolonnene VNr og betengelse fra tabellen Vare

3.  **Forklaring:**
    Henter unike dataene fra kolonnene KatNr fra tabellen Vare. Altså den fjerner duplikater av dataene.

4.  **Forklaring:** ...
    Henter datene Fornavn, Etternavn, Stilling fra tabellen ansatt. En ting å legge merke til er at Stilling kolonnen blir endret til Jobbtittel kolonne.

### DEL 2

#### 1.                                                  
hobbyhuset=# 
SELECT KNr, Fornavn, Etternavn, Adresse, PostNR  
FROM Kunde 
ORDER BY KNR DESC 
LIMIT 20;

 knr  |  fornavn   |  etternavn   |           adresse            | postnr 
------+------------+--------------+------------------------------+--------
 5824 | Erland     | Hussain      | Nesttunkollen 1              | 0171
 5823 | Ailin      | Fjellvang    | Hjortlandsvegen 52           | 3681
 5822 | Gøril      | Bjørke       | Svineryggen                  | 3681
 5821 | Birgitte   | Garshol      | Jonsvollsgaten 68A           | 5912
 5820 | Elias      | Husabø       | Neshaugen 69                 | 4742
 5819 | Eystein    | Bakker       | Borgermester Platous gate 49 | 3790
 5818 | Lucas      | Kirkeby      | Petedalsheia 71              | 3790
 5817 | Abdullah   | Endal        | Gullfjellsvegen 9            | 5282
 5816 | Joakim     | Bjørgen      | Danckert Krohns gate 71      | 3606
 5815 | Gøril      | Bjørke       | Skjoldlia                    | 3681
 5814 | Bengt      | Hollund      | Mølleveien 31                | 0801
 5813 | Amina      | Alexandersen | Asylplassen 2                | 3199
 5812 | Abdirahman | Lindahl      | Solbakksvingen 27            | 4276
 5811 | Olve       | Gundersen    | Kringlebotn 25               | 0270
 5810 | Hilmar     | Bergstrøm    | Bursflata 31                 | 2302
 5809 | Søren      | Hasle        | Lilandsvegen 29              | 5859
 5808 | Johny      | Jonassen     | Nøttveitvegen 35             | 5859
 5807 | Abdirahman | Lindahl      | Solbakksvingen 27            | 4276
 5806 | Brian      | Holte        | Nedberget 49                 | 2309
 5805 | Jane       | Brandtzæg    | Elgvegen 58                  | 1286
(20 rows)


#### 2.
hobbyhuset=# 
SELECT Fornavn, Etternavn 
From Ansatt 
ORDER BY AnsNr ASC 
LIMIT 10;

  fornavn  | etternavn  
-----------+------------
 Georg     | Barth
 Gunnlaug  | Angeltveit
 Morgan    | Dalland
 Vilde     | Aksnes
 Henriette | Brobakken
 Synøve    | Bakketun
 Ragnvald  | Allum
 Oliver    | Abrahamsen
 Oda       | Cappelen
 Andrine   | Ebbesen
(10 rows)

#### 3.
hobbyhuset=# 
SELECT 
DISTINCT 
Stilling 
FROM Ansatt;

       stilling        
-----------------------
 Kundebehandler
 Markedssjef
 Innkjøper
 Daglig leder
 Lagermedarbeider
 Produktutvikler
 Regnskapssekretær
 Databaseadministrator
 Lagerleder
(9 rows)

#### 4.
hobbyhuset=# 
SELECT VNr, Betegnelse, Pris 
FROM Vare;

  vnr  |           betegnelse           |   pris   
-------+--------------------------------+----------
 10820 | Dukkehår, hvitt                |    53.50
 10822 | Dukkehår, lys brunt            |    53.50
 10830 | Nisseskjegg, 30 cm             |    66.50
 10835 | Trollhår, hvitt                |    95.00
 10854 | Bomullsgarn, grått             |    45.50
 11630 | Skinnsnor, natur               |    53.50
 12054 | Hengebjørk                     |   412.50
 12055 | Røsslyng                       |   274.50
 12056 | Einer 'Blåmann'                |   220.50
 12088 | Einer 'Tyrihans'               |   247.00
 12089 | Gran, standard                 |   166.00
 12090 | Hvitgran                       |   221.00
 12091 | Sølvgran 'Globosa'             |   329.50
 12092 | Europabarlind                  |   274.50
 13001 | Glasskuler, 100 gr             |    44.00
 15207 | Antron garn, hvit              |    28.50
 15208 | Antron garn, gul               |    28.50
 15211 | Tubeflue verktøy               |   240.00
 15217 | Kram tørrfluekorker, 5stk      |    37.00
 15559 | Kakepapir, sølv                |    44.00
 20936 | Fjær, natur                    |    29.00
 20980 | Naturfjær                      |    31.50
--More-- 

#### 5. 
hobbyhuset=# 
SELECT Navn AS "Kategorinavn", KatNr AS "KategoriID" 
FROM Kategori;

       Kategorinavn        | KategoriID 
---------------------------+------------
 Hageutstyr                |          1
 Hobbymaling               |          2
 Keramikk                  |          3
 Konfekt og marsipan       |          4
 Kurver og fletting        |          5
 Tekstil, søm og strikking |          6
 Fiske                     |          7
 Jakt                      |          8
 Modellbygging             |          9
 Bøker                     |         10
 Leker                     |         11
 Hagemøbler                |         12
 Dukker og nisser          |         13
 Busker                    |         14
 Blomsterfrø               |         15
 Blomsterløker             |         16
 Dekorasjoner              |         17
 Grønnsaksfrø              |         18
 Tresløyd                  |         19
 Hobbypakker               |         20
 Gjødsel                   |         21
(21 rows)

#### 6.
hobbyhuset=# 
SELECT COUNT(*) 
FROM Kunde 
CROSS JOIN Ordre;

    count  
--------------
 1122304
(1 row)


## Oppgave 2: WHERE-klausulen
1.  `SELECT * FROM Vare WHERE Pris > 500;`
2.  `SELECT * FROM Ansatt WHERE Stilling = 'Salgssjef' AND Årslønn > 600000;`
3.  `SELECT Fornavn, Etternavn FROM Kunde WHERE PostNr = '0001' OR PostNr = '0002';`
4.  `SELECT Betegnelse FROM Vare WHERE NOT KatNr = 1;

1.  **Forklaring:** 
    Fra tabellen Vare henter den ut alle varer som koster over 500. 

2.  **Forklaring:** 
    Denne SQL-Spørring prøver å hente ut alle stillingene med titellen "Salgssjef" og som har årslønn over 600000 fra tabellen Ansatt.

3.  **Forklaring:** 
    Henter kolonnene fornavn og etternavn fra tabellen kunder som har postNr = 001 eller postNr = 0002.

4.  **Forklaring:** 
    Henter kolonnen betegnelse fra tabellen vare hvor alle datene blir hent ut bortsett fra KatNr = 1.

### DEL 2

#### 1. 
hobbyhuset=# 
SELECT * 
FROM Vare 
WHERE Pris > 200 AND Pris < 500;

  vnr  |           betegnelse           |  pris  | katnr | antall | hylle 
-------+--------------------------------+--------+-------+--------+-------
 12054 | Hengebjørk                     | 412.50 |    14 |      0 | D01
 12055 | Røsslyng                       | 274.50 |    14 |      0 | D01
 12056 | Einer 'Blåmann'                | 220.50 |    14 |      0 | D01
 12088 | Einer 'Tyrihans'               | 247.00 |    14 |      0 | D01
 12090 | Hvitgran                       | 221.00 |    14 |      0 | D01
 12091 | Sølvgran 'Globosa'             | 329.50 |    14 |      0 | D01
 12092 | Europabarlind                  | 274.50 |    14 |      0 | D01
 15211 | Tubeflue verktøy               | 240.00 |     7 |     39 | B42
 21037 | Figurtråd, 50 m                | 338.00 |    17 |      0 | B36
 22055 | Bensinkanne 5 ltr., grønn      | 246.50 |     1 |    110 | A27
 25079 | Trillebår                      | 384.00 |     1 |     46 | A11
 25121 | Hafa elektrisk hekksaks Z3     | 481.50 |     1 |    110 | A12
 25136 | Juwa Anleggspade               | 207.00 |     1 |      6 | A30
 25137 | Juwa Snøskuffe, standard       | 262.00 |     1 |     30 | A04
 25154 | Ljå                            | 317.00 |     1 |      4 | A17
 32191 | Formgummi 0.5 l                | 462.00 |     3 |     88 | B04
 43014 | Treramme A4                    | 428.00 |    17 |     24 | B25
 43015 | Treramme A5                    | 331.00 |    17 |      0 | B32
 49921 | Lezlo leire, økonomipakke      | 411.00 |     3 |    164 | B04
 55130 | Moro med marsipan              | 343.50 |    10 |    140 | C20
 64511 | Lilje sibir, 20 stk.           | 261.50 |    16 |    278 | E03
 64552 | Storblomstret begonia, 20 stk. | 317.00 |    16 |     42 | E03
--More-- 


#### 2.
hobbyhuset=# 
SELECT * 
FROM Ansatt 
WHERE Stilling = 'Lagermedarbeider' OR Stilling = 'Innkjøper';

 ansnr | fornavn | etternavn  |        adresse        | postnr | fødselsdato | kjønn |     stilling     |  Årslønn  
-------+---------+------------+-----------------------+--------+-------------+-------+------------------+-----------
     3 | Morgan  | Dalland    | Jansbergveien 19      | 3830   | 1974-01-10  | M     | Innkjøper        | 670500.00
    11 | Oliver  | Abrahamsen | Tarjei Vesaas' vei 3A | 3812   | 1989-01-20  | M     | Lagermedarbeider | 466900.00
(2 rows)

### 3.
hobbyhuset=# 
SELECT * 
FROM Kunde 
WHERE (PostNr='3199' OR PostNr='1711') 
AND Fornavn LIKE 'A%';

 knr  | fornavn |  etternavn   |    adresse    | postnr 
------+---------+--------------+---------------+--------
 5813 | Amina   | Alexandersen | Asylplassen 2 | 3199
(1 row)

### 4.
SELECT * FROM Vare WHERE NOT KatNr=1 AND Antall>600;
  vnr  |       betegnelse        |  pris  | katnr | antall | hylle 
-------+-------------------------+--------+-------+--------+-------
 33044 | Blandet blomsterfrø     |  16.50 |    15 |   1080 | E05
 33045 | Blomkarse               |  20.50 |    15 |   1206 | E05
 33046 | Brudeslør               |  17.00 |    15 |    640 | E05
 41098 | Keramisk leire          |  95.00 |     3 |    834 | B02
 42939 | Pepperkakeformer, 15stk | 109.00 |     4 |    640 | B09
 42941 | Julesett                |  82.00 |    17 |   1040 | B29
 45923 | Krukke med føtter, 12cm |  48.00 |    17 |    604 | B32
 72777 | Julehobbypakke for barn | 177.00 |    20 |    820 | A06
 80692 | Rørespatel              |  45.50 |     4 |    602 | B17
 82093 | Rund gulrot             |  28.00 |    18 |    658 | E25
(10 rows)

### 5.
SELECT * FROM Vare WHERE NOT KatNr=1 AND Antall>600;
  vnr  |       betegnelse        |  pris  | katnr | antall | hylle 
-------+-------------------------+--------+-------+--------+-------
 33044 | Blandet blomsterfrø     |  16.50 |    15 |   1080 | E05
 33045 | Blomkarse               |  20.50 |    15 |   1206 | E05
 33046 | Brudeslør               |  17.00 |    15 |    640 | E05
 41098 | Keramisk leire          |  95.00 |     3 |    834 | B02
 42939 | Pepperkakeformer, 15stk | 109.00 |     4 |    640 | B09
 42941 | Julesett                |  82.00 |    17 |   1040 | B29
 45923 | Krukke med føtter, 12cm |  48.00 |    17 |    604 | B32
 72777 | Julehobbypakke for barn | 177.00 |    20 |    820 | A06
 80692 | Rørespatel              |  45.50 |     4 |    602 | B17
 82093 | Rund gulrot             |  28.00 |    18 |    658 | E25
(10 rows)

### 5. 
hobbyhuset=# 
SELECT * 
FROM Ordre 
WHERE SendtDato IS NOT NULL AND BetaltDato IS NULL;

 ordrenr | ordredato | sendtdato | betaltdato | knr 
---------+-----------+-----------+------------+-----
(0 rows)

### 6.
hobbyhuset=# 
SELECT * 
FROM Ansatt 
WHERE Etternavn 
ILIKE'%sen%';

 ansnr | fornavn | etternavn  |        adresse        | postnr | fødselsdato | kjønn |     stilling      |  Årslønn  
-------+---------+------------+-----------------------+--------+-------------+-------+-------------------+-----------
    11 | Oliver  | Abrahamsen | Tarjei Vesaas' vei 3A | 3812   | 1989-01-20  | M     | Lagermedarbeider  | 466900.00
    16 | Andrine | Ebbesen    | Kristianias gate 9    | 3800   | 1988-12-27  | K     | Regnskapssekretær | 532300.00
(2 rows)


## Oppgave 3: Gruppering og Sortering
1.  `SELECT * FROM Vare ORDER BY Pris DESC;`
2.  `SELECT KatNr, COUNT(*) FROM Vare GROUP BY KatNr;`
3.  `SELECT Stilling, AVG(Årslønn) FROM Ansatt GROUP BY Stilling;`
4.  `SELECT KatNr, SUM(Antall) FROM Vare GROUP BY KatNr HAVING SUM(Antall) > 500;`

1.  **Forklaring:** ...

2.  **Forklaring:** ...

3.  **Forklaring:** ...

4.  **Forklaring:** ...

## Oppgave 4: Spørringer mot Flere Tabeller
1.  `SELECT V.Betegnelse, K.Navn FROM Vare V JOIN Kategori K ON V.KatNr = K.KatNr;`
2.  `SELECT O.OrdreNr, K.Fornavn, K.Etternavn FROM Ordre O LEFT JOIN Kunde K ON O.KNr = K.KNr;`
3.  `SELECT A1.Fornavn, A2.Fornavn FROM Ansatt A1, Ansatt A2 WHERE A1.PostNr = A2.PostNr AND A1.AnsNr < A2.AnsNr;`
4.  `SELECT V.Betegnelse FROM Vare V WHERE V.VNr NOT IN (SELECT VNr FROM Ordrelinje);`

1.  **Forklaring:** ...

2.  **Forklaring:** ...

3.  **Forklaring:** ...

4.  **Forklaring:** ...

## Oppgave 5: NULL-verdier og Aggregeringsfunksjoner

Forklar hva følgende SQL-spørringer gjør, og hvorfor resultatene blir som de blir. Vær spesielt oppmerksom på hvordan `NULL` påvirker resultatet.

1.  **Spørring:**
    ```sql
    SELECT COUNT(*), COUNT(Bonus) FROM Ansatt;
    ```
    **Forklaring:**
    *   *... Skriv din forklaring her ...*

2.  **Spørring:**
    ```sql
    SELECT AVG(Bonus) FROM Ansatt;
    ```
    **Forklaring:**
    *   *... Skriv din forklaring her ...*

3.  **Spørring:**
    ```sql
    SELECT Fornavn, Etternavn, COALESCE(Bonus, 0) AS JustertBonus FROM Ansatt;
    ```
    **Forklaring:**
    *   *... Skriv din forklaring her ...*

4.  **Spørring:**
    ```sql
    SELECT Stilling, SUM(Årslønn + Bonus) FROM Ansatt GROUP BY Stilling;
    ```
    **Forklaring:**
    *   *... Skriv din forklaring her ...*

## Oppgave 6: Tre-verdi Logikk (TRUE, FALSE, UNKNOWN)

SQLs logikk er ikke bare `TRUE` eller `FALSE`. Når `NULL` er involvert, får vi en tredje tilstand: `UNKNOWN`. Denne oppgaven utforsker hvordan dette påvirker `WHERE`-klausuler.

### Del 1: Forklar SQL-spørringene

Forklar resultatet av følgende SQL-spørringer. Hvorfor returnerer de det de gjør?

1.  **Spørring:**
    ```sql
    SELECT COUNT(*) FROM Ordre WHERE ErBetalt = TRUE;
    ```
    **Forklaring:**
    *   *... Skriv din forklaring her ...*

2.  **Spørring:**
    ```sql
    SELECT COUNT(*) FROM Ordre WHERE ErBetalt = FALSE;
    ```
    **Forklaring:**
    *   *... Skriv din forklaring her ...*

3.  **Spørring:**
    ```sql
    SELECT COUNT(*) FROM Ordre WHERE ErBetalt = TRUE OR ErBetalt = FALSE;
    ```
    **Forklaring:**
    *   *... Skriv din forklaring her ...*

4.  **Spørring:**
    ```sql
    SELECT COUNT(*) FROM Ordre WHERE ErBetalt IS UNKNOWN;
    ```
    **Forklaring:**
    *   *... Skriv din forklaring her ...*
