# UNIX  Unix wasn't all that badly designed back in the 1970's. We like…

UNIX  Unix wasn't all that badly designed back in the 1970's. We like it a lot especially because of the openness of its modern clones. And it has that ubiquitous “get things done” feeling.

As long as you are learning “the unix way”, things look relatively good. Every problem has a new solution that creates new interesting problems. That have solutions… You have literally half a century of well known workarounds to add on top of other workarounds.

Even simple things as building software (from your code and dependencies) are chaotic and unpredictable. External dependencies are often picked up from the current state of your system. As I suggested, the first time you build your LFS to boost your Linux skills feels great. But when you realize distribution build systems are just workarounds over LFS…

❦

I used to live in a dream that the “linux distro way” of maintaining dynamic libraries and other dependencies is the best and only way. Only later I realized that this chaos is what holds development and all great features like fully reproducible builds back.

Back then I talked to developers of Freeswitch. It was a lovely piece of software in many ways nicer than Asterisk. I told the developers that I need to build FreeSWITCH with the versions of dynamic libraries included in my distro and they said no. I was sad, they were right.

Back then it was one of the reasons FreeSWITCH was way less popular than Asterisk was. I didn't like the decision of FreeSWITCH developers but now I guess I should have disliked the way Linux distributions were designed. Docker changed that (or rather added another workaround layer) and became instantly popular.

❦

In the past couple of years I design a set of programming courses focused on C, C++ and later Rust development with the Unix platform in mind. I did a pretty good job in showing people how operating system APIs work and what they provide.

Now I'm thinking of redesigning the whole thing to shift focus from “how things work” to what's the best way to “achieve things”. Don't get me wrong. Learning how the old computer masters designed things in the old days is great. It just no longer seems good enough for the current world of software development.

Je mi líto, že vám to musím říct, ale UNIX nemá ani dobrý design, ani dobrou architekturu. Čím dříve se s tím smíříte, tím lépe se vám bude s padesátiletým softwarovým odkazem pracovat.

❦

Říká se že jsou unixové systémy pevně spjaté s jazykem C. Jenže když se podíváte na systémové API, uvidíte spíše assembler. Posuďte sami.

1) Potřebuju zapisovat do souboru, vypisovat na terminál, nebo poslat data po síti.

Takže si data sesbírám do nějakého bufferu třeba na zásobníku. Jedním argumentem předávám paměťovou adresu druhým počet bajtů v bufferu. Odpovědí mi přijde počet skutečně zapsaných bajtů.

Pokud by systém nezapsal celý buffer, musím operaci opakovat. Ani tentokrát nemůžu jednoduše „poslat buffer“. Musím poslat adresu posunutou o již zpracované bajty, a počet bajtů o stejnou hodnotu zmenšený.

Jestli je někde prostor udělat fatální bezpečnostní chybu, pak tohle je přesně to místo.

2) Potřebuju data z jichž zmíněných zdrojů přečíst.

To si vytvořím úplně stejný buffer, jenom do něj nedávám žádná data. Celé volání vypadá úplně stejně. Řeknu kde ten buffer je a jak je velký. Při každém dalším čtení pošlu adresu zvýšenou o již přečtená data a velikost o ně sníženou.

3) Polymorfismus aneb mnohotvarost

Když potřebujem poslat nebo přečíst síťovou adresu, máme trochu problém. Struktura IPv4 adresy vypadá jinak než struktura IPv6, dále máme lokální unixové sockety a spoustu dalších.

Aby systém věděl se kterou adresou pracuje, máme pevně daný číselník typu adres a všechny ty struktury mají na začátku prostor pro toto číslo. Zároveň se „pro jistotu“ vždy posílá ještě velikost adresy v bajtech, abychom si mohli vzájemně kontrolovat, jestli pracujeme se správně velkou alokací.

4) Složité zápisy jednoduchých věcí

Assemblerovská architektura se projevuje i když chci udělat tak jednoduchou věc, jako požádat operační systém, aby některý z mých prostředků předal jinému procesu.

Schválně se podívejte do screenshotu, a řekněte mi, jak dlouho vám trvá, než si uvědomíte, že celý ten kód ve výsledku pouze pošle jeden file descriptor druhé straně k vyzvednutí. Kód na vyzvednutí mimochodem vypadá prakticky totožně.


A takto bych mohl pokračovat libovolně dlouho. Ono to na datové úrovni není úplně špatně. Na ekonomické úrovni vám to váže vzácné lidské zdroje, které potřebujete na budování produktů a generování příjmů, aby ty lidi bylo z čeho platit.

(Challenge: Pivo za každou nalezenou chybu.)

P. S. Nemyslete si, že by vás Windows nebo Mac měly jakkoli spasit. Microsoft dokázal mnohé věci za svoji existenci ještě více pokazit a zkomplikovat.
