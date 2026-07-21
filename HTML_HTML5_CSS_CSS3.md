# Jazyk HTML

Jazyk HTML (zkratka pro Hypertext Markup Language) je standardní jazyk
pro zápis www stránek. Hypertext je text, který např. umožňuje odkázat
přímo na jiný text nebo jinou část dokumentu, třeba klikem myši.
Jednoduše řečeno, umožňuje tvorbu odkazů majících funkci referencí.

Soubory napsané v jazyce HTML mají příponu html, případně se můžete
setkat se zastaralou příponou htm.

Jedná se o prostý textový soubor, tudíž média nejsou součástí souboru,
ale jsou umístěna samostatně v libovolném adresáři na úložišti či na
internetu. Názvy souborů by měly být malými písmeny a bez diakritických
znamének, aby chodily i na Linuxu.

Význam jednotlivých částí je určen pomocí značek, tzv. tagů. Tagy tedy
popisují strukturu webové stránky a definují prohlížeči způsob, jak má
obsah stránky zobrazit. Každý tag začíná znakem \<, za nímž následuje
název značky, případné parametry a tag je uzavřen znakem \>. Rovněž
platí, že cokoliv je ve špičatých závorkách, je automaticky bráno jako
tag a nebude v prohlížeči vidět. Tagy rozlišujeme párové a nepárové.
Párové tagy obvykle definují vlastnosti textu, který obklopují.
Počáteční a koncový párový tag se zapisuje stejným názvem, leč
v koncovém je před názvem lomítko. Tagy mohou mít své atributy, které
specifikují určité vlastnosti nebo funkcionality. V případě párových
tagů se atributy zapisují v otevírací části tagu.

HTML element je označení pro vše od začátku přes obsah až po konec tagu.

``` html
<img src="./img/img1.jpg" alt="nepárový tag">
```

*Zde ukázka nepárového tagu pro zobrazení obrázku z lokálního úložiště.
Atributy tagu jsou src a alt.*

``` html
<h1>párový tag</h1>
```

*Tento párový tag řekne prohlížeči, aby text vypadal jako hlavní
nadpis.*

