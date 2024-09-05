# Technologicky dluh
## Dříve se o programátorech a obecně lidech z IT říkalo, že jinak jednoduché věci zbytečně komplikují, a že mluví divným jazykem.

Když jsem se v březnu 2020 rozhodl nastudovat aktuální verze programovacího jazyka C++ a připravit nové kurzy, nedošla mi plná hloubka toho, co dělám.

Podívejte se na snímek z dokumentace (cppreference), a zkuste aspoň rámcově pochopit, o čem se tam vůbec mluví. Pokud se vám dělá nevolno, a stále nevíte vůbec nic, právě jste pochopili podstatu celého problému.

❦

Sledujte se mnou. Ani nemusíte znát nic z programování. Ale zkuste seznam dočíst do konce.

‣ Vím, co je „class“ a „downcast“ z obecného povědomí o objektově orientovaném programování.
‣ Vím, co je „constness“ a „volatility“, „lvalue“ a „complete class“, z obecného přehledu o fungování C a C++.
‣ Znám specifický význam „reference“ a „pointer“ pro C++, jen nechápu ty okecávky.
‣ Dodatečně přiřazuju význam „non-virtual base“ jako vymezení se vůči „virtual inheritance“, jen tápu, proč mě to má v tomto kontextu zajímat.
‣ Rozumím definici „prvalue“, jen mi takové vymezení, navíc specifické pro C++ nedává žádný jiný než historický smysl.
‣ Dohledávám význam „inaccessible base“ jako vymezení vůči „private inheritance“.
‣ Dohledávám „ambiguous base“ a zjišťuju, že je to zase detail ohledně „virtual inheritance“.

Tak to bychom měli s ne úplně velkou jistotou přečtenou polovinu prvního bodu z deseti, které mají vysvětlit stupidní konverzi hodnoty na jiný datový typ.

A to se bavíme o industriálním jazyce, který se bude používat další desítky let. Takže v zásadě stačí tvářit se, že je všechno v pohodě, a nechávat si platit jenom za to, že jste ochotní se v tomhle bordelu vyznávat.

Navíc ten jazyk oproti jiným dost podporuje vznik složitých a špatně předvídatelných chyb, takže už samotný fakt, že v něm někdo píše komerční kód, vytváří další pracovní a obchodní příležitosti. Inu, na důchod jsem se právě zajistil.

Jestliže můžeme C++ ukazovat jako zářný příklad technologického dluhu, můžeme pak vývoj software v C++ označit jako dluhové podnikání? 

## Někdy je lepší udělat restart.

Programátoři potřebují ukládat seznamy věcí, které nejsou stejné. Hned ukážu na oblíbeném příkladu.

Jdeme tvořit obraz. Budeme na plátno skládat základní tvary.

 ‣ Kolečko potřebuje ke svému upřesnění jenom jedno číslo, poloměr.
 ‣ Obdélník šířku a výšku, případně ještě úhel, jak je natočený.
 ‣ Obecný mnohoúhelník pak libovolně velký seznam vrcholů.

Protože chceme vidět, jak obraz vypadá, náš program musí umět nakreslit celé plátno na obrazovku. Tedy vymazat obrazovku a obtisknout jeden tvar po druhém na správné místo.

Aby to fungovalo, stačí pár věcí.

 ‣ Všechny tvary mají společnou vlastnost, lze je nakreslit na obrazovku.
 ‣ Zmíněný seznam umí vyhradit místo, kam lze uložit kterýkoli z nich.
 ‣ Umíme pro každý prvek seznamu zavolat správnou kreslicí rutinu.

Můžeme tomu říkat polymorfismus. V našem případě to jednoduše znamená, že můžeme projít seznam tvarů, a každý nechat nakreslit pomocí kódu, který přísluší danému typu. Tedy spustit jiný kus kódu pro nakreslení kruhu než pro nakreslení obdélníku.

Funkci polymorfismu garantuje programovací jazyk, a v detailu se v tomto ohledu různé jazyky velmi liší. Výše uvedený příklad se řeší pomocí podtypů a Liskovovoé substitučního principu. Napíšu kód, který na první pohled pracuje s abstraktým typem „Tvar“, ale ve skutečnosti dokáže pracovat s konkrétními typy „Kruh“ a „Obdélník“.

Jsou dva hlavní směry, jak to udělat. Statický polymorfismus znamená, že se vše vyřeší v době sestavení programu a obecný kód se zkompiluje do několika konkrétních kusů kódu podle potřeby. Dynamický polymorfismus vytváří datové struktury takové, aby program dokázal najít správný kus kódu až za běhu.

Statický polymorfismus bývá efektivnější. Dynamický polymorfismus je univerzálnější. Proto programovací jazyky zaměřené na výkon, jako je C++ nebo Rust, poskytují obě možnosti.

Je tu ovšem jeden zásadní rozdíl. Rust jako relativně nový programovací jazyk nabízí možnost popsat očekávané vlastnosti konkrétních typů pomocí rozhraní (trait). Rust tak kontroluje konkrétní kód, zda skutečně splňuje rozhraní, a obecný kód, zda používá pouze uvedené rozhraní a nic jiného.

Takové kontroly C++ neumí. V rámci standardu C++20 byla přidána poněkud bizarní možnost přidat kontrolu konkrétního kódu, ovšem bez kontroly obecného kódu. To vede na nesrozumitelné až nesmyslné chybové hlášky a ztracený čas programátora.

Navíc rozhraní pro statický polymorfismus popisuje zcela odlišně od rozhraní dynamického. To mi připadá jako špatný nápad. Výrazně to zvyšuje komplexitu a komplikovanost jazyka, přitom to nepřináší ani takový přínos jako řešení v Rustu. To vše kvůli dědictví z osmdesátých let a zachovávání zpětné kompatibility.

Když se bavím se skalními C++ programátory, často tyhle věci obhajují, a ptají se mě, jak bych to „v C++“ řešil lépe. Ale proč bych měl já opravovat něco, co je fundamentálně rozbité?

![Technologicky dluh](images/Technologicky%20dluh.png)

