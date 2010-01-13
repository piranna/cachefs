Simulator de algoritmi de caching

Sunt simula�i doi algoritmi de caching pentru a fi compara�i.
Avem un cache cu dou� niveluei (RAM �i SSD).
Fi�ierele sunt doar citite, nu �i modificate (exemplu: server web).

Primul algoritm: c�nd se solicit� un fi�ier care nu e �n cache, se �ncearc� aducerea lui
�n RAM (dac� are loc) �i apoi �n SSD (dac� are loc). Dac� nu are loc �n niciunul din aceste
medii de stocare, se verific� dac� are dimensiunea mai mic� dec�t memoria RAM �i se �terg de
aici at�tea fi�iere �nc�t noul fi�ier s� aib� loc �i acesta de copiaz� �n RAM. Dac� fi�ierul
nu ar putea �nc�pea �n RAM se verific� dac� are dimensiunea mai mic� dec�t SSD-ul �i se �terg
de aici at�tea fi�iere �nc�t noul fi�ier s� aib� loc �i acesta de copiaz� �n SSD. Dac� 
fi�ierul nu ar �nc�pea nici �n SSD, se las� pe HDD. �tergerea fi�ierelor din RAM �i SSD se
face �ncep�nd cu cele mai vechi fi�iere introduse acolo.
Al doilea algoritm este similar cu primul, doar c� fi�erele care au maxim o dimensiunea dat�
(de exmplu fi�iere .css. .html) se copiaz� doar �n RAM, iar celelalte se copiaz� doar pe SSD,
pentru o �mbun�t��ire a performa�ei.

Date de intrare:
Files.txt, care con�ine fi�ierele care vor fi acesate, sub forma unei perechi 
"index_fi�ier m�rime_fi�ier" pe c�te o linie.
Profile.txt care con�ine pe prima linie dimensiunea memoriei RAM, pe a doua linie dimensiunea
memoriei SSD (HDD-ul are o dimensiune irelevant�, din moment ce con�ine toate fi�ierele care
vor fi accesate), pe a treia linie dimensiunea maxim� a fi�ierelor care vor fi copieate �n RAM
de algoritmul 2 �i pe a patra linie ordinea �n care vor fi accesate fi�ierele.
Times.txt con�ine pe prima linie timpul de acces al unui fi�ier care se afl� �n RAM, SSD, 
respectiv HDD, pe a doua linie rata de citire din RAM, SSD, HDD (timpul se citire se ob�ine
�mp�r�ind dimensiunea la aceast� rat�) �i pe a treia linie timpul de copiere de pe HDD �n RAM,
respectiv SSD.

Datele de ie�ire: c�te un fi�ier pentru fiecare algoritm care con�ine linii de trei numere ce
reprezint� indexul fi�erului, dimesiunea sa �i timpul �n care a fost citit acel fi�ier. Pe 
ultima linie se afl� timpul total �n care au fost citite fi�ierele.

Timp de accesare fi�ier din RAM sau SSD = timp acces + dimensiune / rat� citire.
Timp de accesare fi�ier din HDD = timp acces + dimensiune / rat� citire + timp copiere * dimensiune.