Pro tvorbu www stránek stačí obyčejný textový editor, leč pro snazší
práci existují speciální editory s šikovným našeptáváním (Visual Studio
Code), nebo WYSIWYG (zkratka pro „what you see is what you get")
editory.

Zdrojový text zobrazené stránky je možné v prohlížeči zobrazit pomocí
kliku pravým tlačítkem myši a z nabídky vybrat *Zobrazit zdrojový kód
stránky.*

![](media/image1.png)

*Ukázka jednoduchého kódu www stránky, která zobrazí nadpis „Ahoj
světe"*

``` html
<!-- text komentáře -->
```

*Tento nepárový tag umožňuje komentáře v kódu HTML.*

`<!DOCTYPE html>` Tento nepárový tag je informací pro prohlížeč, jaký
typ dokumentu má očekávat, píše se tedy jako první a je nutný pro
správné zobrazení www stránky. V tomto případě informuje o formátu
HTML5.

`<html lang="cs"></html>` je párovým tagem HTML dokumentu. Kořenový
element html obsahuje veškerý obsah stránky (vyjma *\<!DOCTYPE html\>*).
Vždy by měl být přítomen atribut lang, který oznamuje, jakým jazykem je
psána webová stránka. To usnadňuje práci vyhledávačům a prohlížečům.

# Head -- hlavička

``` html
<head></head> 
```

Prvním tagem v rámci html tagu je head, ve kterém se nacházejí metadata,
neboli data o html dokumentu. Patří mezi ně titulek stránky, používaná
sada znaků, CSS styly, skripty či další informace (meta). Hlavička se v
HTML dokumentu vyskytuje pouze jednou.

## HTML elementy v hlavičce

#### Title -- název stránky

``` html
<title></title> 
```

Element title je vyžadován v každém HTML dokumentu. Musí být čistě
textový a zobrazuje se jako název stránky v oušku karty v prohlížeči.

#### Meta

``` html
<meta> 
```

-   ``` html
    <meta charset="UTF-8" />
    ```

Určuje kódování znaků pro HTML dokument

-   ``` html
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    ```

Metadata pro prohlížeč Internet Exoplorer, aby použil poslední verzi
rendrovacího enginu.

-   ``` html
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    ```

Informace prohlížeči o dimenzování a měřítku. Zde bude šířka stránky
podle šířky obrazovky a nastaví počáteční úroveň zvětšení při prvotním
načtení prohlížečem.

-   ``` html
    <meta name="keywords" content="HTML, CSS, výuka, školení">
    ```

Klíčová slova pro vyhledávače.

-   ``` html
    <meta name="description" content="Tvorba www stránek">
    ```

Popis obsahu stránky.

-   ``` html
    <meta name="author" content="Jan Novák">
    ```

Jméno autora stránky.

#### Style

``` html
<style></style> 
```

Uvnitř tohoto elementu můžeme definovat kaskádové styly CSS

#### Script

``` html
<script></script> 
```

Element script může jednak obsahovat skriptovací kód, nebo pomocí
atributu src odkazuje na externí soubor skriptovacího kódu, nejčastěji v
jazyce JavaScript. Tento tag se může vyskytovat i v rámci těla stránky.

-   ``` html
    <script src="./script/script.js"></script>
    ```

Atribut src udává cestu k externímu souboru skriptu.

Target upravuje navigaci z odkazů nebo formulářů, které nemají
definovaný svůj atribut target. V případě `target="_blank"` se otevře
obsah v nové kartě.

#### Link

``` html
<link> 
```

Specifikuje vztah mezi dokumentem a externím zdrojem, nejčastěji se
používá pro připojení externího CSS souboru.

-   ``` html
    <link rel="stylesheet" href="./style.css">
    ```

Atributem rel pojmenovává vztah externího zdroje k dokumentu, v tomto
případě jde o soubor kaskádových stylů. Atribut href klasicky udává
cestu k externímu souboru.

# Body -- tělo dokumentu

``` html
<body></body> 
```

Body je stejně jako head unikátním tagem. Element obsahuje veškerý
viditelný obsah HTML dokumentu.

## Typy HTML elementů

Rozlišujeme několik základních typů HTML elementů. V rámci této kapitoly
si představíme první dva typy.

### Block -- blokový element

Jedná se o HTML element, který vždy začíná na nové řádce, zabírá
maximální možnou šířku a ve výchozím nastavení prohlížeč přidá mezeru
nad a pod.

***In-line -- řádkový element***

Oproti blocku in-line element na nové řádce nezačíná a vezme si jen
tolik místa, kolik jeho obsah zabírá. Tyto tagy mají v drtivé většině
hlavní funci ovlivnit design.

## Modifikace HTML elementů

HTML elementy je možno samozřejmě modifikovat. Pouze s výchozím
nastavením by nebylo možno vytvořit nic smysluplného. Toho lze dosáhnout
jednak atributy a v drtivé většině případů pomocí kaskádových stylů.
Kaskádovým stylům se budeme zevrubně věnovat v samostatné kapitole
později, ale právě kvůli nastavování vlastností jednotlivým elementům je
nutné se o nich zmínit i v kapitolách následujících.

## Text v HTML

Zajímavostí jazyka HTML je práce s textem. Ten ignoruje násobné mezery,
zalomení a použití tabulátorů ve zdrojovém textu. Text se zobrazí
v celistvém toku.

### Blokové elementy

#### Nadpisy (Headings)

`<h1></h1> `až `<h6></h6>`

Pro nadpisy se používá párový tag h1 až h6, přičemž h1 je největší a
hlavní nadpis a h6 je nadpis nejmenší. Platí pravidla, že h1 se na
stránce vyskytuje pouze jednou a pro použití nadpisů platí hierarchie.
Např. po h2 tedy následuje h3 a nelze přeskočit např. na h5. Jedná se o
blokové elementy. Pomocí atributu `style` můžete nastavit zarovnání
textu pomocí kaskádových stylů a vlastnosti text-align, v příkladu níže
zarovnáno na střed. Takto to lze u všech blokových elementů s textem.

``` html
<h1 style="text-align: center;">Nadpis</h1>
```

#### Odstavec (Paragraph)

``` html
<p></p>
```

Párový tag p reprezentuje blokový HTML element pro odstavec. Odstavce
mají defaultně nastaveny mezery nad a pod o výšce jednoho řádku. Mezery
dvou sousedních odstavců se vzájemně překrývají.

#### Zalomení (Break)

``` html
<br>
```

Nepárový tag br způsobí pouze zalomení řádku v textu. Neměl by se
používat mimo text.

#### **Vodorovná čára (Horizontal rule**)

``` html
<hr>
```

Ve výchozím nastavení se pomocí tohoto tagu zobrazí vodorovná čára po
celé šíři stránky nebo elementu, ve kterém se nachází. Používá se hlavně
pro vizuální oddělení částí stránky.

#### Předformátovaný text (Preformatted text)

``` html
<pre></pre>
```

Pokud bychom rádi zachovali formátování původního textu (vícero mezer za
sebou, odsazení, odřádkování...), např. pro víceřádkový fragment kódu,
lze použít párový tag pre. Defaultně je nastaven font písma, jehož každý
znak zabírá stejnou šířku, čili se zarovnává přesně ve svislém směru.

#### Oddíl (Division)

``` html
<div></div>
```

Div je tzv. neutrální tag, jenž od sebe odděluje hierarchicky text,
elementy nebo jejich skupiny, aby bylo snazší využít kaskádových stylů.
Div nemá ve výchozím stavu nastavené mezery, pouze začíná na novém
řádku.

Zároveň se používá i při vytváření různých obrazců ruku v ruce s užitím
CSS. Čili jeho význam je daleko nad rámec práce s textem v HTML a
setkáte se s ním velmi často, zejména v problematice rozložení stránky.

#### Adresa (Address)

``` html
<address></address>
```

Address je tag, který má stejné vlastnosti jako paragraph, leč s tím
rozdílem, že písmo je nastaveno na kurzívu. Jeho funkce je očividná
z názvu, tedy pro zápis adres.

#### Bloková citace (Blockquote)

``` html
<blockquote></blockquote>
```

Blockquote slouží pro několikařádkové citace. Funkčně je to podobný tag
paragraphu, ale navíc s odsazením od obou bočních okrajů 40px.

Dále existují tagy, které jen upřesňují strukturu kódu www stránek do
logických celků. Jejich užívání není striktní, ale setkáte se s nimi
v praxi určitě. Víc o těchto strukturních tazích v první části skript
věnovaných webdesignu a CSS3 animaci.

### Řádkové elementy

#### **Tučné písmo (Bold**)

``` html
<b></b>
```

Text, který je tagem b ohraničen, se ztuční.

#### Kurzíva (Italics)

``` html
<i></i>
```

Pokud chcete, aby text byl kurzívou, umístěte jej do párového tagu i.

#### Horní index (Superscript)

``` html
<sup></sup>
```

Chcete-li psát např. matematrické vzorce, v případě mocnin využijete
párový tag sup. Ten zmenší znak a posune jej směrem nahoru.

#### Dolní index (Subscript)

``` html
<sub></sub>
```

V případě chemických vzorců využijete tag sub, jenž zmenší znak a umístí
jej níže než znaky v klasickém textu.

#### Zdůraznění textu (Emphasis)

``` html
<em></em>
```

Tag em má za úkol zdůraznit text, prohlížeč jej vyrendruje jako kurzívu.

#### Silné zvýraznění textu (Strong)

``` html
<strong></strong>
```

Tímto tagem je obalen text, na jehož důležitost chceme upozornit.
Zobrazí se jako tučné písmo.

#### Podbarvený text (Mark)

``` html
<mark></mark>
```

Tag mark podbarví text žlutě a barvu písma nastaví na černou.

#### Vysvětlení zkratky (Abbreviation)

``` html
<abbr></abbr>
```

V tagu obalená zkratka je vysvětlena v atributu title. Vysvětlivka se
objeví v bublině po najetí na zkratku kurzorem.

-   ``` html
    <abbr title="European Union">EU</abbr>
    ```

#### Řádková citace (Quote)

``` html
<q></q>
```

Krátká citace, jež nezalamuje text. Pro upřesnění zdroje citace můžeme
použít atribut cite.

-   ``` html
    <q cite="http://www.ucitelka.cz">Kdo se neučí, ten kurz nedokončí.</q>
    ```

#### Kód (Code)

``` html
<code></code>
```

Tímto tagem zvýrazníte text jako krátkou část kódu. Font má všechny
znaky stejně široké (monospace).

#### Span

``` html
<span></span>
```

Span je neutrální in-line element. Tag vymezuje část textu, na nějž
chceme aplikovat nějaké speciální vlastnosti kaskádovými styly nebo
JavaScriptem.

Tyto následující HTML elementy nejsou ani řádkové ani blokové. Můžete se
s nimi setkat v blozích nebo zpravodajských článcích.

#### Odstraněný text (Deleted text)

``` html
<del></del>
```

Přeškrtnutí textu, aby bylo jasné, že jde o text smazaný.

#### Přidaný text (Inserted text)

``` html
<ins></ins>
```

Nově přidaný text -- zvýraznění textu podtržením.

## Seznamy

Seznamy jsou blokové HTML elementy, jež užíváme hlavně jako výčtové
prvky stránky. V případě odrážkových seznamů se s nimi setkáte i
v souvislosti s navigačními lištami.

### Odrážkové seznamy (Unordered lists)

``` html
<ul></ul>
```

Neuspořádané seznamy definuje párový tag ul a jednotlivé položky seznamu
jsou vymezeny tagem li.

``` html
<ul>
  <li>chleba</li>
  <li>citróny</li>
  <li>zubní pasta</li>
</ul>
```

Vzhled odrážek je nastaven defaultně. Toto lze změnit pomocí kaskádových
stylů.

``` html
<ul style="list-style-type: square;">
  <li>chleba</li>
  <li>citróny</li>
  <li>zubní pasta</li>
</ul>
```

*Pomocí CSS vlastnosti list-style-type můžete nastavit odrážky na
square, circle, disc (defaultní).*

### Číslované seznamy (Ordered lists)

``` html
<ol></ol>
```

Číslované seznamy využívají pro položky stejný tag li jako seznamy
neuspořádané. Jsou definovány párovám tagem ol.

``` html
<ol>
  <li>chleba</li>
  <li>citróny</li>
  <li>zubní pasta</li>
</ol>
```

Defaultně je seznam číslován arabskými číslicemi, což je možno změnit
v CSS.

``` html
<ol style="list-style-type: upper-roman;">
  <li>chleba</li>
  <li>citróny</li>
  <li>zubní pasta</li>
</ol>
```

*CSS vlastnost list-style-type podobně jako u neuspořádaných seznamů
nastavuje vzhled číslování (upper-roman, lower-alpha, atp.)*

Pomocí atributů lze nastavit od kterého čísla (písmena) bude seznam
začínat a případně i sestupný směr počítání.

`reversed	`Atribut tagu ol obrací směr počítání.

`start	`Atribut tagu ol nastavuje počátek číslování seznamu.

`type	`Druhá možnost, jak změnit výchozí vzhled číslování senamu --
atributem type. Je možno nastavit hodnoty 1, a, A, I, i. Je to tedy
mnohem méně možností než přes kaskádové styly.

``` html
<ol start="100" reversed>
  <li>chleba</li>
  <li>citróny</li>
  <li>zubní pasta</li>
</ol>
```

*Na příkladu vidíte, že seznam bude začínat na 100 a bude pokračovat 99,
98, 97...*

``` html
<ol type="i">
  <li>chleba</li>
  <li>citróny</li>
  <li>zubní pasta</li>
</ol>
```

*Zde ukázka, jak způsobem přes atribut type změnit vzhled číslování
seznamu.*

Seznamy můžete do sebe libovolně zanořovat a dokonce kombinovat i
číselné a odrážkové.

### Seznamy definic (Description lists)

``` html
<dl></dl>
```

Tag dl definuje seznam definic, kde jsou jednotlivé položky otagovány dt
a na střídačku proloženy vysvětlujícím tagem dd.

``` html
<dl>
  <dt>tygr</dt>
  <dd>šelma kočkovitá</dd>
  <dt>hyena</dt>
  <dd>šelma psovitá</dd>
</dl>
```

## Tabulky

``` html
<table></table>
```

Tabulky měly v dávné minulosti důležitou roli z hlediska layoutu
webových stránek. Jelikož responzivní či adaptivní design byly termíny
zatím neznámé a rozlišení monitorů nebyly tak rozmanité, jako tomu je
dnes, mohl být obsah stránky napevno „nastrkán" do tabulky. Ty doby jsou
naštěstí pryč a dnes jsou tabulky používány už jen jako tabulky. Párový
tag table vymezuje blokový element tabulky.

`<tr></tr>	`Pomocí tagu table row vytvoříme v tabulce řádek. Kolik tagů,
tolik řádků.

`<td></td>	`Table data cell (buňka tabulky) v rámci řádku vymezuje buňku.

`<th></th>	`Table header cell (hlavičková buňka) plní stejnou úlohu jako
td, ale používá se v hlavičce tabulky. Má tučnější písmo a text je
vycentrován.

`<thead></thead>	`Tag sdružuje řádky hlavičky tabulky.

`<tbody></tbody>	`Tag sdružuje řádky těla tabulky.

`<tfoot></tfoot>	`Tag sdružuje řádky patičky tabulky.

`<caption></caption>	`Tabulka může mít titulek.

Kdysi se pro modifikace tabulek využívalo mnoho atributů. Dnes tomu je
jinak, atribitů se využívá zlomek a používáme výhradně stylování pomocí
CSS.

`colspan	`Atribut tagu td nebo th a celé číslo udává, kolik buněk v rámci
řádku se sloučí do jedné. Směr sloučení zleva doprava.

`rowspan	`Rovněž atribut td a th. Celé číslo udává počet buněk, které se
sloučí v rámci slouce. Směr sloučení shora dolů.

Defaultně se tabulky zobrazují bez rámečků, je třeba si je nadefinovat
v kaskádových stylech jak pro celou table, tak jednotlivé buňky. CSS
styly se probírají v samostatné kapitole, leč v rámci tabulek se bez
nich zcela neobejdeme. Jelikož jich je celkem hodně, nebudeme je psát
jako atribut tabulkových tagů, ale jako samostatný tag style v rámci
hlavičky (vizte kapitola Head - hlavička).

`border	`CSS vlastnost definující rámeček pomocí až 3 znaků: tloušťka,
styl čáry (povinné) a barva.

`border-collapse	`CSS vlastnost, nabývajících dvou hodnot: `separate`
(defaultní -- každý element má rámeček svůj) a `collapse` (celá tabulka
má jednoduchý rámeček).

`width	`CSS vlastnost pro dimenzování šířky.

`height	`CSS vlastnost pro dimenzování výšky.

`text-align	`CSS vlastnost pro nastavení pozice textu.

`background	`CSS vlastnost pro nastavení pozadí.

Pomocí border (tloušťka, styl čáry, barva) nastavíme vlastní rámeček a
border-collapse: collapse zajistí, aby rámeček nebyl dvojitý. Určitě si
vyzkoušejte styl různě obměnit.

``` html
<style>
  table, td, th {
    border: 1px solid black;
    border-collapse: collapse;
  }
</style>
```

Zde máme příklad jednoduché tabulky v kódu i výsledek. Nastylováno máme
CSS kódem z předchozího příkladu. Jak si můžete všimnout, šířka sloupce
se odvíjí od šířky buňky s nejdelším textem.

``` html
<table>
  <caption>Elektronika</caption>  
  <thead>
    <tr>
      <th>Položka</th>
      <th>Cena</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>televize</td>
      <td>15000</td>
    </tr>
    <tr>
      <td>vysavač</td>
      <td>6000</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>suma</td>
      <td>21000</td>
    </tr>
  </tfoot>
</table>
```

Pokud si do style přidáme další CSS vlastnosti pro buňku, můžeme
nastavit šířku, výšku, vycentrování textu a barvu pozadí.

``` html
<style>
  table, td, th {
    border: 1px solid black;
    border-collapse: collapse;
  }
  td {
    width: 100px;
    height: 30px;
    text-align: center;
    background: yellow;
  }
</style>
```

Na jednoduchých příkladech níže je ukázáno, jak se pracuje s atributy
`colspan` a `rowspan`.

``` html
<table>
  <tr>
    <td colspan="2">přes dvě buňky</td>
  </tr>
  <tr>
    <td>buňka</td>
    <td>buňka</td>
  </tr>
</table>
<table>
  <tr>
    <td rowspan="2">přes dvě buňky</td>
    <td>buňka</td>
  </tr>
  <tr>
    <td>buňka</td>
  </tr>
</table>
```

## Odkazy

``` html
<a></a>
```

Tagem a (anchor) se může obalit text, obrázek, téměř cokoliv. Výjimku
tvoří jiný odkaz a složité elementy, jako např. tabulka nebo formulář,
ty jako odkaz použít nemůžeme. Na obsah odkazu se dá pak kliknout a tím
přejít na cíl odkazu. Odkazovat se můžeme na jiné stránky, na jiné místo
na stejné stránce, ale také poslat mail nebo i zavolat na telefonní
číslo, což zpravidla vyžaduje externí program. Element má několik
atributů, leč důležité jsou pro nás pouze dva z nich.

`href	`Atribut nám udává cestu k cíli odkazu.

`target	`Upřesňuje, jak se má odkaz otevřít. Výchozí hodnota je nastavena
na \_self, čili se otevře odkaz ve stejném okně, z jakého jej spouštíme.
Je možno mj. nastavit na \_blank, to znamená otevřít v novém okně.

Pokud je odkazem text, ve výchozím nastavení je vždy podtržený. Odkaz,
na nějž jsme ještě nekliknuli, je modrý. Navštívený odkaz je fialový a
červeně odkaz aktivní. Toto se dá změnit v kaskádových stylech pomocí
vlastnosti text-decoration a color. Samozřejmě, pokud máte barvu písma
jinou než black, tak si nastavíte tu svoji.

``` html
<style>
  a {
    text-decoration: none;
    color: black;
  }
</style>
```

### Odkaz relativní

``` html
<a href="./odkaz.html" ><img src="../pics/picture.jpg"></a>
```

Relativní odkaz udává cestu k cíli vzhledem k dokumentu, ve kterém se
odkaz nachází. V tomto případě klikem na obrázek se dostaneme na stránku
umístěnou ve stejné složce. Odkaz se otevře defaultně ve stejném okně.

`/odkaz.html	`kořenový adresář webu (root)

`./odkaz.html	`aktuální složka

`../odkaz.html	`nadřazená složka

`../../odkaz.html	`složka o dvě úrovně nadřazená

### Odkaz absolutní

``` html
<a href="https://www.odkaz.cz" target="_blank">Odkaz na jinou stránku</a>
```

Absolutní odkaz udává plnou cestu k cíli. Zde je odkaz na stránku na
internetu a otevře se na nové kartě, jelikož jsme nastavili target na
\_blank.

### Kotva

``` html
<a href="#home">Klikem domů</a>
```

Pomocí kotvy se dostaneme v rámci stránky na tu část, jejíž element má
id stejné pojmenování jako text za hashtagem v href atributu tagu
odkazu.

``` html
<div id="home">Doma</div>
```

## Formuláře

``` html
<form></form>
```

Formulář je z hlediska uživatele množinou aktivních prvků (textová pole,
výběr z nabídky, zaškrtávací políčka...), pomocí kterých může zadat
nějaké informace. Získaná data z formuláře se pak dále zpracovávají,
například na straně serveru v jazyku php. Příkladem mohou být
objednávkové nebo přihlašovací či registrační formuláře. Kontrola
zadaných údajů může být na straně klienta (JavaScript) i serveru.
Odeslání dat z formuláře se realizuje aktivací prvku input submit.

Na příkladu níže vidíte jak vypadá kód jednoduchého formuláře.

``` html
<form action="/form.php" method="post">
    <label for="jmeno">Jméno:</label>
    <input type="text" id="jmeno" name="jmeno">
    <label for="prijmeni">Příjmení:</label>
    <input type="text" id="prijmeni" name="prijmeni">
    <input type="submit" value="Odešli">
</form>
```

![](media/image13.png)Prvky formuláře jsou in-line elementy, tudíž se
zobrazí pěkně vedle sebe na jednom řádku. Toto lze pak změnit úpravou
kódu a kaskádových stylů.

`action	`Atribut specifikuje, kam odeslat data po odeslání formuláře.

`method	`Atribut specifikuje metodu odeslání dat. Metody mohou být GET
nebo POST.

### Popisné prvky

#### Label

``` html
<label></label>
```

Než začneme s aktivními prvky, je dobré nejprve zmínit element label,
který slouží jako popisek právě těmto prvkům, aby uživatel věděl, na co
vlastně kliká, nebo co má do pole zapsat. Výhodou je, že klikem na label
lze aktivovat příslušný prvek, což je výhoda např. u checkboxu nebo
radiobuttonu. Jsou to prvky malé a není uživatelsky přívětivé se
trefovat jen do nich. Label zabírá přeci jen víc místa.

`for	`Atribut specifikuje, na který prvek formuláře se label váže. For
musí souhlasit s id příslušného prvku.

``` html
<label for="souhlas">Souhlasím s podmínkami</label>
<input type="checkbox" id="souhlas" name="souhlas">
```

#### Fieldset a legend

``` html
<fieldset></fieldset>
```

V případě, že chceme opticky sdružit nějakou skupinu prvků, obalíme je
tagem fieldset, což kolem nich vytvoří rámeček.

``` html
<legend></legend>
```

Pakliže bychom rádi dali i této skupině prvků v rámečku nějaký popis,
můžeme použít element legend uvnitř fieldsetu.

``` html
<fieldset>
  <legend>Základní údaje</legend>
  <label for="jmeno">Jméno:</label>
  <input type="text" id="jmeno" name="jmeno">
  <label for="prijmeni">Příjmení:</label>
  <input type="text" id="prijmeni" name="prijmeni">
 </fieldset>
```

![](media/image15.png)

### 

### 

### Aktivní prvky

#### Input

``` html
<input>
```

Input neboli vstupní vstupní pole je nejrozmanitější z aktivních prvků.
Jednotlivé typy si rozebereme níže.

`type	`Atribut specifikuje, o který typ vstupního pole input se jedná.

`name	`Velice důležitý atribut pro identifikaci a zpracování dat z
formuláře.

`placeholder	`Pokud jde o textový input, placeholder se zobrazuje ve
formě nápovědního textu ve vstupním poli do doby jeho aktivace
(kliknutím do pole). Neplést s value.

`value	`Výchozí hodnota pole, v případě submitu název tlačítka.

`checked	`U radiobuttonu a checkboxu, pokud chceme, aby políčko bylo
defaultně zašrtnuté.

`autofocus	`Jakmile je stránka načtena v prohlížeči, pole je ve stavu
focus, tzn. v případě zadávání textu můžete začít psát, aniž byste
museli do pole kliknout.

`required	`Pole musí být vyplněno.

`min, max	`U číselných nebo časových vstupních polí minimální nebo
maximální možná hodnota.

`list	`Našeptávání z nabídky možností z připojeného datalistu.

`disabled	`Pole neaktivovatelné.

[Obyčejné textové pole]{.underline}

Vstupní pole s atributem `type="text"` slouží k zadání jednoduchého
textu. V následujícím případu pro zadání jména a s příkladem užití
placeholderu, jenž při kliknutí do pole zmizí.

``` html
<label for="jmeno">Jméno:</label>
<input type="text" id="jmeno" name="jmeno" placeholder="Zadejte jméno">
```

![](media/image16.png)

![](media/image17.png)Zde máme podobné vstupní pole s předvyplněnou
hodnotou, kterou v případě zadávání hodnoty jiné musíme smazat.
Atributem size jsme upravili šířku pole.

``` html
<label for="jmeno">Jméno:</label>
<input type="text" id="jmeno" name="jmeno" value="Markétka" size="4">
```

[Pole pro heslo]{.underline}

Vstupní pole s atributem `type="password"` slouží k zadání hesla, zadaný
text se zobrazí jako kuličky. Na této ukázce s využitím placeholderu,
první obrázek před kliknutím na prvek a druhý po zadání hesla.

``` html
<label for="heslo">Heslo:</label>
<input type="password" id="heslo" name=" heslo" placeholder="Zadejte své heslo">
```

![](media/image18.png)![](media/image19.png)

[Pole pro email]{.underline}

Vstupní pole s atributem `type="email"` slouží k zadání emailu, přičemž
kontroluje správnost zadaného formátu textu.

``` html
<label for="email">Email:</label>
<input type="email" id=" heslo" name="email" placeholder="Zadejte svůj email">
```

[Checkbox]{.underline}

Vstupní pole s atributem `type="checkbox"` je zatrhávací tlačítko pro
výběr jeho hodnoty. Příklad nám ukazuje dva checkboxy, první z nich má
nastavený atribut checked, prvek tedy bude defaultně zaškrtnutý.

``` html
<label for="souhlas">Souhlasím s podmínkami</label>
<input type="checkbox" id="souhlas" name="souhlas" checked>
<label for="news">Chci zasílat newsletter</label>
<input type="checkbox" id="news" name="news">
```

![](media/image20.png)

[Radio]{.underline}

Vstupní pole s atributem `type="radio"` je rovněž zatrhávací tlačítko,
ale s tím rozdílem, že se ze skupiny více radio polí vybírá jen jedna
hodnota. Tato skupina musí mít stejný atribut `name`. Atribut `checked`
funguje stejně jako u checkboxu. Všimněte si, že když prohodíte pořadí
labelu a inputu, projeví se to i na výsledku.

``` html
<input type="radio" id="vek1" name="vek" checked>
<label for="vek1">0-30</label>
<input type="radio" id="vek2" name="vek">
<label for="vek2">31-60</label>
<input type="radio" id="vek3" name="vek">
<label for="vek3">61 a víc</label>
```

[Pole pro časové údaje]{.underline}

Vstupní pole s atributem `type="time"`, `type="date"` a `type="time"`
slouží pro výběr časových údajů. Na tomto příkladu si u výběru data
omezíme výběr na rok 2023 pomocí atributů `min` a `max`.

``` html
<label for="cas">Výběr času:</label>
<input type="time" id="cas" name="cas">
<label for="datum">Výběr data:</label>
<input type="date" id="datum" name="datum" min="2023-01-01" max="2023-12-31">
<label for="datumcas">Kombinovaný výběr:</label>
<input type="datetime-local" id="datumcas" name="datumcas">
```

![](media/image22.png)

[Pole pro čísla]{.underline}

Vstupní pole s atributem `type="number"` slouží pro vložení čistě
číselné hodnoty. Defaultně je vstup nastavený na celá čísla, pomocí
atributu step lze změnit. V příkladu níže na desetinná čísla s přesností
na 1 desetinu. Lze pomocí atributů min a max nastavit i mezní hodnoty.
Čísla lze zadávat přímo z klávesnice nebo možno využít krokovací šipky,
které se zobrazí při aktivaci prvku klikem myši.

``` html
<label for="cislo">Vyber počet:</label>
<input type="number" id="cislo" name="cislo" min="0" step="0.1">
```

[Pole pro nahrání souboru]{.underline}

Vstupní pole s atributem `type="file"` slouží k nahrání souboru
z lokálního úložiště. Defaultně je input nastaven na výběr jednoho
souboru, pokud nastavíte atribut multiple, můžete vybrat více souborů
najednou.

``` html
<label for="soubory">Vyberte soubory:</label>
<input type="file" id="soubory" name="soubory" multiple>
<label for="soubor">Vyberte soubor:</label>
<input type="file" id="soubor" name="soubor">
```

![](media/image23.png)

[Hidden pole]{.underline}

Pole s atributem `type="hidden"` má nastavenou hodnotu, ale uživateli se
nezobrazuje. To slouží k předání skytých dat bez zásahu uživatele.

``` html
<input type="hidden" name="schovany" value="nějaká data">
```

[Submit]{.underline}

Vstupní pole s atributem `type="submit"` spustí odeslání dat. Kam a
jakou metodou specifikují atributy tagu form -- action a method.

``` html
<input type="submit" value="Odešli data">
```

![](media/image24.png)

#### Textarea

``` html
<textarea></textarea>
```

Textové pole je podobné input poli textového typu, leč podporuje
víceřádkový text a má obdobné použití atributů -- `name`, `placeholder`,
`autofocus`, `disabled`. Value zde neexistuje, výchozí hodnotu nastavíme
textem mezi tagy (volitelné). V pravém dolním roku je zobáček, který
umožňuje resize pole.

`cols	`Atribut definuje výchozí viditelnou šířku pole v počtu znaků na
šířku.

`rows	`Atribut definuje výchozí viditelnou výšku pole v počtu řádků.

`wrap	`Atribut specifikuje zalamování textu. Defaultně je nastaven na
soft, tzn. text se odesílá tak, jak je zapsán a zalamuje se jen v
mezeře. Výjimku tvoří slova delší než řádek. Dále existují parametry
hard (zalomení i uprostřed delších slov) a off (text se nezalamuje
vůbec).

``` html
<textarea name="text" cols="15" rows="5">
  Tento text se zobrazí jako výchozí hodnota :-)
</textarea>
```

#### Select a Option

``` html
<select></select>
```

Select je pole výběru z více možností. Rovněž sdílí několik společných
atributů s imput polem -- `name`, `placeholder`, `autofocus`,
`disabled`. Možnosti jsou v párových tazích option.

`size	`Atribut definující počet zobrazovaných řádků. Defaultní size 1 se
zobrazí jako řádek s roletkovým menu. Vyšší size bude zobrazovat daný
počet možností se scrollbarem.

`multiple	`Atribut definuje výchozí viditelnou výšku pole v počtu řádků.

``` html
<option></option>
```

Všechny možnosti pro select jsou jedna po druhé obaleny v párovém tagu
option. Pozor, hodnota v option je nastavena pomocí atributu `value`.
Text mezi tagy není hodnotou.

`selected	`Atribut definující option, který se bude po načtení stránky
zobrazovat jako vybraný.

``` html
<select name="zvirata">
    <option value="lion">Lev</option>
    <option value="giraffe" selected>Žirafa</option>
    <option value="ape">Opice</option>
    <option value="frog">Žába</option>
</select>
<select name="zvirata" size="3">
    <option value="lion">Lev</option>
    <option value="giraffe" selected>Žirafa</option>
    <option value="ape">Opice</option>
    <option value="frog">Žába</option>
</select>
```

#### Datalist

``` html
<datalist></datalist>
```

Datalist se používá jako našeptávač možností ve spojení s tagem imput,
např. typu text. Aby spojení inputu a datalistu bylo funkční, input musí
mít nastaven atribut `list` stejně jako `id` datalistu. Možnosti jsou
tentokrát v nepárových tazích option. Zobrazují se hodnoty z atributu
`value`.

``` html
<input type="text" list="zvirata">
<datalist id="zvirata">
    <option value="žirafa">
    <option value="opice">
    <option value="žába">
    <option value="lev">
</datalist>
```

## Plovoucí rám

``` html
<iframe></iframe>
```

Inline frame neboli plovoucí rám se používá pro vložení jiné webové
stránky uvnitř aktuální stránky, ale lze využít například i pro videa
z Youtube nebo mapy z Google. Využívá známé atributy `src`, `name`,
`height`, `width`. Pro šířku a výšku můžete zadat čísla bez jednotek
(chápána v pixelech), nebo jako procenta, vizte příklad níže.

``` html
<iframe src="https://www.seznam.cz/" name="Seznam.cz" height="300" width="100%"> </iframe>
```

## Obrázky

``` html
<img>
```

Obrázky -- images jsou zapisovány nepárovým tagem img. Odkaz na samotný
obrázek na úložišti nebo webu nastavíme ve známém atributu `src`. Pro
nastavení vlastní výšky a šířky obrázku, aby v layoutu stránky bylo
vyhrazeno místo ještě před načtením samotného obrázku, jsou zde atributy
`height`, `width` v celých číslech bez jednotek, které prohlížeč přečte
jako pixely. Obrázky jsou in-line elementy.

`alt	`Atribut definující zástupný text, který se zobrazí v případě
nenačtení obrázku. Další funkcí je, že text je předčítán programem pro
nevidomé, kteří si stránku otevřou, aby věděli, co na obrázku je. Proto
je důležité atribut nezapomínat.

`usemap	`Atribut okazující na element mapy, v případě, že chceme obrázek
využít jako obrázkovou mapu s klikatelnými oblastmi odkazujícími na jiné
stránky apod.

`title	`Pokud najedete myší na obrázek, zobrazí se vám title v bublině.

`srcset	`Atribut se používá v případě adaptivního obrázku, pokud chceme
při různých velikostech okna, aby se měnil i zdroj obrázku.

`sizes	`Atribut definuje změny dimenzí obrázku podle velikosti stránky.

``` html
<img src="./pics/kocka.jpg" alt="kočka na střeše" height="300" width="300">
```

*Ukázka kódu klasického obrázku s nastavenými atributy zdroje,
zástupného textu a dimenzí.*

``` html
<img src="kocka.jpg" alt="kočka na střeše" usemap="#mapa">
<map name="mapa">
  <area shape="circle" coords="100,100,20" alt="Kočka" href="cat.html">
  <area shape="rect" coords="150,200,200,250" alt="Okno" href="window.html">
  <area shape="circle" coords="250,250,15" alt="Miska s mlékem" href="milk.html">
</map>
```

*Ukázka kódu obrázkové mapy. Area tagy vymezují oblasti na obrázku,
které fungují jako odkazy.*

``` html
<img src="kocka.jpg" 
alt="kočka na střeše" 
srcset="kocka_s.jpg 600w,
```

> ``` text
> kocka_m.jpg 1024w,
> ```
>
> ``` text
> kocka_l.jpg 1600w" 
> ```

``` text
	sizes="(min-width: 768px) 80vw,
```

> ``` text
> 100vw">
> ```

*Ukázka kódu adaptivního obrázku. Sizes -- od šířky okna 768px bude
obrázek v šíři 80% viewportu, v menších oknech přes celou šíři
viewportu. Ze srcset vidíme, že jsou různé zdroje obrázku pro různé
šířky oken.*

``` html
<picture></picture>
```

Párový tag picture zjednodušuje zápis adaptivního obrázku.

``` html
<source>
```

Všiměte si na příkladu užití jednoduchého tagu source s atributy `media`
(definuje, kdy se má zdoj zobrazit) a `srcset`. Tag img zakomponujeme
pro případ, že by návštěvník stránky měl zastaralý prohlížeč.

``` html
<picture>
  <source media="(min-width: 600px)" srcset="kocka_s.jpg">
  <source media="(min-width: 1024px)" srcset="kocka_m.jpg">
  <source media="(min-width: 1600px)" srcset="kocka_l.jpg">
  <img src="kocka.jpg">
</picture>
```

### Typy obrázků

**PNG** Portable Network Graphics je bezztrátový formát obrázku, jenž
umožňuje mít průhledné pozadí a podporuje až 16 milionů barev.

**.png**

**JPEG** Joint Photographic Experts Group je zkratka pro formát
komprimovaného obrázku, jenž tím páden zabírá málo místa a nepodporuje
průhlednost. Je třeba si dávat pozor na zvětšování obrázků v
responzivním layoutu stránky. Pokud byste neúměrně zvětšili hodně
komprimovaný obrázek, byl by rozmazaný.

**.jpeg, .jpg** **, .jfif, .pjpeg, .pjp**

**ICO** Použití pro favico -- obrázek, který se zobrazuje v oušku
stránky ve vrchní liště.

**.ico, .cur**

**GIF** Graphic interchange format. Formát dobrý pro jednoduché obrázky
a animace. Podporuje jen 256 barev a podporuje průhlednost.

**.gif**

**SVG** Scalable Vector Graphics. Formát SVG je vektorová grafika v XML
formátu s podporou animací. Využívá písma a základních geometrických
tvarů, jako obdélník, kruh, elipsa, čára, mnohoúhelník. Nehodí se pro
fotografie, využívá se hlavně u ikon a grafiky pro web. Kvalita
zobrazení obrázku se nemění při změně rozměrů. Je možno klasicky dát
jako obrázek img do zdroje atributu src, ale také umístit do stránky
přímo v tagu svg. Modifikace pomocí CSS jsou rozmanité.

> ``` html
> <svg width="400" height="200">
> ```
>
> ``` html
> <rect width="400" height="200"/>
> ```
>
> ``` html
> </svg>
> ```

Takto bychom nadefinovali přímo obdélník o rozm. 400 x 200 px v kódu.

**.svg**

**APNG** Animated Portable Network Graphics. Používá se pro animované
sekvence bez ztráty kvality.

**.apng**

Víc o těchto tazích týkajících se multimédií v první části skript
věnovaných webdesignu a CSS3 animaci.

# CSS -- Kaskádové styly

CSS je zkratkou pro Cascading Style Sheets.

## Zápis CSS

Nejdřív vybereme selektor -- v tomto případě jsou to všechny elementy
h1, následují složené závorky, které vymezují vlastnosti platné pro daný
selektor. Následuje název vlastnosti a za dvojtečkou hodnota vlastnosti
(může být vícenásobná). Jednotlivé deklarace vlastností mezi sebou
oddělujeme středníky.

``` css
h2 {color: red; text-decoration: underline;}
```

## Umístění CSS

### Inline

Zápis CSS se provádí přívo v tagu elementu v atributu `style`. Odpadá
zde nutnost selektoru, CSS styl bude platit jen pro tento a žádný jiný
element.

``` html
<p style="color: blue; text-align: right">Odstavec s inline CSS</p>
```

### Stylopis

Stylopis neboli interní CSS se zapisuje uvnitř tagu `<style></style>` v
hlavičce dokumentu.

``` html
<style>
  p {
    color: blue;
    text-align: right;
  }
</style>
```

### Externí soubor CSS

CSS se může nacházet i v externím souboru s příponou .css. Ten do našeho
HTML dokumentu zakomponujeme pomocí tagu `<link>` v hlavičce.

``` html
<link rel="stylesheet" href="./style.css">
```

## Typy selektorů

Pokud není CSS styl zapsán jako inline v atributu `style` přímo v tagu
elementu, je třeba používat selektor. Jmenné konvence při psaní tříd a
id nejsou úplně striktní, ale nejvhodnější zápis je pouze malými písmeny
s pomlčkami jako oddělovači slov. Názvy tříd a id nesmějí začínat
číslovkami.

### Základní selektory

#### Element

Jako selektor se vezme jméno tagu elementu. Všechny elementy tohoto
jména na stránce budou mít stejné vlastnosti, které jim deklarujeme.

``` css
p {color: blue; text-align: right;}
```

*Zde jsme nadefinovali elementu p modrou barvu a text bude zarovnaný
vpravo. Bude platit pro všechny odstavce na stránce.*

#### Třída

Pokud například nechceme, aby se vybraly všechny odststavce na stránce,
ale jen některé, sáhneme po selektoru třída. Název třídy se musí psát v
CSS zápisu s tečkou před.

``` css
.trida {color: blue; text-align: right;}
```

V HTML se u těchto vybraných elementů musí třída specifikovat v atributu
`class`.

``` html
<p class="trida">Toto je odstavec s CSS třídou "trida"</p>
```

#### Id

V případě, že chceme vybrat unikátní element, sáhneme po selektoru id.
Jedno id nesmí používat více elementů a CSS zápisu názvu id předchází
hashtag.

``` css
#unikatni-id {color: blue; text-align: right;}
```

V HTML tohoto elementu musí id specifikovat v atributu `id`.

``` html
<p id="unikatni-id">Toto je odstavec s id "unikatni-id"</p>
```

#### Univerzální selektor

Když bychom rádi, aby platila nějaká CSS pravidla na stránce obecně pro
veškeré elementy, použijeme univerzální selektor.

``` css
* {color: darkblue; text-align: right;}
```

#### Seskupení selektorů

Máme-li pro více selektorů stejné vlastnosti, je možno je napsat
dohromady oddělené čárkou.

``` css
p, h2, h3 {color: darkblue; text-align: right;}
```

Můžete dokonce i kombinovat jednotlivé typy mezi sebou.

#### Specifikace selektorů

Chceme-li specifikovat třeba jen odstavce nějaké konkrétní třídy, toto
lze taky zapsat. Pozor, bez mezer!

``` css
p.trida {color: darkblue; text-align: right;}
```

Dále můžeme specifikovat element na základě validního atributu. Celý
atribut je v hranatých závorkách.

``` css
input[type="text"] {background: red;}
```

### Kombinátory

Předchozí kapitola byla vcelku nenáročná na představu. U kombinátorů to
bude těžší. Ukážeme si to na jednoduchém strukturovaném kódu.

``` html
<body>
  <div>
    <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit.</p>
    <article>
      <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit.</p>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
    </article>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
  </div>
  <img src="./pics/kocka1.jpg" alt="kocka">
  <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
  <div>
    <img src="./pics/kocka2.jpg" alt="kocka">
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
  </div>
  <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</p>
  <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
</body>
```

Pro ještě lepší představu si můžeme kód graficky znázornit jako
hierarchický strom HTML elementů.

*Poznámka pro ty z vás, kteří už vědí, co je DOM, k němu se dostaneme
později.*

![](media/image28.png)

#### Potomek

Potomek je element, který se vyskytuje jakkloliv strukturně hluboko
zahnízděný v jiném elementu - předkovi. Na příkladu níže tedy styl platí
pro všechny odstavce, které jsou hierarchicky níž než div. Na obrázku
veškeré elementy p napravo od obou div.

``` css
div p {color: darkblue; text-align: right;}
```

#### Dítě

Dítě je přímý potomek jiného elementu. Na obrázku tedy všechny odstavce
jen o jednu úroveň níže než elementy div.

``` css
div > p {color: darkblue; text-align: right;}
```

#### Sousední sourozenec

Vybere element typu za znaménkem +, který následuje hned za prvním
členem kombinátoru. V příkladu platí pouze pro tento případ: div 2,
který má přímo hierarchicky vedle sebe odstavec.

Div číslo 1 má přímého sourozence element img, čili toho se kombinátor
netýká.

``` css
div + p {color: darkblue; text-align: right;}
```

#### Obecný sourozenec

Vybere všechny elementy typu za znaménkem \~ na stejné úrovni, které
následují po prvním členu kombinátoru. V příkladu vybere všechny
odstavce ve stejné lajně s div 1 a 2.

``` css
div ~ p {color: darkblue; text-align: right;}
```

### Pseudo-třídy

Sytlování na základě určitého stavu elementu řešíme pomocí tzv.
pseudo-tříd. Pseudo-tříd je hromada, uvádím proto jen ty nejdůležitější.
U několika následujících možností budu uvádět i případy s odkazy. Pokud
budete stylovat u odkazů každou nebo jen některé z možností, je třeba
zachovat pořadí, ve kterém je uvádím.

#### Link

Tato akce je spojena výhradně s odkazy. Styl je přiřazen odkazu, který
ještě uživatel nenavštívil.

``` css
a:link {color: red;}
```

#### Visited

Roněž akce spojena pouze s odkazy. V tomto případě se jedná o styl
přiřazen již navštívenému odkazu.

``` css
a:visited {color: green;}
```

#### Hover

Hover je akce, kdy se kurzor myši nalézá nad plochou vymezenou
elementem. Zde po najetí myší na div nastavíme žluté pozadí a tmavý
rámeček. Pokud plochu elementu opustíme, styl se opět přestane
projevovat.

``` css
div:hover {background: yellow; border: 1px solid black;}
a:hover {color: blue;}
```

#### Active

Pokud je prvek aktivovaný, tzn. je něj zrovna kliknuto (zejména se jedná
o tlačítka a odkazy), i při této akci je možno nastylovat. (pozn.
neplést aktivovaný a aktivní prvek)

``` css
button:active {border-width: 2px;}
a:active {color: darkred;}
```

#### Focus

Zejména u formulářových prvkům (focus klikem myší nebo přeskočení
tabulátorem) ale i tlačítek a odkazů (focus tabulátorem) lze nastylovat
akci focus, při níž je prvek vybraný (odkaz, tlačítko -- můžeme
odentrovat) nebo aktivní (input -- můžeme zadávat z klávesnice).

``` css
input[type="text"]:focus {background: yellow;}
a:focus {border: 1px solid blue;}
```

#### First child, nth child & last child

Tyto pseudo-třídy úzce specifikují, které dítě nadřazeného elementu se
bude stylovat -- musí se shodnout typ a pořadí. Na příkladech vidíte, že
se bude stylovat odstavec, který zároveň splňuje podmínku pořadí v řadě
všech potomků v každém jeho přímém předkovi. Doporučuji si vyzkoušet
každý z případů separátně na ukázkovém kódu ze sekce Kombinátory.

``` css
p:first-child {color: darkblue;}
p:nth-child(3) {color: darkblue;}
p:last-child {color: darkblue;}
```

#### First of type, nth of type & last of type

Podobné pseudo-třídy těm předchozím s tím rozdílem, že selektor musí
splňovat podmínku pořadí v řadě sourozenců stejného typu. Rovněž
doporučuji vyzkoušet na ukázkovém kódu.

``` css
p:first-of-type {color: darkblue;}
p:nth-of-type(3) {color: darkblue;}
p:last-of-type {color: darkblue;}
```

### Pseudo-elementy

Pseudo-elementy jsou jednak určené pro stylování určité části elementu.
Pozor na zápis -- oproti pseudo-třídám se píší s dvojitou dvojtečkou. Na
příkladech níže vidíte, jak jednoduše nastylovat první řádek odstavce a
první písmeno odstavce.

``` css
p::first-line {color: darkblue;}
p::first-letter {color: darkblue; font-size: x-large;}
```

Dále můžeme pomocí pseudo-elementů before a after vložit nějaký obsah
před nebo za element. V příkladu přidáváme obrázek před/za element
hlavního nadpisu.

``` css
h1::before {content: url(./circle.svg);}
h2::after {content: url(./circle.svg);}
```

## Priorita pravidel

Je třeba si uvědomit, že každý zápis css stylu má svoji určitou váhu a
svou roli hraje i specifikace zápisu.

1.  **!important** -- Nejvyšší priorita, jež přepíše veškerá předešlá
    pravidla. Nedoporučuje se moc používat.

``` css
p {color: blue !important;}
```

2.  **Inline zápis** -- má vyšší váhu než externě připojený css soubor
    nebo interní styl zapsaný v hlavičce dokumentu v tagu style. Hodnota
    specifikace 1000.

``` html
<p style="color: blue;">Lorem ipsum dolor sit amet.</p>
```

3.  **Interní a externí styly**

    1.  **Id** -- selektor identifikátorem s hodnotou specifikace 100.

    2.  **Třídy, pseudo-třídy, atributové selektory** -- hodnota
        specifikace 10.

    3.  **Elementy, pseudo-elementy --** hodnota specifikace 1.

    4.  **\*** **--** obecný selektor má specifikační hodnotu 0.

> Pokud je v jednom dokumentu stejný selektor, pak záleží na pořadí.
> Pozdější zápis přepíše ten předešlý.

4.  **Výchozí hodnoty**

Specifikace se sčítají, proto bude mít `p.trida` větší prioritu než jen
selektor `p`.

### Dědičnost

Dále je třeba mít na paměti, že u kaskádových stylů hraje svoji roli i
dědičnost. To znamerná, že některé vlastnosti přejímají od nařazeného
elementu automaticky i jeho potomci. To usnadňuje práci a hlavně šetří
řádky kódu. Výjimkou jsou input a button elementy, ty jsou z dědičnosti
vyjmuty.

Dědičnost se týká zejména viditelnosti, vlastnosti textu, barvy. Některé
vlastnosti se nedědí vůbec, např. rámeček.

Specifiikace zápisu má vždy přednost před dědičností.

## Barvy

Pomocí CSS stylování můlžeme nastavit barvu textu, pozadí, rámečků.

### RGB(A) barvy

Zkratka RGB reprezentuje intenzitu barevných zdrojů světla pro složení
výsledné barvy -- Red, Green a Blue.

``` css
rgb(red, green, blue)
```

Každá z barev může nabýt hodnotu 0 až 255, což definuje intenzitu. Pro
příklad několik běžných barev.

`rgb(0, 0, 0) `černá `rgb(0, 255, 0) `zelená

`rgb(255, 255, 255) `bílá `rgb(0, 0, 255) `modrá

`rgb(255, 0, 0) `červená `rgb(255, 255, 0) `žlutá

Pokud přidáme ještě čtvrtý parametr Alpha, definujeme tím průhlednost
barvy.

``` css
rgba(red, green, blue, alpha)
```

Alpha může být buďto v procentech nebo v desetinných číslech v intervalu
od 0 do 1, přičemž 100% nebo 1 definuje barvu neprůhlednou.

``` text
rgba(60, 179, 113, 0.5)
rgba(106, 90, 205, 80%)
```

### HEX barvy

Hexadecimální zápis barvy je obdobný jako pro barvy RGB.

``` text
#rrggbb
```

Každá z barev může nabýt hodnoty 00 až ff. Šestimístný zápis se dá
zkrátit na trojmístný, pakliže každou z dvojic hodnot reprezentuje
stejný znak.

`#000000 `nebo` #000 `černá `#00ff00 `nebo` #0f0 `zelená

`#ffffff `nebo` #fff `bílá `#0000ff `nebo` #00f `modrá

`#ff0000 `nebo` #f00 `červená `#ffff00 `nebo` #ff0 `žlutá

I u hexadecimálního zápisu barev můžeme specifikovat hodnotu Alpha jako
čtvrtou dvojici hodnot.

``` text
#rrggbbaa
```

### HSL(A) barvy

Zcela odlišný je zápis barvy HSL, což je zkratka pro Hue (odstín),
Saturation (sytost), Lightness (světlost).

``` css
hsl(hue, saturation, lightness)
```

**Hue** -- Odstín je hodnota úhlu ve stupních na barevném kruhu až do
velikosti plného úhlu (0 - 360).

**Saturation** -- Sytost je procentuální hodnota, přičemž 0% jsou
odstíny šedé a 100% je plná barevnost.

**Lightness** -- Světlost je rovněž hodnota v procentech -- 0% je vždy
černá, 100% vždy bílá a 50% je hodnota „ani ztmavená ani zesvětlená".

`hsl(0, 100%, 50%) `červená

`hsl(120, 100%, 50%) `zelená

`hsl(240, 100%, 50%) `modrá

Pokud bychom chtěli definovat průhlednost, můžeme nastavit hodnotu Alpha
jako čtvrtý parametr. Hodnota může být v procentech nebo od 0 do 1,
obdobně jako u barev RGBA.

``` text
hsla(240, 100%, 50%, 0.5)
hsla(240, 100%, 50%, 50%)
```

## Jednotky v CSS

V CSS se setkáme s několika způsoby vyjádření délky. V případech, jako
jsou odsazení, výška, šířka či třeba velikost textu.

Pokud má hodnota délky jednotky, vždy píšeme v CSS zápisu bez mezery
mezi hodnotou a jednotkou!

``` css
.banner {width: 100vw;}
```

### Absolutní jednotky

Jednotky, které se k ničemu nevztahují, jejich rozměr je neměnný. Patří
zde in (Inch), px (Pixel), pc (Picas), pt (Point), cm, mm.

#### px

Pixel je asi nejvíce známá absolutní jednotka délky na webu. Velikost 1
px je rovna 1/96 z 1 in (1 in = 2,54 cm).

Nejdříve je třeba zmínit, že v kaskádových stylech se bavíme o tzv. CSS
pixelu (dále jen pixel) a ne hardwarovém pixelu, který je ekvivalentní k
jednomu obrazovému bodu displeje. Ty nás nezajímají. Jejich cesty se
rozdělily v době nástupu displejů s vysokým rozlišením.

Výchozí hodnota velikosti písma ve většině prohlížečů je nastavena na
16px. Výchozí velikost můžeme změnit tímto způsobem:

``` css
html {font-size: 18px;}
```

Použití pixelů by se mělo omezit na opravdu nezbytné případy jako
rámečky, dekorace. V případě velikosti písma v pixelech v různých
částech dokumentu by to znemožňovalo uživatelům využít zvětšenou výchozí
velikost písma pro náš web.

### Relativní jednotky

Jednotky, které se vztahují k jiné délkové vlastnosti. Použití
relativních jednotek je lepší pro zobrazování webu na různých
zařízeních.

#### rem

Jednotka 1rem je rovna výchozí velikosti písma prohlížeče, což je
většinou 16px. Pokud užvatel nenastaví jinou defaultní hodnotu písma.

#### em

Jednotka je vztažena k velikosti fontu v daném elementu.

#### vw, vh

Viewport je velikost okna prohlížeče. Viewport width (vw) je jeho šířka
a viewport height (vh) je jeho výška, přičemž hodnota je ekvivalentní k
procentuální délce.

100vw je celá šířka viewportu, 50vh je poloviční výška viewportu.

#### %

Hodnota délky v procentech se vztahuje k nadřazenému elementu.

## Box model

Představte si každý HTML element jako box, který má několik vrstev:

-   **obsah elementu** -- text, obrázek, média, jiné elementy

-   **padding** -- vnitřní odsazení elementu

-   **border** -- ohraničení elementu

-   **margin** -- vnější odsazení elementu

Rozměry box modelu zahrnují všechny tyto prvky. Povoleny jsou jen kladné
hodnoty.

![](media/image29.png)

### Šířka a výška

`width`, `height`

Je třeba mít na paměti, že pokud elementu přiřazuji délku a šířku,
dimenzuji tím pouze část obsah elementu.

``` css
div.ctverec {
  height: 5rem;
  width: 5rem;
  background-color: blue;
}
```

*Zde chci, aby div vypadal jako modrý čtverec, takže mu nadefinuji
stejnou výšku i šířku. A samozřejmě barvu pozadí.*

Co se týče výšky elementu, většinou se nastavovat nemusí, jelikož se
element výškově přizpůsobí obsahu. Pokud obsah stránky ve vertikálním
směru přeteče, zobrazí se vertikální scrollbar a uživatel se může
pohybovat nahoru a dolu pomocí kolečka myši. Výšku nastavujeme u prvků
jako jsou navigační lišta, footer, div jako obrazec ap.

Je třeba si dávat pozor na horizontální přetečení, to je vysloveně
nežádoucí.

Pokud u obrázku zadáte pouze jeden z rozměrů, druhý se dopočítá
automaticky, aby se nezměnil poměr stran. Na příkladu uvádím obrázek,
který bude zabírat 50% šířky nadřazeného elementu.

``` css
img {width: 50%;}
```

U textových in-line elementů (span, strong, em...) se šířka nastavit
nedá.

### Maximální šířka

``` css
max-width
```

Abychom zabránili případu, kdy šířka blokového elementu (div, p) je
větší než šířka okna a tím "přeteče" mimo okno, použijeme místo `width`
vlastnost `max-width`. Tím docílíme toho, že element se v horizontálním
směru smrskne a výšku elementu natáhne, pokud je obsahem čistě text. V
případě, že by obsahem byl např. obrázek, je třeba mu přiřadit takto
šířku `img {width: 100%;}`.

``` css
div {max-width: 50rem;}
```

Existují i vlastnosti `min-width`, `max-height` a `min-height`, jejich
použití je obdobné.

V případě `max-height` je třeba nastavit i vlastnost `overflow: auto;`.
Pokud by obsah byl delší na výšku než element, pak by obsah přetekl.

### ![](media/image30.png)Padding

Používá se k odsazení obsahu elementu od ohraničení. Takto vzniklý
prostor je průhledný. Pro každou stranu elementu existuje specifická CSS
vlastnost:

``` css
div.ctverec {
  padding-top: 0.5rem;
  padding-right: 1.5rem;
  padding-bottom: 0.8rem;
  padding-left: 0.9rem;
}
```

Dá se ale zapsat i zkráceně jako `padding`, přičemž pořadí hodnot je
vždy top-right-bottom-left.

``` css
div.ctverec {padding: 0.5rem 1.5rem 0.8rem 0.9rem;}
```

V případě, že je padding na každé straně elementu stejný, lze zápis opět
zjednodušit:

``` css
div.ctverec {padding: 1.5rem;}
```

Pokud je stejná hodnota paddingu pro vertikální směr (top-bottom) a
stejná pro horizontální směr (left, right):

``` css
div.ctverec {padding: 1.5rem 0.5rem;}
```

### Margin

Používá se k vytvoření mezery mezi elementy. Je to průhledný vnější
prostor od ohraničení elementu. Pravidla pro zápis jsou zcela stejná
jako u paddingu.

``` css
div.ctverec {	div.ctverec {
  margin-top: 0.5rem;	  padding: 0.5rem 1.5rem 0.8rem 0.9rem;
  margin-right: 1.5rem;	}	
  margin-bottom: 0.8rem;
  margin-left: 0.9rem;
}
```

Důležité zmínit, že marginy dvou sousedních elementů se spolu nesčítají,
ale splynou. Pokud tedy jeden element má margin 50px a druhý 30px,
výsledný margin bude roven 50px.

### Border

Ohraničení elementu můžeme nazvat i jako rámeček. Oproti marginu a
paddingu můžeme krom jeho rozměru nastylovat i jeho vzhled: styl čáry,
barvu a případně i zaoblení rohu.

Tentokrát ukážu jako první zkrácený zápis, se kterým se setkáte
nejčastěji:

``` css
div.ctverec {border: 1px solid #f00;}
```

*Chceme plný červený rámeček okolo divu o tl. 1px. Zápis je vždy
v pořadí tloušťka čáry, styl čáry, barva.*

Pokud chceme vlastnosti každé ze stran nastavit samostatně:

`border-top`, `border-right`, `border-bottom`, `border-left`

Pokud chceme samostatně nastavit šířku, styl nebo barvu (příklad pro
`border-top`):

`border-top-width`, `border-top-style`, `border-top-color`

Ukážeme si toto vše na příkladu, kde se projeví i pravidlo kaskády, že
pozdější zápis je platný:

``` css
div.ctverec {
  border: 1px solid #f00;
  border-right-width: 5px;
  border-bottom-style: dashed;
  border-left-color: #ff0;
}
```

*Nejdříve jsme nastavili červený plný rámeček o tl. 1px okolo celého
divu, pak jsme přepsali šířku pravého rámečku na 5px, styl spodního
rámečku na čárkovaný a barvu levého na žlutou.*

V rámci ohraničení elementu je možno i zaoblit rohy pomocí
`border-radius`.

``` css
div.ctverec {
  border: 1px solid #f00;
  border-radius: 5px;
}
```

Když si to shrneme -- rámeček může být na každé straně jiný a dokonce
může být i jen částečný, pokud nadefinujeme třeba jen některé ze stran.

### Alternativní box model

Pokud byste rádi změnili způsob počítání rozměrů tak, aby v uživatelem
definované šířce a výšce byly zohledněn i padding, border a margin,
stačí nastavit vlastnost `box-sizing` na `border-box`.

Pokud bychom chtěli vlastnost pouze pro jeden element:

``` css
div.ctverec {
  height: 5rem;
  width: 5rem;
  border: 1px solid #f00;
  padding: 0.5rem;
  margin: 0.3rem;
  box-sizing: border-box;
}
```

*S takto nastavenou vlastností box-sizing bude šířka i výška boxu 5rem
včetně všech odsazení a okrajů.*

Tuto vlastnost můžeme nastavit jako defaultní pro celý dokument:

``` css
html {box-sizing: border-box;}
```

pozn.: Defaultní hodnota standardního box modelu je
`box-sizing: content-box;`

## Outline

![](media/image31.png)Outline neboli obrys není součást box modelu a ani
se nepočítá do rozměrů elementu. Je vykreslována vně ohraničení
elementu. Definujeme ji stejnou po celém obvodu. Má tyto vlastnosti:

`outline-style` -- solid, dotted, dashed apod.

``` css
outline-color
```

`outline-width` -- v jednotkách (px) nebo thin, medium, thick

`outline-offset` -- udává odstup od border. Offset se nedá zapsat ve
zkráceném zápisu, musí se definovat zvlášť.

`outline` -- zkrácený zápis v pořadí: tloušťka, styl, barva.

``` css
p {outline: thin dashed blue;}
```

*Zde máme odstavec s modrou tenkou tečkovanou outline.*

## Text

### Barva textu

Můžeme nastavit jak barvu textu, tak barevné pozadí elementu.

``` css
p {	p {
  color: #fff;	  color: rgb(255, 50, 70);		
  background-color: #000;	}
}	
```

*Bílý text odstavce na černém pozadí. Text odstavce bude v barvě odstínu
červené.*

### Zarovnání textu

Pomocí `text-align` zarovnáváme text nalevo (defaultně `left`), napravo
(`right`) nebo na střed (`center`).

``` css
h1 {text-align: center;}	p {text-align: right;}
```

*Nadpis bude zarovnán na střed. Text odstavce bude zarovnán napravo.*

### Dekorace textu

``` css
a {text-decoration: underline;}
```

Použijeme-li vlastnost `text-decoration`, jsme schopni nastavit textu
podtržení, přeškrtnutí, čáru nad textem apod. Odkazy jsou v HTML
defaultně podtržené, pokud toto nastavení chceme změnit, použijeme:

``` css
a {text-decoration: none;}
```

Jako příklad uvádím pouze zjednodušený zápis, jelikož v běžné praxi víc
nepoužijete. Zápis hodnot je v pořadí styl dekorace, barva dekorace,
styl linky a tloušťka linky.

``` css
span {text-decoration: overline blue double 2px;}
span {text-decoration: line-through red;}
```

### Transformace textu

Zda se text renderuje pouze velkým či malým písmem, případně kapitálkou,
toho docílíme pomocí CSS vlastnosti `text-transform`. Může nabýt hodnot
`uppercase`, `lowercase`, `capitalize`.

``` css
p {text-transform: uppercase;}
```

### Rozestupy, mezery

#### Odsazení

Vlastnost `text-indent` odsadí první řádek textu.

``` css
p {text-indent: 3rem;}
```

#### Mezery mezi znaky

Pomocí `letter-spacing` nastavujeme prostor mezi znaky textu. Hodnota
může být i záporná.

``` css
h2 {letter-spacing: 0.5rem;}
```

#### Mezery mezi slovy

Obdoba znakových mezer, která se omezuje pouze na mezery mezi
jednotlivými slovy. Hodnota může být rovněž záporná.

``` css
p {word-spacing: 0.3rem;}
```

#### Výška řádku

CSS vlastnost `line-height` definuje mezeru mezi řádky. Defaultní
hodnota je 1.1 -- 1.2.

``` css
p {line-height: 1.5;}
p {line-height: 0.9;}
```

### Stínování textu

Chceme-li textu nastavit stínování, docílíme toho vlastností
`text-shadow`.

`h1 {text-shadow: 3px 3px;}	`*černý stín posunutý 3px doprava a dolů*

`h1 {text-shadow: 3px 3px blue;}	`*modrý stín posunutý 3px doprava a
dolů*

`h1 {text-shadow: 3px 3px 5px blue;}	`*modrý stín posunutý 3px doprava a
dolů rozostřený*

### Sloupce

Rozdělení blokového elementu (`div`, `p`) na sloupce.

`column-count` CSS vlastnost, která nám udává, na kolik sloupců se má
daný element rozdělit. `column-count: 3; `*Rozdělí nám element na 3
slopce.*

`column-fill` Zajišťuje rozložení textu ve sloupcích -- `balance`
(defaultní, rozloží do všech sloupců stejným dílem), `auto` (text
vyplňuje postupně sloupce do jejich plné výšky)

`column-gap	`Mezera mezi sloupci. Výchozí hodnota je `1em`.

`column-width	`Specifikace šířky jednoho sloupce v délkových jednotkách.

`columns	`Souhrnná vlastnost pro šířku a počet sloupečků.
`columns: 10rem 3;`

`column-span	`Specifikuje, přes kolik sloupců se roztáhne zanořený
element, např. nadpis. `column-span: 2;` nebo `column-span: all;`

`column-rule	`Souhrnná vlastnost pro oddělovací čáru mezi sloupci --
šířka, styl a barva. `column-rule: 5px solid blue;`

## Font

Pokud se bavíme o fontu, myslíme tím výběr písma a jeho vlastnosti.
Správný výběr písma je důležitý pro celkové grafické vyznění stránky.
Špatný výběr dokáže pokazit opravdu hodně.

### Výběr písma

Pomocí vlastnosti `font-family` definujeme druh písma. Druhy písma
můžeme rozdělit v základu na **serif** (patkové), **sans-serif**
(bezpatkové), **monospace** (všechny znaky zaujímají stejné místo),
**cursive** (písmo imitující psací písmo -- neplést s kurzívou, která je
angl. italic), **fantasy** (písmo ozdobné).

**Web safe fonts** jsou písma, která jsou univerzálně známá prohlížečům
a zařízením. Patří mezi ně Arial (sans-serif), Verdana (sans-serif),
Times New Roman (serif), Georgia (serif), Courier new (monospace).

Při výběru písma vždy dejte prohlížeči více možností. Pokud nezná první
možnost výběru písma, vybere druhé. Pokud nezná ani druhé, vybere třetí.
Tomuto se říká **fallback**. Stránky si vždy vyzkoušejte zobrazit na
různých zařízeních a prohlížečích, abyste si byli jisti správným výběrem
písma.

``` css
html {font-family: 'Courier New', Courier, monospace;}
```

*Pokud má název fontu více slov, vždy je dávejte do úvozovek.*

### Další vlastnosti písma

`font-size` nastavuje velikost písma, např. v pixelech, rem, em...

`font-style` umožňuje nastavit hodnoty na **normal** (defaultní),
**italic** a **oblique**. Italic a oblique jsou si podobné.

`font-weight` nastavuje tloušťku fontu na **normal** (defaultní),
**bold**, **číselná hodnota** (např. 700), **lighter** apod.

## Display

Display je jedna z nejdůležitějších vlastností. Specifikuje jak nebo
zda-li vůbec je element zobrazen. V rámci HTML části skrip jsme si něco
málo řekli o rozdělení elementů do základních typů.

### Block a in-line

Ty nejzásadnější jsou blokové a in-line elementy, které mají defaultně
vlastnost display nastavenou takto:

``` css
display: block; 
```

*Blokový element může mít libovolnou výšku a šířku a vždy začíná na nové
řádce. Na nové řádce začíná i libovolný element, co je za ním.*

``` css
display: inline; 
```

*Řádkový element zabírá jen tolik šířky, kolik zabere jeho obsah.*

Pokud bychom kvůli rozvržení stránky chtěli změnit jejich defaultní
zobrazení, můžeme tak učinit prostým přepsáním vlastnosti display. Tímto
neměníme typ elementu, ale pouze již zmíněné zobrazení elementu. Blokový
element se může chovat jako in-line a naopak.

### Viditelnost elementu

Tato vlastnost se hojně používá v součinnosti s JavaScriptem. Pokud
nějakému elementu přepíšeme display hodnotu na none, pak jej prohlížeč
nevykreslí a nezabírá ani jemu přiřazené místo.

``` css
display: none; 
```

V případě, že chceme element pouze zneviditelnit, ale s layoutem stránky
přitom nepohnout, využijeme zcela odlišné CSS vlastnosti `visibility`,
jíž nastavíme na hodnotu `hidden`. Takto zneviditelněný element zabírá
stále stejně místa jako před modifikací, jen není vidět.

``` css
visibility: hidden; 
```

### Inline-block

Pokud bychom rádi využili výhod blokových elementů v rámci jednoho
řádku, pak je k dispozici:

``` css
display: inline-block; 
```

Takovému elementu me možno přiřadit šířku, výšku, projeví se marginy,
paddingy apod. s tím rozdílem, že nezačíná na novém řádku a ani řádek za
sebou nezalamuje.

### List-item

Defaultní hodnota display pro položku seznamu `<li></li>` je
`list-item`.

``` css
display: list-item; 
```

Např. v případě, že seznam používáme pro základ navigačního menu,
přepisujeme u položky seznamu tuto hodnotu na `inline`.

`display: flex | inline-flex;` bude vysvětleno v kapitole týkající se
rozvržení stránky.

## CSS specifika vybraných elementů

### Tabulky

V části skript HTML jsme si ukázali základní CSS modifikace tabulek.
Existují ještě rozšiřující vlastnosti CSS.

`table-layout 	`Tato vlastnost nastavuje způsob, jakým se vypočítává
šířka sloupců v tabulce. Defaultně je nastaveno na `auto`, tedy podle
nejdelšího obsahu buňky. Můžeme nastavit na `fixed`, kdy jsou všechny
sloupce stejně široké -- závisí od šířky tabulky.

`border-spacing 	`Definuje mezeru mezi rámečky buněk tabulky. Může mít
jednu (ve všech směrech) nebo dvě hodnoty (horizontální a vertikální
směr). Funguje pouze, pokud má tabulka defaultní vlastnost
`border-collapse: separate; ` `table {border-spacing: 8px 5px;}`

`caption-side 	`Pozici popisku tabulky můžeme umístit nad tabulkou
(defaultní `top`), nebo pod (`bottom`).

`empty-cells 	`Definuje, zda se zobrazují rámečky prázdných buněk
(defaultní `show`), nebo schovají (`hide`). Má efekt pouze při
`border-collapse: separate;`

### Seznamy

U seznamů je také třeba se zmínit o některých dalších CSS vlastnostech.

`list-style-position 	`Touto vlastností lze u seznamů definovat, zda
budou odrážky či číslování součástí položky seznamu (`inside`), nebo vně
položky seznamu (defaultní `outside`).

`list-style-type: none; 	`Pokud použijeme hodnotu `none` pro tuto
vlastnost, odstraní se odrážky či číslování.

`list-style-image 	`Jako odrážku můžeme nastavit i obrázek.

``` css
	list-style-image: url('./square_blue.gif');
```

`list-style	`Zkrácený zápis pro seznamy v pořadí hodnot: typ, pozice
odrážky/číslování a případně url obrázku.

``` css
	list-style: square inside url('./square_blue.gif');
```

> ``` css
> list-style: circle outside;
> ```

## CSS layout

### Overflow

V případě, že je obsah elementu větší než samotný element, pak mluvíme o
přetečení obsahu mimo element. Overflow je defaultně nastaven takto:

``` css
overflow: visible;
```

Máme několik možností, jak to změnit.

`overflow: hidden; 	`Takto sice přetečení skryjeme, ale tím nevíme, co
tam vlastně je.

`overflow: scroll;	`Scroll nám zobrazí horizontální i vertikální
scrollbar, byť například ten horizontální nepotřebujeme.

`overflow: auto;	`Zobrazí takový scrollbar, který je díky přetečení
třeba.

Vlastnosti `overflow-x` a `overflow-y` nám specifikují, se kterým směrem
přetečení chceme pracovat. Nabývá stejných hodnot jako u předchozích
případů.

### Float

V minulosti byl float hojně používán při layoutu stránek. Nyní máme
mnohem šikovnější nástroje, leč je dobré mít povědomí, jak funguje,
jelikož se s ním určitě setkáte.

``` css
float: left | right | none;
```

V defaultním nastavení má každý element hodnotu `none`. Pokud elementu
(např. img) nastavíme `left` nebo `right`, vyjmeme jej tak ze
standardního toku dokumentu a bude obtékaný. Je nutné dodržet pravidlo,
že obtékaný element musí mít nastavenou šířku. Pro představu příklad
níže.

``` html
<div>
  <img src="./pics/pes.png" alt="pes">
  Nějaký dlouhý text...třeba na 20 řádků
</div>
```

*Máme zde v rámci div obrázek a nějaký text a pokud chceme, aby obrázek
byl vlevo a text jej obtékal, je třeba nastavit float. Pozor, obrázek
musí mít nastavenou šířku.*

``` css
img {width: 500px; float: left;}
```

### Position

Tato CSS vlastnost definuje způsob pozicování HTML elementu.

`position: static; 	`Defaultní pozice všech elementů na stránce. Pozice
je standardně dána jejich typem (blok, in-line...). Nemají na ni vliv
poziční vlastnosti.

Na následující hodnoty pozice mají vliv poziční vlastnosti `top` (posun
shora dolů), `bottom` (posun zdola nahoru), `left` (posun zleva doprava)
a `right` (posun zprava doleva).

`position: relative;	`Element s pozicí relativní ke své standardní
pozici. Pokud mu přiřadíme některou z CSS pozičních vlastností, posouvá
se vzhledem ke své defaultní pozici.

`position: absolute;	`Pozice absolutní. Element s pozicí absolutní se
posouvá relativně k nejbližšímu pozicovanému předkovi. Pokud nemá
žádného pozicovaného předka, pak se posouvá relativně k tělu stránky.

`position: fixed;	`Pokud má element fixed polohu, pak zaujímá pozici
vzhledem k viewportu a tam zůstává i při scrollování stránky.
Zajímavostí je, že takto pozicovaný element nezanechává za sebou prázdné
místo na stránce, kde by se měl standardně nacházet.

`position: sticky;	`Element zaujímá svoje místo na stránce do doby, než
k němu doscrollujeme. V ten moment se začne chovat jako fixed. Používá
se hlavně u navbaru, který leží pod úvodní fotkou stránky, a chceme, aby
se po odscrollování pod fotku přilepil pod vrchní okraj viewportu
(nadřazený element je body), nebo nadpisů některých sekcí (nadřazený
element může být div). Musí být přítomna alespoň jedna poziční
vlastnost, aby sticky fungoval (`top: 0;`). Pokud odscrollujeme pod
nadřazený element, zmizí i sticky element.

``` css
	div.menu {position: sticky; top: 0;}
```

Je samozřejmé, že se změnami pozic elementů přichází i úskalí --
vzájemné překrývání elementů. Tuto problematiku řeší kapitola týkající
se z-indexu.

### Media query

Media queries jsou velmi nápomocné, když chceme stránku upravit pro
různé velikosti/rozlišení obrazovek -- pro desktopový monitor, tablet
nebo mobil. Stačí si nadefinovat breakpointy a se změnou velikosti
obrazovky i vhodnější vlastnosti, jako například velikost fontu, šířka
div, chování flexboxu apod.

``` css
@media screen and (min-width: 600px) {font-size: 1.2rem;}
```

*Zde je ukázka breakpointu -- pokud je obrazovka široká 600px a víc, pak
je velikost písma 1,2rem.*

``` css
@media screen and (max-width: 600px) {font-size: 0.9rem;}
```

*Pokud je obrazovka široká 600px a méně, pak je velikost písma 0,9rem.*

Existují dva přístupy, jak stránky tímto způsobem navrhovat -- desktop
first, mobile first. V dnešní době, kdy drtivá většina uživatelů
internetu navštěvuje stránky na telefonu, je prosazován mobile first
přístup.

V praxi to znamená, že vzhled stránky nejdříve navrhnete tak, jak by měl
vypadat v mobilním zařízení a pak pomocí media query přidáte breakpointy
pro větší obrazovky (pomocí min-width).

### Flexbox

*Zdroj informací a předlohy obrázků z webu
[https://css-tricks.com/snippets/css/a-guide-to-flexbox]{.underline}*

Flexbox je velmi šikovný nástroj, který je užitečný pro dynamické
rozvržení stránky. Ve zkratce, podle velikosti zobrazovacího displeje se
mění distribuce místa pro specifické elementy v layoutu stránky.

Tyto specifické elementy jsou flex items (položky) - přímí potomci tzv.
flex kontejneru.

![](media/image32.png)

V klasickém layoutu jsme byli zvyklí na uspořádání elementů podle jejich
typu (block, in-line). U flexboxu je to uspořádání podle osy ve zvoleném
směru.

-   **flex kontejner (flex container)** -- je element, kterého určíme
    pomocí vlastnosti `display: flex;`

-   **položka (flex item) --** přímí potomci kontejneru -- děti

-   **hlavní osa (main axis)** -- ve výchozím stavu horizontální směr
    zleva doprava (lze změnit)

-   **příčná osa (cross axis)** -- vždy kolmá k hlavní ose, ve výchozím
    stavu vertikální shora dolů

#### Flex kontejner a jeho vlastnosti

``` css
display: flex;
```

Jak už bylo zmíněno v krátkém přehledu, HTML element, který je definován
`display: flex;` se začne chovat jako flex kontejner a tím jeho přímým
potomkům připadnou vlastnosti specifické pro flex položky.

``` css
display: inline-flex;
```

Tato hodnota je použita v případě, když chceme, aby kontejner byl
součástí řádku a choval se navenek jako in-line element.

``` css
flex-direction: row | column | row-reverse | column-reverse;
```

V základním nastavení je směr hlavní osy zleva doprava (`row`). Můžeme
přenastavit shora dolů (`column`), zprava doleva (`row-reverse`), zdola
nahoru (`column-reverse`).

![](media/image33.png) ![](media/image34.png)

``` css
flex-wrap: nowrap | wrap | wrap-reverse;
```

Defaultně je vlastnost nastavena na `nowrap`, tedy všechny položky
zůstávají vedle sebe a smrští se. Pokud zvolíme `wrap`, pak se položky
nesmršťují a pokračují na dalších řádcích směrem dolů. V případě, že
bychom chtěli zalamovat zdola nahoru - `wrap-reverse`.

![](media/image35.png) ![](media/image36.png)

``` css
flex-flow: column wrap;
```

Tato vlastnost zjednodušuje zápis pro direction a wrap do jedné
vlastnosti.

``` css
justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
```

Rozložení prostoru ve směru hlavní osy.

`flex-start` Položky jsou zarovnány v containeru od počátku hl. osy.

![](media/image37.png)

`flex-end` Zarovná od konce.

![C:\\Users\\veetek\\AppData\\Local\\Microsoft\\Windows\\INetCache\\Content.Word\\justify-end.png](media/image38.png){width="1.8883508311461068in"
height="0.8409722222222222in"}

`space-between` První a poslední položka každá na jednom konci osy
v rámci kotejneru a zbylé se pravidelně rozprostřou mezi nimi.

![C:\\Users\\veetek\\AppData\\Local\\Microsoft\\Windows\\INetCache\\Content.Word\\justify-space-between.png](media/image39.png){width="1.8958333333333333in"
height="0.8326388888888889in"}

`center	`Položky se shluknou ke středu.

![C:\\Users\\veetek\\AppData\\Local\\Microsoft\\Windows\\INetCache\\Content.Word\\justify-center.png](media/image40.png){width="1.9112718722659667in"
height="0.8523589238845144in"}

`space-around` Každá položka má po bocích stejné mezery, které se u dvou
sousedních položek sčítají.

![C:\\Users\\veetek\\AppData\\Local\\Microsoft\\Windows\\INetCache\\Content.Word\\justify-space-around.png](media/image41.png){width="1.9340944881889763in"
height="0.8394214785651793in"}

`space-evenly` Obdoba předchozího s tím rozdílem, že se mezery
sousedních položek nesčítají.

![C:\\Users\\veetek\\AppData\\Local\\Microsoft\\Windows\\INetCache\\Content.Word\\justify-space-evenly.png](media/image42.png){width="1.9194510061242345in"
height="0.8408956692913386in"}

``` css
align-items: stretch | flex-start | flex-end | center | baseline;
```

Zarovnání položek ve směru příčné osy.

`stretch` Položky se roztáhnou ve směru příčné osy a vyplní tak
kontejner.

![C:\\Users\\veetek\\AppData\\Local\\Microsoft\\Windows\\INetCache\\Content.Word\\align-items-stretch.png](media/image43.png){width="1.9241699475065617in"
height="0.8405807086614173in"}

`flex-start` Položky zarovnány od počátku př. osy.

> ![C:\\Users\\veetek\\AppData\\Local\\Microsoft\\Windows\\INetCache\\Content.Word\\align-items-start.png](media/image44.png){width="1.9243055555555555in"
> height="0.8340277777777778in"}

`flex-end` Zarovnání od konce.

> ![C:\\Users\\veetek\\AppData\\Local\\Microsoft\\Windows\\INetCache\\Content.Word\\align-items-end.png](media/image45.png){width="1.9291666666666667in"
> height="0.8340277777777778in"}

`center` Vycentrování položek.

![C:\\Users\\veetek\\AppData\\Local\\Microsoft\\Windows\\INetCache\\Content.Word\\align-items-center.png](media/image46.png){width="1.9233136482939632in"
height="0.8358727034120735in"}

`baseline` Zarovnání podle základní linky textu položek.

![C:\\Users\\veetek\\AppData\\Local\\Microsoft\\Windows\\INetCache\\Content.Word\\align-items-baseline.png](media/image47.png){width="1.886111111111111in"
height="0.8338385826771654in"}

``` css
align-content: stretch | flex-start | flex-end | center | space-between | space-around | space-evenly;
```

![](media/image48.png)Rozložení prostoru ve směru příčné osy mezi řádky
hl. osy. Všechny tyto hodnoty jsou variace na předchozí vlastnosti s tím
rozdílem, že rozdělujeme prostor mezi řádky.

``` text
gap, row-gap, column-gap
```

Vlastnosti definující základní mezery mezi položkami. Netýká se mezer
k okrajům kontejneru.

`gap: 15px;` Položky mají mezi sebou v každém směru mezeru 15px.

`gap: 15px 25px;` Položky mají mezi sebou mezeru ve směru příčné osy
15px a ve směru hlavní 25px.

`row-gap: 15px;` Položky mají mezi sebou mezeru ve směru příčné osy 15px
(default mezi řádky).

`column-gap: 25px;` Položky mají mezi sebou mezeru ve směru hlavní osy
25px (default mezi sloupci).

> ![C:\\Users\\veetek\\AppData\\Local\\Microsoft\\Windows\\INetCache\\Content.Word\\flex-gap.png](media/image49.png){width="2.9328357392825897in"
> height="0.8922123797025372in"}

#### Položky a jejich vlastnosti

``` css
flex-grow
```

Číslo bez jednotky udává, jak moc může položka růst. Defaultní hodnota
je 0. Pokud nastavíme 1 nebo třeba 4, číslo značí, jaký podíl z volné
plochy bude položka zaujímat vzhledem k ostatním položkám.

``` css
#polozka-1 {flex-grow: 2;}
flex-shrink
```

Rovněž číslo bez jednotky udává, jak se může položka smršťovat, pokud je
to nutno. Defaultní je 1. Pokud chceme, aby se položka nesmršťovala,
nastavíme na 0.

``` css
#polozka-1 {flex-shrink: 0;}
flex-basis
```

Jedná se o výchozí velikost položky (50%, 10rem). V defaultním nastavení
je nastaveno na auto.

``` css
#polozka-1 {flex-basis: 5rem;}
flex
```

Zkrácený zápis v pořadí grow, shrink, basis. První shrink je hodnota
povinná.

``` css
#polozka-1 {flex: 2 0 5rem;}
align-self
```

Pro zarovnání všech položek ve směru příčné osy platí `align-items`. Pro
nastavení hodnoty pro jednu konkrétní položku použijeme `align-self`.
Hodnoty můžete požít vizte `align-items`.

``` css
#polozka-2 {align-self: center;}
order
```

Ve výchozím stavu jsou položky v kontejneru v pořadí, v jakém jsou
napsány v HTML. Pořadí ale můžeme jednotlivým položkám změnit, pokud jim
přiřadíme čísla pořadí ve vlastnosti order.

``` css
#polozka-4 {order: 4;}
```

*Pokud byste si chtěli doplnit více informací o flexboxu, doporučuji
tuto stránku:*

*[https://css-tricks.com/snippets/css/a-guide-to-flexbox]{.underline}*

*Pro trénování základních funkcí flexboxu je výborná tato hra:
[https://flexboxfroggy.com]{.underline}*

### Z-index

Pokud pracujeme s pozicováním elementů (absolutní, relativní, fixní,
sticky nebo flex položky) a elementy se překrývají, ve výchozím
nastavení platí pravidlo pořadí, ve kterém jsou napsány v HTML kódu.
Druhý překrývá první, třetí překrývá druhý a první atd.

``` css
z-index
```

Pokud chceme pořadí určit sami, můžeme tak učinit vlastností `z-index`,
přičemž bezrozměrné číslo určuje pořadí překrytí elementu.

``` css
#pozicovany-element {z-index: 5;}
```

Pozor na dědění z-indexu. Pokud mám v parent prvku se z-indexem 0
potomka a budu se mu snažit přiřadit z-index vyšší, bude stále na nule.

## CSS proměnné a funkce

### Proměnné

``` css
var()
```

Můžeme si v rámci CSS stylů nadefinovat proměnné, které obsahují
specifické hodnoty, jež v dokumentu opakovaně využijeme.

1.  **Deklarace proměnné** v rámci CSS stylopisu -- pozor na jmennou
    konvenci. Proměnná musí začínat dvěma pomlčkami (\--) a je
    case-sensitive.

> ``` css
> :root {--main-color: #fd0000;}
> ```
>
> *Pokud proměnnou deklarujeme v pseudotřídě :root, je platná v celém
> dokumentu.*
>
> ``` css
> main {--main-color: #fd0000;}
> ```
>
> *Pokud proměnnou deklarujeme v určitém selektoru, je platná pouze
> v něm.*

2.  **Použití proměnné**

``` css
p {color: var(--main-color);}
```

> Pokud chcete eliminovat chyby ve stylopisu, vždy uvádějte i druhou
> hodnotu barvy pro případ, že by proměnná nebyla deklarována.

``` css
p {color: var(--main-color, red);}
```

### Funkce

`min()`**,** `max()`

Tyto funkce vracejí minimální/maximální z hodnot v závorce.

``` css
width: min(250px, 40%, 16rem);
calc()
```

Funkce vypočítá matematické operace (+, -, \*, /).

``` css
width: calc(100vw-2rem);
clamp()
```

Funkce vybírá ze tří hodnot -- první z hodnot je minimální, druhá
ideální a třetí maximální. Čili vrací prostřední hodnotu, pokud není
menší než první nebo větší než třetí.

``` css
width: clamp(10rem, 50%, 20rem);
```

# Webhosting -- stránky www, React app

Abyste si byli schopni vystavit své stránky a projekty na internetu, je
třeba, abyste si zřídili následující dvě věci:

-   doména

-   hosting poskytovatel

**Doména** je webová adresa, která vede k stránkám nebo webovým
aplikacím. **Poskytovatel webhostingu** umožňuje svým uživatelům uložit
soubory a data jejich stránek a aplikací na svých serverech a
zpřístupňuje jejich obsah na internetu.

Doménu si můžete pořídit zdarma u většiny webhosting poskytovatelů,
pokud příliš nelpíte na jejím názvu. Stejně tak i služby webhostingu
můžete využít zdarma, ovšem za cenu reklamních oznámení.

Samozřejmě, pokud se v budoucnu chystáte doménu využít více než jen pro
studijní či testovací účely, je dobré zvážit placenou doménu a
uživatelský plán u poskytovatele webhostingu. Nám ale nyní bude stačit
pro výukové účely ten bezplatný základ.

Jeden z webhostingů je **Endora** - [endora.cz](https://www.endora.cz),
která mj. poskytuje zdarma i MySQL databázi a její server podporuje PHP.
Což se hodí pro další fáze našeho kurzu.

![Obsah obrázku text, snímek obrazovky, číslo, Písmo Popis byl vytvořen
automaticky](media/image50.jpeg){width="6.302083333333333in"
height="3.8020833333333335in"}

Již na úvodní stránce si můžete otestovat, zda vámi vybrané jméno domény
není už někým obsazené. Při rozkliknutí nabídky u výběru „koncovky" vám
to nabídne i právě zmíněné domény zdarma. Ty mají sice prapodivné
koncovky typu *.jecool.net*, ale zase neplatíte ani korunu. Po výběru
domény si již můžete vybrat plán předplatného. Vyberte *Free*.

![Obsah obrázku text, snímek obrazovky, Písmo, Webová stránka Popis byl
vytvořen automaticky](media/image51.jpeg){width="6.291666666666667in"
height="3.625in"}

Poté si vyberete uživatelské jméno a email, který bude s vašim účtem
svázaný a po potvrzení správnosti emailu už jen nastavíte heslo a můžete
nahrávat soubory.

Zde jsou alternativy k Endoře:

-   [webnode.com](https://www.webnode.com/)

-   [zikum.cz](https://zikum.cz/)

-   [webzdarma.cz](https://www.webzdarma.cz/)

## FTP přístup

Po přihlášení do svého účtu si můžete přímo ve webovém rozhraní
prohlédnout obsah vašich složek na serveru hostingu. V postranní nabídce
jde o **Správce souborů** -\> název vaší domény.

![Obsah obrázku text, snímek obrazovky, software, Webová stránka Popis
byl vytvořen
automaticky](media/image52.jpeg){width="4.585683508311461in"
height="3.5in"}

Otevře se vám stránka *Správce souborů* rovnou ve složce, která by vás
měla zajímat nejvíce:

*nazev-vasi-domeny.cz/web/*

Jde totiž o root složku vašeho hostingu, kde byste měli mít hlavní
soubor *index.html*, resp. *index.php*, který je očekáván, když uživatel
zadá do adresního řádku adresu vaší domény. My tam nyní máme defaultně
přednastavený nějaký *index.php*, který návštěvníky vaší domény
momentálně upozorňuje, že zatím zde není nic k vidění.

Mazat a přidávat soubory lze i přes toto webové rozhraní, ale to je
způsob mírně kostrbatý.

![Obsah obrázku text, Písmo, snímek obrazovky Popis byl vytvořen
automaticky](media/image53.jpeg){width="6.302083333333333in"
height="1.3333333333333333in"}

Můžeme na to jít elegantněji přes FTP, což je zkratka pro File Transfer
Protocol, je standardní síťový protokol používaný k přenosu souborů mezi
klientem a serverem na počítačové síti.

Stáhněte si aplikaci WinSCP na stránkách
[winscp.net](https://winscp.net/), pokud již jiného obdobného klienta
nepoužíváte. Po instalaci a otevření vás automaticky klient vyzve
k přidání/přihlášení pro připojení k serveru.

![Obsah obrázku text, snímek obrazovky, displej, software Popis byl
vytvořen automaticky](media/image54.jpeg){width="5.081827427821523in"
height="3.4270833333333335in"}

Teď si asi říkáte, kde tyto údaje krom uživatelského jména a hesla
získám? Potřebné údaje máte v záložce postranního panelu na Endoře
s názvem **FTP**. Jako hostitel uveďte *kocicka.endora.cz* a číslo portu
*21*. Toto spojení si můžete uložit, abyste nemuseli vždy vyplňovat
znova a znova tyto údaje.

Nyní vidíte v okně klienta adresářovou strukturu na serveru a můžete
pohodlně manipulovat se soubory a složkami, tedy je i kopírovat ze svého
lokálního úložiště. Původní složky prosím nemažte. Jděte do root složky,
čili do té s názvem *web* a smažte si ten defaultní soubor *index.php*.

## 

## Hosting klasických www stránek

Pokud se jedná o hosting webových stránek, je třeba mít na paměti tři
důležité body:

-   ve složce musí být soubor s názvem **index.html** (nebo
    *index*.*php*), který funguje implicitně jako vstupní uzel při
    zadání adresy, např. *https://testovacidomena.funsite.cz*

-   jinak byste museli explicitně do adresy zadávat i název html
    souboru, pokud by se jmenoval jinak, např.
    *https://testovacidomena.funsite.cz/home.html*

-   musíte nahrát i všechny soubory stylu (např. *style.css*), skripty
    (např. *script.js*), soubory fontů, obrázky a jiná média, které máte
    nalinkované v html a css souborech

-   pamatujte na adresářovou hierarchii -- musíte ji buď zachovat, nebo
    budete muset upravit relativní cesty k souborům

-   i podsložky rootu mohou mít index.html, ale adresa se musí
    přizpůsobit cestě k souboru, např.:
    *https://testovacidomena.funsite.cz/podslozka*

## Deployment React aplikace

Pro příklad uvedu nejjednodušší způsob, jak udělat správně build
aplikace a následně ji nahrát na hosting. Opět je třeba se držet tohoto
následujícího postupu.

1.  **Úprava package.json**

První a nejzásadnější věc je nastavit kořenovou složku React aplikace na
hostingu, aby se při buildu aplikace správně vytvořily cesty k souborům.

Takže si musíte dobře rozmyslet, kam soubory aplikace v rámci serveru
umístíte. Uvedu na příkladu:

![Obsah obrázku text, Písmo, snímek obrazovky, design Popis byl vytvořen
automaticky](media/image55.jpeg){width="2.0833333333333335in"
height="1.3020833333333333in"}Já se rozhodnul, že si vytvořím v rootu
svojí adresářové struktury (složka **web**) podsložku **projects** vedle
*index.html*, což bude řekněme stránka mého portfolia. Dále budu
předpokládat, že projektů bude více, proto si i v této složce vytvořím
podsložku **react-app**. Zde budu umísťovat soubory React aplikace.

Nastavím na začátek *package.json* následující vlastnost:

*\"homepage\"*:
\"https://testovacidomena.funsite.cz/projects/react-app\",

Pro vysvětlení:

-   *https://testovacidomena.funsite.cz/* je adresa rootové složky
    domény (web)

-   *projects/react-app* je už relativní cesta ke složce, kde budou
    soubory aplikace

2.  **Build aplikace a přesun souborů**

V příkazovém řádku ve složce, kde máte rozdělaný React projekt, spusťte
příkaz

**npm run build**

Ve složce projektu se vám vygeneruje podsložka build. Veškerý obsah této
složky zkopírujte do výše vybrané složky na hostingu a máte hotovo.
